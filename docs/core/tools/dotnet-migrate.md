---
title: "dotnet-migrate-Befehl – .NET Core-CLI"
description: "Der dotnet-migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-migrate, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e8491d69b2e0df7b3bd2741e34abdb9631777019
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Name

`dotnet-migrate`: Migriert ein .NET Core-Projekt von Preview 2 in ein .NET Core-Projekt von SDK 1.0.

## <a name="synopsis"></a>Übersicht

`dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet migrate`-Befehl migriert ein gültiges *project.json*-basiertes Projekt von Preview 2 in ein gültiges *csproj*-Projekt von .NET Core SDK 1.0. 

Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält. Dieses Verhalten ist mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert. 

Migration wird auf Folgendes ausgeführt:

* Ein einzelnes Projekt durch Angabe der zu migrierenden *project.json*-Datei.
* Alle Verzeichnisse, die in der *global.json*-Datei angegeben sind, indem ein Pfad zur *global.json*-Datei übergeben wird.
* Ein *solution.sln*-Datei, in dem die Projekte, auf die in der Projektmappe verwiesen wird, migriert werden.
* Rekursiv für alle Unterverzeichnisse im angegebenen Verzeichnis.

Der `dotnet migrate`-Befehl speichert die migrierte *project.json*-Datei in einem `backup`-Verzeichnis, das erstellt wird, falls das Verzeichnis noch nicht vorhanden ist. Das Verhalten wird mithilfe der `--skip-backup`-Option überschrieben. 

Standardmäßig gibt der Migrationsvorgang den Status der Migration in die Standardausgabe (STDOUT) aus. Bei Verwendung der `--report-file <REPORT_FILE>`-Option wird die Ausgabe in die angegebene Datei gespeichert. 

Der `dotnet migrate`-Befehl unterstützt nur gültige *project.json*-basiere Projekte von Preview 2. Dies bedeutet, dass Sie ihn nicht zum Migrieren von *project.json*-basierten Projekte von DNX oder Preview 1 direkt an MSBuild/csproj-Projekte verwenden können. Sie müssen zuerst das Projekt manuell auf ein *project.json*-basiertes Projekt von Preview 2 migrieren und anschließend den `dotnet migrate`-Befehl verwenden, um das Projekt zu migrieren.

## <a name="arguments"></a>Argumente

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

Der Pfad zu einem der Folgenden:

* eine *project.json*-Datei zum Migrieren.
* eine *global.json*-Datei wird die in *global.json* angegebenen Ordner migrieren.
* eine *solution.sln*-Datei wird die Projekte migrieren, auf die in der Projektmappe verwiesen wird.
* ein Verzeichnis zum Migrieren, das rekursiv nach *project.json*-Dateien suchen wird, um sie zu migrieren.

Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis gewählt.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-t|--template-file <TEMPLATE_FILE>`

Für die Migration zu verwendende CSPROJ-Vorlagendatei. Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde. 

`-v|--sdk-package-version <VERSION>`

Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird. Der Standardwert ist die Version des SDK in `dotnet new`.

`-x|--xproj-file <FILE>`

Der Pfad zur XPROJ-Datei, die verwendet werden soll. Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.

`-s|--skip-project-references [Debug|Release]`

Die Migration von Projektverweisen wird übersprungen. Standardmäßig werden Projektverweise rekursiv migriert.

`-r|--report-file <REPORT_FILE>`

Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.

`--format-report-file-json <REPORT_FILE>`

Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.

`--skip-backup`

Das Verschieben der Dateien *project.json*, *global.json* und *\*.xproj* in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.

## <a name="examples"></a>Beispiele

Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:

`dotnet migrate`

Migrieren Sie alle Projekte, die die *global.json*-Datei umfasst:

`dotnet migrate path/to/global.json`

Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten (P2P). Verwenden Sie außerdem eine bestimmte SDK-Version:

`dotnet migrate -s -v 1.0.0-preview4`

