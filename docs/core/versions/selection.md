---
title: Auswählen der zu verwendenden .NET Core-Version
description: In diesem Artikel erfahren Sie, wie .NET Core automatisch Laufzeitversionen für Ihr Programm sucht und auswählt. Außerdem erfahren Sie in diesem Artikel, wie Sie eine bestimmte Version erzwingen.
author: thraka
ms.author: adegeo
ms.date: 06/26/2019
ms.openlocfilehash: 546725db907937dea6fe0739656fb585a8855644
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713977"
---
# <a name="select-the-net-core-version-to-use"></a>Auswählen der zu verwendenden .NET Core-Version

Dieser Artikel beschreibt die Richtlinien, die .NET Core-Tools, .NET Core SDK und die Laufzeit für die Versionsauswahl verwenden. Durch diese Richtlinien wird ein Gleichgewicht zwischen der Ausführung von Anwendungen mit den angegebenen Versionen und der Ermöglichung eines einfachen Upgrades von Entwickler- und Endbenutzercomputern hergestellt. Mit diesen Richtlinien werden die folgenden Aktionen ausgeführt:

- Einfache und effiziente Bereitstellung von .NET Core, einschließlich Sicherheit und Zuverlässigkeitsupdates
- Verwendung der neuesten Tools und Befehle unabhängig von der Ziellaufzeit

Für das Vorkommen der Versionsauswahl gilt:

