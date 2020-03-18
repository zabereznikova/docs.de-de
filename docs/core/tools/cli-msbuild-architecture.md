---
title: Architektur der .NET Core-Befehlszeilentools
description: Informationen zu .NET Core-Toolschichten und Änderungen der neuesten Versionen.
ms.date: 03/06/2017
ms.openlocfilehash: fde1a0acb6af9dd65aa3466b4ea37473b2eab6fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092914"
---
# <a name="high-level-overview-of-changes-in-the-net-core-tools"></a>Allgemeine Übersicht über Änderungen in .NET Core-Tools

Dieses Dokument beschreibt die Änderungen im Zusammenhang mit dem Verschieben von *project.json* nach MSBuild und das Projektsystem *csproj* mit Informationen zu den Änderungen an den Schichten der .NET Core-Tools und die Implementierung der CLI-Befehle. Diese Änderungen sind mit der Version von .NET Core SDK 1.0 und Visual Studio 2017 am 7. März 2017 aufgetreten (weitere Informationen finden Sie in der [Ankündigung](https://devblogs.microsoft.com/dotnet/announcing-net-core-tools-1-0/)), aber sie wurden zuerst mit der Version von .NET Core SDK Preview 3 implementiert.

## <a name="moving-away-from-projectjson"></a>Abkehr von „project.json“

Die größte Änderung in den Tools für .NET Core ist sicherlich die [Abkehr von „project.json“ hin zu „csproj“](https://devblogs.microsoft.com/dotnet/changes-to-project-json/) als Projektsystem. Die neuesten Versionen der Befehlszeilentools unterstützen keine *project.json*-Dateien. Das heißt, dass diese Version nicht zum Erstellen, Ausführen und Veröffentlichen von auf „project.json“ basierenden Anwendungen und Bibliotheken verwendet werden kann. Sie müssen Ihre vorhandenen Projekte migrieren oder neue Projekte starten, um diese Version der Tools verwenden zu können.

Im Rahmen dieses Wechsels wurde die benutzerdefinierte Build-Engine, das zum Erstellen von „project.json“-Projekten entwickelt wurde, durch eine ausgereifte und vollausgestattete Build-Engine namens [MSBuild](https://github.com/Microsoft/msbuild) ersetzt. MSBuild ist eine in der .NET-Community bekannte Engine. Dies ist seit dem ersten Release der Plattform eine wichtige Technologie. Da mit MSBuild .NET Core-Anwendungen erstellt werden müssen, wurde MSBuild zu .NET Core portiert und kann auf allen Plattformen genutzt werden, auf denen .NET Core ausgeführt wird. Eines der wichtigsten Ziele von .NET Core ist ein plattformübergreifender Entwicklungsstapel, und wir haben dafür gesorgt, dass auch nach diesem Wechsel dieses Ziel erfüllt wird.

> [!TIP]
> Wenn Sie noch nicht mit MSBuild vertraut sind und mehr darüber erfahren möchten, können Sie zum Einstieg den Artikel [MSBuild-Konzepte](/visualstudio/msbuild/msbuild-concepts) lesen.

## <a name="the-tooling-layers"></a>Die Toolschichten

Infolge der Änderung der Build-Engine und der Bewegung weg vom vorhandenen Projektsystem kamen natürlich einige Fragen auf. Haben diese Änderungen Auswirkungen auf die allgemeinen „Schichten“ des .NET Core-Toolökosystems? Gibt es neue Bits und Komponenten?

Lassen Sie uns als schnelle Auffrischung mit den Schichten in Preview 2 beginnen, die die folgende Abbildung zeigt:

![Allgemeine Architektur der Preview 2-Tools](media/cli-msbuild-architecture/p2-arch.png)

Die Schichten der Tools in Vorschauversion 2 sind unkompliziert. Die .NET Core-CLI bildet die Basis. Alle weiteren Tools auf höherer Ebene wie beispielsweise Visual Studio oder Visual Studio Code hängen zum Erstellen von Projekten, Wiederherstellen von Abhängigkeiten usw. von der CLI ab. Für einen Wiederherstellungsvorgang in Visual Studio musste z. B. der Befehl `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) in der CLI aufgerufen werden.

Durch den Wechsel zum neuen Projektsystem ändert sich die vorherige Abbildung:

![Grundlegende Architektur von .NET Core SDK 1.0.0](media/cli-msbuild-architecture/p3-arch.png)

Der Hauptunterschied besteht darin, dass die CLI nicht mehr die Fundamentschicht darstellt. Diese Rolle wird jetzt von der „freigegebenen SDK-Komponente“ übernommen. Diese freigegebene SDK-Komponente ist eine Gruppe von Zielen und zugehörigen Aufgaben, die für das Kompilieren des Codes, dessen Veröffentlichung, das Packen von NuGet-Paketen usw. verantwortlich sind. Das .NET Core SDK ist ein Open-Source-Produkt und auf GitHub im [SDK-Repository](https://github.com/dotnet/sdk) verfügbar.

> [!NOTE]
> Ein „Ziel“ ist ein MSBuild-Ausdruck, der einen benannten Vorgang angibt, den MSBuild aufrufen kann. Es ist in der Regel an eine oder mehrere Aufgaben gekoppelt, die dem Ziel entsprechende Logik ausführen. MSBuild unterstützt viele vorgefertigte Ziele, z.B. `Copy` oder `Execute`. Außerdem können Benutzer mithilfe von verwaltetem Code eigene Aufgaben schreiben und Ziele definieren, um diese Aufgaben ausführen. Weitere Informationen finden Sie unter [MSBuild-Aufgaben](/visualstudio/msbuild/msbuild-tasks).

Alle Toolsets nutzen nun die freigegebene SDK-Komponente und ihre Ziele. Das gibt auch für die CLI. Visual Studio 2019 ruft beispielsweise nicht den `dotnet restore`-Befehl ([siehe Hinweis](#dotnet-restore-note)) auf, um Abhängigkeiten für .NET Core-Projekte wiederherzustellen. Stattdessen wird direkt das Ziel „Wiederherstellen“ verwendet. Da es sich MSBuild-Ziele handelt, können Sie MSBuild auch „roh“ verwenden, um sie mit dem Befehl [dotnet msbuild](dotnet-msbuild.md) auszuführen.

### <a name="cli-commands"></a>CLI-Befehle

Die freigegebene SDK-Komponente bedeutet, dass die meisten vorhandenen CLI-Befehle als MSBuild-Aufgaben und -Ziele neu implementiert wurden. Was bedeutet dies für die CLI-Befehle und Ihre Nutzung des Toolsets?

Aus Benutzersicht ändert sich die Art der Verwendung der CLI nicht. Die CLI weist noch immer die Hauptbefehle auf, die im Release der .NET Core 1.0-Vorschauversion 2 vorhanden waren:

- `new`
- `restore`
- `run`
- `build`
- `publish`
- `test`
- `pack`

Diese Befehle werden weiter wie erwartet ausgeführt (Erstellen, Veröffentlichen, Packen eines Projekts usw.). Sie können sich entweder mithilfe des Hilfebildschirms des Befehls (mit `dotnet <command> --help`) oder der Dokumentation auf dieser Website mit dem Verhalten der Befehle vertraut machen.

Hinsichtlich der Ausführung verwenden die CLI-Befehle ihre Parameter und erstellen einen Aufruf an „rohes“ MSBuild, woraufhin das Modul die benötigten Eigenschaften festlegt und das gewünschte Ziel ausführt. Um dies besser zu veranschaulichen, betrachten Sie den folgenden Befehl:

   ```dotnetcli
   dotnet publish -o pub -c Release
   ```

Mit diesem Befehl wird eine Anwendung im Ordner `pub` mithilfe der Konfiguration „Release“ veröffentlicht. Intern wird dieser Befehl in den folgenden MSBuild-Aufruf übersetzt:

   ```dotnetcli
   dotnet msbuild -t:Publish -p:OutputPath=pub -p:Configuration=Release
   ```

Relevante Ausnahmen für diese Regel sind die Befehle `new` und `run`. Sie wurden nicht als MSBuild-Ziele implementiert.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
