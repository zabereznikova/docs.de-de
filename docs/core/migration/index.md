---
title: .NET Core-Migration über „project.json“
description: Erfahren Sie, wie Sie ein älteres .NET Core-Projekt mithilfe von „project.json“ migrieren.
ms.date: 07/19/2017
ms.openlocfilehash: 0d4190a02389089a888d8b52dd8e7c412636b575
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538249"
---
# <a name="migrating-net-core-projects-from-projectjson"></a>Migrieren von .NET Core-Projekten über „project.json“

In diesem Dokument werden die folgenden drei Migrationsszenarien für .NET Core-Projekte behandelt:

1. [Migration von einem gültigen neuesten Schema von *project.json* zu *csproj*](#migration-from-projectjson-to-csproj)
2. [Migration von DNX zu csproj](#migration-from-dnx-to-csproj)
3. [Migration von RC3 und früheren .NET Core csproj-Projekten in das endgültige Format](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

Dieses Dokument gilt nur für ältere .NET Core-Projekte, die „project.json“ verwenden. Die hier genannten Informationen gelten nicht für die Migration von .NET Framework zu .NET Core.

## <a name="migration-from-projectjson-to-csproj"></a>Migration von project.json zu csproj

Die Migration von *project.json* zu *csproj* kann mithilfe einer der folgenden Methoden erfolgen:

- [Visual Studio](#visual-studio)
- [dotnet migrate-Befehlszeilentool](#dotnet-migrate)

Beide Methoden verwenden die gleiche zugrunde liegende Engine, um die Projekte zu migrieren, sodass die Ergebnisse bei beiden gleich sind. In den meisten Fällen genügt eine der folgenden beiden Methoden zum Migrieren von *project.json* zu *CSPROJ*-Dateien, und es ist keine weitere manuelle Bearbeitung der Projektdatei erforderlich. Die resultierende *.csproj*-Datei erhält denselben Namen wie das Verzeichnis, in dem sie enthalten ist.

### <a name="visual-studio"></a>Visual Studio

Wenn Sie eine *XPROJ*-Datei oder eine Projektmappendatei öffnen, die auf *XPROJ*-Dateien in Visual Studio 2017 oder Visual Studio 2019 Version 16.2 oder früher verweist, wird das Dialogfeld **Unidirektionales Upgrade** angezeigt. Das Dialogfeld zeigt die Projekte, die migriert werden sollen. Wenn Sie eine Projektmappendatei öffnen, werden alle Projekte aufgeführt, die in der Projektmappendatei angegeben sind. Überprüfen Sie die Liste der Projekte, die migriert werden sollen, und wählen Sie **OK**.

![Unidirektionales Upgrade-Dialogfeld mit der Liste der zu migrierenden Projekte](media/one-way-upgrade.jpg)

Die ausgewählten Projekte werden von Visual Studio automatisch migriert. Wenn Sie bei der Migration einer Projektmappe nicht alle Projekte auswählen, wird das gleiche Dialogfeld angezeigt, und Sie werden aufgefordert, für die übrigen Projekte aus dieser Projektmappe ein Upgrade auszuführen. Nach dem Migrieren des Projekts können Sie dessen Inhalte anzeigen und ändern, indem Sie im Fenster **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt klicken und anschließend mit der linken Maustaste auf **Edit \<project name>.csproj** (<Projektname>.csproj bearbeiten).

Dateien, die migriert wurden (*project.json*, *global.json*, die *XPROJ*-Datei und die Projektmappendatei), werden in einen *Sicherungsordner* verschoben. Für die migrierte Projektmappendatei wird ein Upgrade auf Visual Studio 2017 oder Visual Studio 2019 durchgeführt, und Sie können diese Projektmappe nicht mehr in Visual Studio 2015 oder früheren Versionen öffnen. Eine Datei namens *UpgradeLog.htm*, die einen Migrationsbericht enthält, wird ebenfalls gespeichert und automatisch geöffnet.

> [!IMPORTANT]
> In Visual Studio 2019 Version 16.3 und höher können Sie ein *XPROJ*-Datei nicht laden oder migrieren. Zusätzlich ist in Visual Studio 2015 die Funktion zum Migrieren einer *XPROJ*-Datei nicht verfügbar. Wenn Sie eine dieser beiden Visual Studio-Versionen verwenden, installieren Sie entweder die passende Visual Studio-Version, oder verwenden Sie das Befehlszeilenmigrationstool, das als nächstes erklärt wird.

### <a name="dotnet-migrate"></a>dotnet migrate

Im Befehlszeilenszenario können Sie den Befehl [`dotnet migrate`](../tools/dotnet-migrate.md) verwenden. Dabei werden ein Projekt, eine Projektmappe oder eine Reihe von Ordnern in dieser Reihenfolge migriert, je nachdem ob sie gefunden wurden. Wenn Sie ein Projekt migrieren, werden das Projekt und alle zugehörigen Abhängigkeiten migriert.

Dateien, die migriert wurden (*project.json*, *global.json* und *XPROJ*-Dateien), werden in einen *Sicherungsordner* verschoben.

> [!NOTE]
> Bei Verwendung von Visual Studio Code ändert der Befehl `dotnet migrate` Visual Studio Code-spezifische Dateien wie z. B. *tasks.json* nicht. Diese Dateien müssen manuell geändert werden.
> Dies gilt auch, wenn Sie einen anderen Editor oder eine andere Integrierte Entwicklungsumgebung (IDE) als Visual Studio verwenden.

Einen Vergleich der Formate *project.json* und *csproj* finden Sie unter [Die Zuordnung zwischen project.json und csproj-Eigenschaften](../tools/project-json-to-csproj.md).

Wenn Sie folgende Fehlermeldung erhalten:

> „No executable found matching command dotnet-migrate“ (Keine ausführbare Datei gefunden, die mit dem Befehl dotnet-migrate übereinstimmt):

Führen Sie `dotnet --version` aus, um zu sehen, welche Version Sie verwenden. [`dotnet migrate`](../tools/dotnet-migrate.md) wurde in .NET Core SDK 1.0.0 eingeführt und in Version 3.0.100 entfernt.
Sie erhalten diese Fehlermeldung, wenn sich eine *global.json*-Datei im aktuellen oder übergeordneten Verzeichnis befindet und die angegebene `sdk`-Version außerhalb dieses Bereichs liegt.

## <a name="migration-from-dnx-to-csproj"></a>Migration von DNX zu csproj

Wenn Sie für die .NET Core-Entwicklung noch immer DNX verwenden, sollte der Migrationsvorgang in zwei Phasen erfolgen:

1. Verwenden Sie die [existing DNX migration guidance (Hinweise zur Migration von einer vorhandenen DNX)](from-dnx.md), um von DNX zu project-json-aktivierter CLI zu migrieren.
2. Führen Sie die Schritte aus dem vorherigen Abschnitt zum Migrieren von *project.json* zu *.csproj* aus.

> [!NOTE]
> DNX gilt seit der Preview 1-Version der .NET Core-CLI offiziell als veraltet.

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a>Migration von früheren .NET Core-csproj-Formaten zu RTM-csproj

Das .NET Core-csproj-Format ändert und entwickelt sich mit jeder neuen Vorabversion der Tools. Es gibt kein Tool, das die Projektdatei von früheren csproj-Versionen zur neuesten migriert, sodass Sie die Projektdatei manuell bearbeiten müssen. Die tatsächlichen Schritte hängen von der Version der Projektdatei ab, die Sie migrieren. Nachfolgend finden Sie einige zu berücksichtigenden Hinweise, die auf den Änderungen von Version zu Version basieren:

- Entfernen Sie die Tools-Version-Eigenschaft aus dem `<Project>`-Element, sofern vorhanden.
- Entfernen Sie den XML-Namespace (`xmlns`) aus dem `<Project>`-Element.
- Wenn es nicht vorhanden ist, fügen Sie das `Sdk`-Attribut dem `<Project>`-Element hinzu, und legen Sie es auf `Microsoft.NET.Sdk` oder `Microsoft.NET.Sdk.Web` fest. Dieses Attribut gibt an, dass das Projekt das SDK verwendet, das verwendet werden soll. `Microsoft.NET.Sdk.Web` wird für Webanwendungen verwendet.
- Entfernen Sie die Anweisungen `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` und `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` vom oberen und unteren Rand des Projekts. Diese Importanweisungen werden durch das SDK impliziert, daher müssen Sie nicht im Projekt enthalten sein.
- Wenn Ihr Projekt `Microsoft.NETCore.App`- oder `NETStandard.Library` `<PackageReference>`-Elemente enthält, sollten Sie diese entfernen. Diese Paketverweise werden [durch das SDK impliziert](../tools/csproj.md).
- Entfernen Sie das `Microsoft.NET.Sdk` `<PackageReference>`-Element, sofern vorhanden. Die SDK-Referenz kommt durch das `Sdk`-Attribut auf dem `<Project>`-Element.
- Entfernen Sie die [Globs](https://en.wikipedia.org/wiki/Glob_(programming)), die [durch das SDK impliziert](../project-sdk/overview.md#default-compilation-includes) werden. Wenn diese Globs im Projekt bleiben, führt dies zu einem Fehler beim Erstellen, da Compile-Elemente dupliziert werden.

Nach diesen Schritten sollte das Projekt mit dem RTM .NET Core-csproj-Format vollständig kompatibel sein.

Beispiele für vor und nach der Migration vom alten csproj-Format zum neuen finden Sie im Artikel [Updating Visual Studio 2017 RC – .NET Core Tooling improvements (Aktualisieren von Visual Studio 2017 RC – Verbesserungen der .NET Core-Tools)](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/) im .NET-Blog.

## <a name="see-also"></a>Weitere Informationen

- [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
