---
title: Befehl „dotnet migrate“
description: Der dotnet migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten.
ms.date: 02/14/2020
ms.openlocfilehash: 2e7f9ae5a1d11c54280d914b04df761f0d5aff99
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284091"
---
# <a name="dotnet-migrate"></a>dotnet migrate

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK

## <a name="name"></a>name

`dotnet migrate`: migriert ein .NET Core-Projekt der Vorschauversion 2 in ein SDK-Projekt für .NET Core.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json <REPORT_FILE>]
    [-r|--report-file <REPORT_FILE>] [-s|--skip-project-references [Debug|Release]]
    [--skip-backup] [-t|--template-file <TEMPLATE_FILE>] [-v|--sdk-package-version]
    [-x|--xproj-file]

dotnet migrate -h|--help
```

## <a name="description"></a>Beschreibung

Dieser Befehl ist veraltet. Der `dotnet migrate`-Befehl ist im .NET Core 3.0 SDK und in neueren Versionen nicht mehr verfügbar. Er kann nur ein .NET Core-Projekt von Vorschau 2 zu einem .NET Core-Projekt der Version 1. x migrieren, was nicht mehr unterstützt wird.

Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält. Dieses Verhalten ist mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert.

Die Migration kann auf den folgenden Objekten ausgeführt werden:

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
* eine *global.json*-Datei. Die in *global.json* angegebenen Ordner werden migriert.
* eine *solution.sln*-Datei. Die in der Projektmappe referenzierten Projekte werden migriert.
* ein zu migrierendes Verzeichnis. Sucht rekursiv nach *project.json*-Dateien, um diese im angegebenen Verzeichnis zu migrieren.

Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis gewählt.

## <a name="options"></a>Optionen

`--format-report-file-json <REPORT_FILE>`

Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-r|--report-file <REPORT_FILE>`

Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.

`-s|--skip-project-references [Debug|Release]`

Die Migration von Projektverweisen wird übersprungen. Standardmäßig werden Projektverweise rekursiv migriert.

`--skip-backup`

Das Verschieben der Dateien *project.json*, *global.json* und *\*.xproj* in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.

`-t|--template-file <TEMPLATE_FILE>`

Für die Migration zu verwendende CSPROJ-Vorlagendatei. Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde.

`-v|--sdk-package-version <VERSION>`

Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird. Der Standardwert ist die Version des SDK in `dotnet new`.

`-x|--xproj-file <FILE>`

Der Pfad zur XPROJ-Datei, die verwendet werden soll. Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.

## <a name="examples"></a>Beispiele

Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:

`dotnet migrate`

Migrieren Sie alle Projekte, die die *global.json*-Datei umfasst:

`dotnet migrate path/to/global.json`

Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten (P2P). Verwenden Sie außerdem eine bestimmte SDK-Version:

`dotnet migrate -s -v 1.0.0-preview4`