- Wenn Sie einen SDK-Befehl ausführen, [verwendet das SDK die neueste installierte Version](#the-sdk-uses-the-latest-installed-version).
- Wenn Sie eine Assembly erstellen, [definieren Zielframeworkmoniker (TFM) die Erstellungszeit-APIs](#target-framework-monikers-define-build-time-apis).
- Wenn Sie eine .NET Core-Anwendung ausführen, [führen die vom Zielframework abhängigen Apps einen Rollforward aus](#framework-dependent-apps-roll-forward).
- Wenn Sie eine eigenständige Anwendung veröffentlichen, [umfassen eigenständige Bereitstellungen die ausgewählte Laufzeit](#self-contained-deployments-include-the-selected-runtime).

Im Folgenden erläutert dieses Dokument diese vier Szenarios.

## <a name="the-sdk-uses-the-latest-installed-version"></a>SDK verwendet die neueste installierte Version

Zu den SDK-Befehlen zählen `dotnet new` oder `dotnet run`. Die .NET Core-CLI muss für jeden `dotnet`-Befehl eine SDK-Version auswählen. Die CLI verwendet standardmäßig das neueste SDK, das auf dem Computer installiert ist, auch wenn Folgendes zutrifft:

- Das Projekt ist auf eine frühere Version der .NET Core-Runtime ausgelegt.
- Die neueste Version des .NET Core SDK ist eine Vorschauversion.

Sie können die Vorteile der neuesten SDK-Funktionen und -Verbesserungen nutzen, während Sie frühere .NET Core-Laufzeitversionen als Ziel festlegen. Sie können mehrere Laufzeitversionen für verschiedene Projekte festlegen, indem Sie die gleichen SDK-Tools für alle Projekte verwenden.

In seltenen Fällen werden Sie eine frühere SDK-Version benötigen. Sie geben die Version in einer [*global.json*-Datei](../tools/global-json.md) an. Die Richtlinie zum Verwenden der neuesten Version bedeutet, dass Sie *global.json* nur verwenden, um eine .NET Core SDK-Version vor der zuletzt installierten Version anzugeben.

*global.json* kann überall in der Dateihierarchie platziert werden. Die CLI sucht im Projektverzeichnis aufwärts, bis sie das erste *global.json* findet. Sie bestimmen, für welche Projekte eine bestimmte *global.json*-Datei gilt, indem Sie ihren Platz im Dateisystem angeben. Die .NET Core-CLI sucht nach einer *global.json*-Datei, die den Pfad vom aktuellen Arbeitsverzeichnis iterativ nach oben navigiert. Die erste gefundene *global.json*-Datei gibt die verwendete Version an. Wenn diese SDK-Version installiert ist, wird sie verwendet. Wenn das in der *global.json-Datei* angegebene SDK nicht gefunden wird, verwendet die .NET-CLI [Abgleichsregeln](../tools/global-json.md#matching-rules), um ein kompatibles SDK auszuwählen oder schlägt fehl, wenn keine gefunden werden.

Das folgende Beispiel veranschaulicht die *global.json*-Syntax:

``` json
{
  "sdk": {
    "version": "2.0.0"
  }
}
```

Die Auswahl einer SDK-Version verläuft folgendermaßen:

1. `dotnet` sucht nach einer *global.json*-Datei, die den Pfad vom aktuellen Arbeitsverzeichnis iterativ zurück nach oben navigiert.
1. `dotnet` verwendet das in der ersten gefundenen *global.json*-Datei angegebene SDK.
1. `dotnet` verwendet das zuletzt installierte SDK, wenn keine *global.json*-Datei gefunden wird.

Weitere Informationen zur Auswahl einer SDK-Version finden Sie im Artikel zu *global.json* im Abschnitt [Abgleichsregeln](../tools/global-json.md#matching-rules).

## <a name="target-framework-monikers-define-build-time-apis"></a>Zielframeworkmoniker definieren Erstellungszeit-APIs

Sie erstellen Ihr Projekt mit APIs, die in einem **Zielframeworkmoniker** definiert sind. Sie geben das [Zielframework](../../standard/frameworks.md) in der Projektdatei an. Setzen Sie das Element `TargetFramework` in Ihrer Projektdatei wie folgt fest:

``` xml
<TargetFramework>netcoreapp2.0</TargetFramework>
```

Sie können Ihr Projekt mit mehreren Zielframeworkmonikern erstellen. Das Festlegen mehrerer Zielframeworks ist üblicher für Bibliotheken, kann aber auch mit Anwendungen durchgeführt werden. Geben Sie eine `TargetFrameworks`-Eigenschaft an (Plural von `TargetFramework`). Die Zielframeworks werden wie im folgenden Beispiel durch Semikolons getrennt:

``` xml
<TargetFrameworks>netcoreapp2.0;net47</TargetFrameworks>
```

Ein bestimmtes SDK unterstützt einen festen Satz von Frameworks, der auf das Zielframework der im Lieferumfang enthaltenen Laufzeit begrenzt ist. Beispielsweise enthält das .NET Core 2.0 SDK die .NET Core 2.0-Laufzeit, eine Implementierung des Zielframeworks `netcoreapp2.0`. Die .NET Core 2.0 SDK unterstützt `netcoreapp1.0`, `netcoreapp1.1` und `netcoreapp2.0`, jedoch nicht `netcoreapp2.1` (oder höher). Für `netcoreapp2.1` installieren Sie das .NET Core 2.1 SDK.

.NET Standard-Zielframeworks sind ebenfalls auf das Zielframework der Laufzeit begrenzt, die zum SDK-Lieferumfang gehört. Das .NET Core 2.0 SDK ist auf `netstandard2.0` begrenzt.

## <a name="framework-dependent-apps-roll-forward"></a>Von Frameworks abhängige Apps führen einen Rollforward aus

Wenn Sie eine Anwendung von der Quelle aus mit [`dotnet run`](../tools/dotnet-run.md) ausführen, von einer [**Framework-abhängigen Bereitstellung**](../deploying/index.md#framework-dependent-deployments-fdd) aus mit [`dotnet myapp.dll`](../tools/dotnet.md#description) oder von einer [**Framework-abhängigen ausführbaren Datei**](../deploying/index.md#framework-dependent-executables-fde) aus mit `myapp.exe`, ist die ausführbare `dotnet`-Datei der **Host** für die Anwendung.

Der Host wählt die neueste Patchversion aus, die auf dem Computer installiert ist. Wenn Sie beispielsweise `netcoreapp2.0` in Ihrer Projektdatei angegeben haben und `2.0.4` die zuletzt installierte .NET-Laufzeit ist, wird die Laufzeit `2.0.4` verwendet.

Wenn keine gültige `2.0.*`-Version gefunden wird, wird eine neue `2.*`-Version verwendet. Wenn Sie beispielsweise `netcoreapp2.0` angegeben haben und nur `2.1.0` installiert ist, wird die Anwendung mit der Laufzeit `2.1.0` ausgeführt. Dieses Verhalten wird als „Rollforward einer Nebenversion“ bezeichnet. Frühere Versionen werden ebenfalls nicht berücksichtigt. Wenn keine gültige Laufzeit installiert ist, wird die Anwendung nicht ausgeführt.

Einige Verwendungsbeispiele veranschaulichen das Verhalten, wenn Sie für Version 2.0 programmieren:

- Version 2.0 ist angegeben. 2.0.5 ist die höchste installierte Patchversion. 2.0.5 wird verwendet.
- Version 2.0 ist angegeben. Es sind keine 2.0.*-Versionen installiert. 1.1.1 ist die höchste installierte Laufzeit. Eine Fehlermeldung wird angezeigt.
- Version 2.0 ist angegeben. Es sind keine 2.0.*-Versionen installiert. 2.2.2 ist die höchste installierte 2.x-Laufzeitversion. 2.2.2 wird verwendet.
- Version 2.0 ist angegeben. Es sind keine 2.x-Versionen installiert. Version 3.0.0 ist installiert. Eine Fehlermeldung wird angezeigt.

Der Rollforward einer Nebenversion hat einen Nebeneffekt, der sich auf Endbenutzer auswirken kann. Betrachten Sie das folgende Szenario:

1. Die Anwendung gibt an, dass die Version 2.0 erforderlich ist.
2. Bei der Ausführung der Anwendung ist zwar nicht die Version 2.0.* installiert, dafür aber Version 2.2.2. Dann wird Version 2.2.2 verwendet.
3. Wenn der Benutzer später die Version 2.0.5 installiert und die Anwendung erneut ausführt, wird Version 2.0.5 verwendet.

Möglicherweise verhalten sich 2.0.5 und 2.2.2 unterschiedlich, insbesondere in Szenarien wie der Serialisierung von Binärdaten.

## <a name="self-contained-deployments-include-the-selected-runtime"></a>Eigenständige Bereitstellungen umfassen die ausgewählte Laufzeit

Sie können eine Anwendung als [**eigenständige Bereitstellung**](../deploying/index.md#self-contained-deployments-scd) veröffentlichen. Bei diesem Ansatz werden die .NET Core-Laufzeit und -Bibliotheken mit Ihrer Anwendung zusammengeführt. Eigenständige Bereitstellungen sind nicht von Laufzeitumgebungen abhängig. Die Auswahl der Laufzeitversion erfolgt bei der Veröffentlichung, nicht bei der Ausführung.

Der Veröffentlichungsprozess wählt die neueste Patchversion der angegebenen Laufzeitfamilie aus. Beispielsweise wählt `dotnet publish` .NET Core 2.0.4 aus, wenn das die neueste Patchversion der .NET Core 2.0-Laufzeitfamilie ist. Das Zielframework (einschließlich der neuesten installierten Sicherheitspatches) ist in der Anwendung enthalten.

Wenn die für eine Anwendung angegebene Mindestversion nicht erfüllt wird, tritt ein Fehler auf. `dotnet publish` wird an die neueste Laufzeitpatchversion gebunden (innerhalb einer bestimmten Haupt-/Nebenversionfamilie). `dotnet publish` unterstützt nicht die Rollforwardsemantik von `dotnet run`. Weitere Informationen zu Patches und eigenständigen Bereitstellungen finden Sie im Artikel zur [Auswahl von Laufzeitpatches](../deploying/runtime-patch-selection.md) bei der Bereitstellung von .NET Core-Anwendungen.

Eigenständige Bereitstellungen erfordern möglicherweise eine bestimmte Patchversion. Sie können die mindestens erforderliche Laufzeitpatchversion in der Projektdatei überschreiben (mit einer höheren/niedrigeren Version), wie im folgenden Beispiel gezeigt:

``` xml
<RuntimeFrameworkVersion>2.0.4</RuntimeFrameworkVersion>
```

Das Element `RuntimeFrameworkVersion` überschreibt die Standardversionsrichtlinie. Für eigenständige Bereitstellungen gibt `RuntimeFrameworkVersion` die *genaue* Laufzeitframeworkversion an. Für Anwendungen, die von Frameworks abhängen, gibt `RuntimeFrameworkVersion` die *mindestens* erforderliche Laufzeitframeworkversion an.
