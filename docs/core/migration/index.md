---
title: .NET Core-Migration über „project.json“
description: Erfahren Sie, wie Sie ein älteres .NET Core-Projekt mithilfe von „project.json“ migrieren.
author: blackdwarf
ms.date: 07/19/2017
ms.custom: seodec18
ms.openlocfilehash: 40a0aaf9d687a580b83e11811effad458f708a85
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170690"
---
# <a name="migrating-net-core-projects-from-projectjson"></a>Migrieren von .NET Core-Projekten über „project.json“

Dieses Dokument behandelt Migrationsszenarios für .NET Core-Projekte und die folgenden drei Migrationsszenarios:

1. [Migration von einem gültigen neuesten Schema von *project.json* zu *csproj*](#migration-from-projectjson-to-csproj)
2. [Migration von DNX zu csproj](#migration-from-dnx-to-csproj)
3. [Migration von RC3 und früheren .NET Core csproj-Projekten in das endgültige Format](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

Dieses Dokument gilt nur für ältere .NET Core-Projekte, die noch „project.json“ verwenden. Die hier genannten Informationen gelten nicht für die Migration von .NET Framework zu .NET Core.

## <a name="migration-from-projectjson-to-csproj"></a>Migration von project.json zu csproj

Die Migration von *project.json* zu *csproj* kann mithilfe einer der folgenden Methoden erfolgen:

- [Visual Studio 2017](#visual-studio-2017)
- [dotnet migrate-Befehlszeilentool](#dotnet-migrate)

Beide Methoden verwenden die gleiche zugrunde liegende Engine, um die Projekte zu migrieren, sodass die Ergebnisse bei beiden gleich sind. In den meisten Fällen genügt eine der folgenden beiden Methoden zum Migrieren von *project.json* zu *csproj* und es ist keine weitere manuelle Bearbeitung der Projektdatei erforderlich. Die resultierende *.csproj*-Datei erhält denselben Namen wie das Verzeichnis, in dem sie enthalten ist.

### <a name="visual-studio-2017"></a>Visual Studio 2017

Beim Öffnen einer *.xproj*-Datei oder einer Projektmappendatei, die auf *.xproj*-Dateien verweist, wird das Dialogfeld **Unidirektionales Upgrade** angezeigt. Das Dialogfeld zeigt die Projekte, die migriert werden sollen.
Wenn Sie eine Projektmappendatei öffnen, werden alle Projekte aufgeführt, die in der Projektmappendatei angegeben sind. Überprüfen Sie die Liste der Projekte, die migriert werden sollen, und wählen Sie **OK**.

![Unidirektionales Upgrade-Dialogfeld mit der Liste der zu migrierenden Projekte](media/one-way-upgrade.jpg)

Visual Studio wird die ausgewählten Projekte automatisch migrieren. Wenn Sie bei der Migration einer Projektmappe nicht alle Projekte auswählen, erscheint das gleiche Dialogfeld und Sie werden aufgefordert, die übrigen Projekte der Projektmappe upzugraden. Nachdem das Projekt migriert wurde, können Sie sich seine Inhalt anzeigen lassen und diese ändern, indem Sie mit der rechten Maustaste auf das Projekt im Fenster **Projektmappen-Explorer** und anschließend auf **Bearbeiten \<Projektname>.csproj** klicken.

Dateien, die migriert wurden (*project.json*, *global.json*, *.xproj* und Projektmappendatei), werden in einen *Sicherung*-Ordner verschoben. Die migrierte Projektmappendatei wird auf Visual Studio 2017 upgegradet und es wird nicht mehr möglich sein, diese Projektmappendatei in früheren Versionen von Visual Studio zu öffnen.
Eine Datei namens *UpgradeLog.htm*, die einen Migrationsbericht enthält, wird ebenfalls gespeichert und automatisch geöffnet.

> [!IMPORTANT]
> Die neuen Tools sind nicht in Visual Studio 2015 verfügbar und Sie können Ihre Projekte mit dieser Version von Visual Studio nicht migrieren.

### <a name="dotnet-migrate"></a>dotnet migrate

Im Befehlszeilenszenario können Sie den Befehl [`dotnet migrate`](../tools/dotnet-migrate.md) verwenden. Dadurch werden ein Projekt, eine Projektmappe oder eine Reihe von Ordnern in dieser Reihenfolge migriert, je nachdem ob sie gefunden wurden.
Wenn Sie ein Projekt migrieren, werden das Projekt und alle zugehörigen Abhängigkeiten migriert.

Dateien, die migriert wurden (*project.json*, *global.json* und *.xproj*), werden in einen *Sicherung*-Ordner verschoben.

> [!NOTE]
> Bei Verwendung von Visual Studio Code ändert der Befehl `dotnet migrate` Visual Studio Code-spezifische Dateien wie z.B. `tasks.json` nicht. Diese Dateien müssen manuell geändert werden.
> Dies gilt auch, wenn Sie Project Ryder oder einen anderen Editor oder eine andere Integrierte Entwicklungsumgebung (IDE) als Visual Studio verwenden.

Einen Vergleich der Formate project.json und csproj finden Sie unter [Die Zuordnung zwischen project.json und csproj-Eigenschaften](../tools/project-json-to-csproj.md).

### <a name="common-issues"></a>Häufig auftretende Probleme

- Wenn Sie folgende Fehlermeldung erhalten: „No executable found matching command dotnet-migrate“ (Keine ausführbare Datei gefunden, die mit dem Befehl dotnet-migrate übereinstimmt):

Führen Sie `dotnet --version` aus, um zu sehen, welche Version Sie verwenden. [`dotnet migrate`](../tools/dotnet-migrate.md) erfordert .NET Core-CLI RC3 oder höher.
Sie erhalten diese Fehlermeldung, wenn sich eine *global.json*-Datei im aktuellen oder übergeordneten Verzeichnis befindet und die `sdk`-Version auf eine ältere Version festgelegt ist.

## <a name="migration-from-dnx-to-csproj"></a>Migration von DNX zu csproj

Wenn Sie für die .NET Core-Entwicklung noch immer DNX verwenden, sollte der Migrationsvorgang in zwei Phasen erfolgen:

1. Verwenden Sie die [existing DNX migration guidance (Hinweise zur Migration von einer vorhandenen DNX)](from-dnx.md), um von DNX zu project-json-aktivierter CLI zu migrieren.
2. Führen Sie die Schritte aus dem vorherigen Abschnitt zum Migrieren von *project.json* zu *.csproj* aus.  

> [!NOTE]
> DNX gilt seit der Preview 1-Version der .NET Core-CLI offiziell als veraltet.

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a>Migration von früheren .NET Core-csproj-Formaten zu RTM-csproj

Das .NET Core-csproj-Format ändert und entwickelt sich mit jeder neuen Vorabversion der Tools. Es gibt kein Tool, das die Projektdatei von früheren csproj-Versionen zur neuesten migriert, sodass Sie die Projektdatei manuell bearbeiten müssen. Die tatsächlichen Schritte hängen von der Version der Projektdatei ab, die Sie migrieren. Nachfolgend finden Sie einige zu berücksichtigenden Hinweise, die auf den Änderungen von Version zu Version basieren:

* Entfernen Sie die Tools-Version-Eigenschaft aus dem `<Project>`-Element, sofern vorhanden.
* Entfernen Sie den XML-Namespace (`xmlns`) aus dem `<Project>`-Element.
* Wenn es nicht vorhanden ist, fügen Sie das `Sdk`-Attribut dem `<Project>`-Element hinzu, und legen Sie es auf `Microsoft.NET.Sdk` oder `Microsoft.NET.Sdk.Web` fest. Dieses Attribut gibt an, dass das Projekt das SDK verwendet, das verwendet werden soll. `Microsoft.NET.Sdk.Web` wird für Webanwendungen verwendet.
* Entfernen Sie die Anweisungen `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` und `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` vom oberen und unteren Rand des Projekts. Diese Importanweisungen werden durch das SDK impliziert, daher müssen Sie nicht im Projekt enthalten sein.
* Wenn Ihr Projekt `Microsoft.NETCore.App`- oder `NETStandard.Library`-`<PackageReference>`-Elemente enthält, sollten Sie diese entfernen. Diese Paketverweise werden [durch das SDK impliziert](https://aka.ms/sdkimplicitrefs).
* Entfernen Sie das `Microsoft.NET.Sdk`-`<PackageReference>`-Element, sofern vorhanden. Die SDK-Referenz kommt durch das `Sdk`-Attribut auf dem `<Project>`-Element.
* Entfernen Sie die [Globs](https://en.wikipedia.org/wiki/Glob_(programming)), die [durch das SDK impliziert](../tools/csproj.md#default-compilation-includes-in-net-core-projects) werden. Wenn diese Globs im Projekt bleiben, führt dies zu einem Fehler beim Erstellen, da Compile-Elemente dupliziert werden.

Nach diesen Schritten sollte das Projekt mit dem RTM .NET Core-csproj-Format vollständig kompatibel sein.

Beispiele für vor und nach der Migration vom alten csproj-Format zum neuen finden Sie im Artikel [Updating Visual Studio 2017 RC – .NET Core Tooling improvements (Aktualisieren von Visual Studio 2017 RC – Verbesserungen der .NET Core-Tools)](https://blogs.msdn.microsoft.com/dotnet/2016/12/12/updating-visual-studio-2017-rc-net-core-tooling-improvements/) im .NET-Blog.

## <a name="see-also"></a>Siehe auch

- [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
