---
title: Verpacken einer Verteilung von .NET Core
description: "Erfahren Sie, wie Sie .NET Core für die Verteilung verpacken, benennen und mit einer Versionsnummer versehen."
keywords: .NET, .NET Core, Quelle, Build
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 71b9d722-c5a8-4271-9ce1-d87e7ae2494d
ms.openlocfilehash: 7ff5ed127ad0d4f435c697a8f35b33c7ba3b56ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="net-core-distribution-packaging"></a>Verpacken einer Verteilung von .NET Core

Da .NET Core auf immer mehr Plattformen verfügbar wird, ist es hilfreich zu erfahren, wie man es verpackt, benennt und mit einer Versionsnummer versieht. Auf diese Weise kann mithilfe von Paketverwaltern eine konsistente Benutzererfahrung sichergestellt werden, unabhängig davon, wo Benutzer .NET ausführen.

## <a name="net-core-components"></a>.NET Core-Komponenten

.NET Core besteht aus drei Hauptteilen, die verpackt werden müssen:

1. **Der Host** (auch bekannt als „Muxer“) verfügt über zwei unterschiedliche Rollen: das Aktivieren einer Laufzeit, um eine Anwendung zu starten und das Aktivieren eines SDKs, um Befehle an dieses weiterzuleiten. Der Host ist eine native ausführbare Datei (`dotnet.exe`) und deren unterstützende Richtlinienbibliotheken (in `host/fxr` installiert). Er wird aus dem Code im Repository [`dotnet/core-setup`](https://github.com/dotnet/core-setup/) erstellt. Es gibt in der Regel nur einen Host auf einem bestimmten Computer, auch wenn dies nicht zwingend erforderlich ist.
2. **Das Framework** besteht aus einer Laufzeit und unterstützt verwaltete Bibliotheken. Das Framework kann als Teil einer Anwendung installiert werden oder als ein freigegebenes Framework an einem zentralen Speicherort, der von mehreren Anwendungen wiederverwendet werden kann. Es kann eine beliebige Anzahl von freigegebenen Frameworks geben, die auf einem bestimmten Computer installiert sind. Freigegebene Frameworks sind unter `shared/Microsoft.NETCore.App/<version>` vorhanden. Der Host führt ein Rollforward über Patchversionen aus. Wenn eine Anwendung `Microsoft.NETCore.App` 1.0.0 zum Ziel hat und nur 1.0.4 vorhanden ist, wird die App mit 1.0.4 gestartet.
3. **Das SDK** (auch bekannt als „die Tools“) ist ein Set von verwalteten Tools, die zum Schreiben und Erstellen von .NET Core-Bibliotheken und -Anwendungen verwendet werden können. Das SDK enthält die CLI, MSBuild und zugeordnete Buildaufgaben und Ziele, NuGet, neue Projektvorlagen usw. Es ist möglich, über mehrere SDKs auf einem Computer zu verfügen (z.B. zum Erstellen von Projekten, die explizit eine ältere Version erfordern), aber es wird empfohlen, die neuesten freigegebenen Tools zu verwenden.

## <a name="recommended-package-names"></a>Empfohlene Paketnamen

Die folgende Anleitung ist unsere Empfehlung für Paketnamen. Ein Paketverwalter kann sich möglicherweise, basierend auf verschiedenen Gründen, davon trennen, z.B. eine andere Tradition der bestimmten Verteilung, die sie als Ziel bestimmen.

### <a name="minimum-package-set"></a>Minimales Paketset

* `dotnet-runtime-[major].[minor]`: ein freigegebenes Framework mit der angegebenen Version (nur die neueste Patchversion für eine bestimmte major+minor-Kombination sollte im Paket-Manager verfügbar sein). **Abhängigkeiten**: `dotnet-host`
* `dotnet-sdk`: das neueste SDK **Abhängigkeiten**: die neueste `dotnet-sdk-[major].[minor]`
* `dotnet-sdk-[major].[minor]`: das SDK mit der angegebenen Version. Die angegebene Version ist die höchste enthaltene Version von enthaltenen freigegebenen Frameworks, sodass Benutzer problemlos ein SDK mit einem freigegebenen Framework verknüpfen können. **Abhängigkeiten**: `dotnet-host`, ein oder mehrere `dotnet-runtime-[major].[minor]` (eine der Laufzeiten wird durch den SDK Code selbst verwendet, mit den anderen können Benutzer erstellen und ausführen).
* `dotnet-host`: der neueste Host.

#### <a name="preview-versions"></a>Vorschauversionen

Paketverwalter können möglicherweise Vorschauversionen des freigegebenen Frameworks und SDKs einschließen. Diese sollten niemals im Paket `dotnet-sdk` ohne Versionsnummer enthalten sein, aber sie können als Pakete mit Versionsnummer mit einem zusätzlichen Vorschaumarker freigegeben werden, der an die major- und minor-Versionsabschnitte des Namens angefügt ist. Beispielsweise gibt es möglicherweise ein Paket `dotnet-sdk-2.0-preview-final`.

### <a name="optional-additional-packages"></a>Optionale zusätzliche Pakete

Einige Verwalter können möglicherweise zusätzliche Pakete bereitstellen, z.B.:

* `dotnet-lts`: die neueste Long Term Support-Version (LTS) des freigegebenen Frameworks. [LTS- und Current-Releasepläne](~/docs/core/versions/lts-current.md) entsprechen unterschiedlichen Rhythmen, mit denen .NET Core freigegeben wird. Benutzer haben die Wahl zwischen dem einen oder anderen Plan, je nachdem, wie oft sie aktualisieren möchten. Dies ist ein Konzept, das auch daran gebunden ist, Ebenen zu unterstützen. Es kann also Sinn machen, abhängig von der berücksichtigten Distribution.

## <a name="disk-layout"></a>Datenträgerlayout

Bei der Installation von .NET Core-Paketen ist die relative Platzierung ihrer Ziele auf dem Datenträger erheblich.
Der `dotnet.exe`-Host sollte neben den Ordnern `sdk` und `shared` platziert sein, die den Inhalt mit Versionsangabe der SDK Pakete `dotnet-sdk` und der Pakete des freigegebenen Framework `dotnet-runtime` enthalten.

Das Datenträgerlayout von Dateien und Verzeichnissen in den Paketen ist mit einer Version versehen. Dies bedeutet, dass die Aktualisierung auf die neueste `dotnet-runtime` die neue Version parallel mit früheren Versionen installiert, wodurch die Möglichkeit verringert wird, dass vorhandene Anwendungen durch Aktualisieren des Pakets beschädigt werden. Paketupdates sollten keine früheren Versionen entfernen.

## <a name="update-policies"></a>Aktualisieren von Richtlinien

Wenn ein `update` ausgeführt wird, lautet das Verhalten der einzelnen Pakete wie folgt:

* `dotnet-runtime-[major].[minor]`: neue Patchversionen aktualisieren das Paket, aber neue Haupt- oder Nebenversionen sind getrennte Pakete.
* `dotnet-sdk`: `update` führt ein Rollforward für Haupt-, Neben- und Patchversionen aus.
* `dotnet-sdk-[major].[minor]`: neue Patchversionen aktualisieren das Paket, aber neue minor- oder major-Versionen sind getrennte Pakete.
* `dotnet-lts`: `update` führt ein Rollforward für major-, minor- und Patchversionen aus.

In diesem Thema wurden unsere Empfehlungen für das Verpacken von .NET Core präsentiert, jedoch kann jede Distribution wählen, welche Versionen wann angeboten werden. Beispielsweise kann eine Distribution, die mehr Wert auf Stabilität als auf Aktualität legt, nur Versionen freigeben, die sich nach dem LTS-Releaseplan richten.