---
title: Auswählen der zu verwendenden .NET Core-Version
description: In diesem Artikel erfahren Sie, wie .NET Core automatisch Laufzeitversionen für Ihr Programm sucht und auswählt. Außerdem erfahren Sie in diesem Artikel, wie Sie eine bestimmte Version erzwingen.
author: adegeo
ms.author: adegeo
ms.date: 03/24/2020
ms.openlocfilehash: faaa638905bb3c8e9cd4c09af83979d90698df3d
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803117"
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
    "version": "3.0.0"
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
<TargetFramework>netcoreapp3.0</TargetFramework>
```

Sie können Ihr Projekt mit mehreren Zielframeworkmonikern erstellen. Das Festlegen mehrerer Zielframeworks ist üblicher für Bibliotheken, kann aber auch mit Anwendungen durchgeführt werden. Geben Sie eine `TargetFrameworks`-Eigenschaft an (Plural von `TargetFramework`). Die Zielframeworks werden wie im folgenden Beispiel durch Semikolons getrennt:

``` xml
<TargetFrameworks>netcoreapp3.0;net47</TargetFrameworks>
```

Ein bestimmtes SDK unterstützt einen festen Satz von Frameworks, der auf das Zielframework der im Lieferumfang enthaltenen Laufzeit begrenzt ist. Beispielsweise enthält das .NET Core 3.0 SDK die .NET Core 3.0-Runtime, bei der es sich um eine Implementierung des `netcoreapp3.0`-Zielframeworks handelt. Das .NET Core 3.0 SDK unterstützt `netcoreapp2.1`, `netcoreapp2.2` und `netcoreapp3.0`, jedoch nicht `netcoreapp3.1` (oder höher). Für `netcoreapp3.1` installieren Sie das .NET Core 3.1 SDK.

.NET Standard-Zielframeworks sind ebenfalls auf das Zielframework der Laufzeit begrenzt, die zum SDK-Lieferumfang gehört. Das .NET Core 3.1 SDK ist auf `netstandard2.1` begrenzt. Weitere Informationen finden Sie unter [.NET Standard](../../standard/net-standard.md).

## <a name="framework-dependent-apps-roll-forward"></a>Von Frameworks abhängige Apps führen einen Rollforward aus

Wenn Sie eine Anwendung von der Quelle aus mit [`dotnet run`](../tools/dotnet-run.md) ausführen, von einer [**Framework-abhängigen Bereitstellung**](../deploying/index.md#publish-runtime-dependent) aus mit [`dotnet myapp.dll`](../tools/dotnet.md#description) oder von einer [**Framework-abhängigen ausführbaren Datei**](../deploying/index.md#publish-runtime-dependent) aus mit `myapp.exe`, ist die ausführbare `dotnet`-Datei der **Host** für die Anwendung.

Der Host wählt die neueste Patchversion aus, die auf dem Computer installiert ist. Wenn Sie beispielsweise `netcoreapp3.0` in Ihrer Projektdatei angegeben haben und `3.0.2` die zuletzt installierte .NET-Laufzeit ist, wird die Laufzeit `3.0.2` verwendet.

Wenn keine gültige `3.0.*`-Version gefunden wird, wird eine neue `3.*`-Version verwendet. Wenn Sie beispielsweise `netcoreapp3.0` angegeben haben und nur `3.1.0` installiert ist, wird die Anwendung mit der Laufzeit `3.1.0` ausgeführt. Dieses Verhalten wird als „Rollforward einer Nebenversion“ bezeichnet. Frühere Versionen werden ebenfalls nicht berücksichtigt. Wenn keine gültige Laufzeit installiert ist, wird die Anwendung nicht ausgeführt.

Einige Verwendungsbeispiele veranschaulichen das Verhalten, wenn Sie für Version 3.0 programmieren:

- ✔️ 3.0 ist angegeben. 3.0.3 ist die höchste installierte Patchversion. 3.0.3 wird verwendet.
- ❌ 3.0 ist angegeben. Es sind keine 3.0.*-Versionen installiert. 2.1.1 ist die höchste installierte Runtime. Eine Fehlermeldung wird angezeigt.
- ✔️ 3.0 ist angegeben. Es sind keine 3.0.*-Versionen installiert. 3.1.0 ist die höchste installierte Runtimeversion. 3.1.0 wird verwendet.
- ❌ 2.0 ist angegeben. Es sind keine 2.x-Versionen installiert. 3.0.0 ist die höchste installierte Runtime. Eine Fehlermeldung wird angezeigt.

Der Rollforward einer Nebenversion hat einen Nebeneffekt, der sich auf Endbenutzer auswirken kann. Betrachten Sie das folgende Szenario:

1. Die Anwendung gibt an, dass Version 3.0 erforderlich ist.
2. Bei Ausführung der Anwendung wird zwar nicht Version 3.0.* installiert, dafür aber Version 3.1.0. Es wird Version 3.1.0 verwendet.
3. Wenn der Benutzer später die Version 3.0.3 installiert und die Anwendung noch mal ausführt, wird Version 3.0.3 verwendet.

Möglicherweise verhalten sich Version 3.0.3 und Version 3.1.0 unterschiedlich, insbesondere in Szenarios wie der Serialisierung von Binärdaten.

## <a name="self-contained-deployments-include-the-selected-runtime"></a>Eigenständige Bereitstellungen umfassen die ausgewählte Laufzeit

Sie können eine Anwendung als [**eigenständige Bereitstellung**](../deploying/index.md#publish-self-contained) veröffentlichen. Bei diesem Ansatz werden die .NET Core-Laufzeit und -Bibliotheken mit Ihrer Anwendung zusammengeführt. Eigenständige Bereitstellungen sind nicht von Laufzeitumgebungen abhängig. Die Auswahl der Laufzeitversion erfolgt bei der Veröffentlichung, nicht bei der Ausführung.

Der Veröffentlichungsprozess wählt die neueste Patchversion der angegebenen Laufzeitfamilie aus. Beispielsweise wählt `dotnet publish` .NET Core 3.0.3 aus, wenn es sich hierbei um die neueste Patchversion der .NET Core 3.0-Runtimefamilie handelt. Das Zielframework (einschließlich der neuesten installierten Sicherheitspatches) ist in der Anwendung enthalten.

Wenn die für eine Anwendung angegebene Mindestversion nicht erfüllt wird, tritt ein Fehler auf. `dotnet publish` wird an die neueste Laufzeitpatchversion gebunden (innerhalb einer bestimmten Haupt-/Nebenversionfamilie). `dotnet publish` unterstützt nicht die Rollforwardsemantik von `dotnet run`. Weitere Informationen zu Patches und eigenständigen Bereitstellungen finden Sie im Artikel zur [Auswahl von Laufzeitpatches](../deploying/runtime-patch-selection.md) bei der Bereitstellung von .NET Core-Anwendungen.

Eigenständige Bereitstellungen erfordern möglicherweise eine bestimmte Patchversion. Sie können die mindestens erforderliche Laufzeitpatchversion in der Projektdatei überschreiben (mit einer höheren/niedrigeren Version), wie im folgenden Beispiel gezeigt:

``` xml
<RuntimeFrameworkVersion>3.0.3</RuntimeFrameworkVersion>
```

Das Element `RuntimeFrameworkVersion` überschreibt die Standardversionsrichtlinie. Für eigenständige Bereitstellungen gibt `RuntimeFrameworkVersion` die *genaue* Laufzeitframeworkversion an. Für Anwendungen, die von Frameworks abhängen, gibt `RuntimeFrameworkVersion` die *mindestens* erforderliche Laufzeitframeworkversion an.

## <a name="see-also"></a>Siehe auch

- [Herunterladen und Installieren von .NET Core](../install/index.yml)
- [Entfernen von .NET Core-Runtime und SDK](../install/remove-runtime-sdk-versions.md)
