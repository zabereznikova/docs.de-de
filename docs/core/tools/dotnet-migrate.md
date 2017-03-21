---
title: Befehl dotnet-migrate | Microsoft-Dokumentation
description: "Der dotnet-migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-migrate, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: b7da4df5319e7c17900b9c093347e8a17045a6a3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Name 
dotnet-migrate – Migriert ein .NET Core-Projekt von Preview 2 in ein .NET Core-Projekt von SDK 1.0.

## <a name="synopsis"></a>Übersicht

```
dotnet migrate [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [<arguments>]
dotnet migrate [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet migrate`-Befehl migriert ein gültiges *project.json*-basiertes Projekt von Preview 2 in ein gültiges *csproj*-Projekt von .NET Core SDK 1.0. 

Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält. Dieses Verhalten kann mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert werden. 

Die Migration kann für Folgendes ausgeführt werden:

* Ein einzelnes Projekt durch Angabe der zu migrierenden *project.json*-Datei
* Alle Verzeichnisse, die in der *global.json*-Datei angegeben sind, indem ein Pfad zur *global.json*-Datei übergeben wird
* Rekursiv für alle Unterverzeichnisse im angegebenen Verzeichnis 

Der Migrationsbefehl speichert die migrierte *project.json*-Datei in einem `backup`-Verzeichnis, das erstellt wird, falls es noch nicht vorhanden ist. Dies kann mithilfe der `--skip-backup`-Option überschrieben werden. 

Standardmäßig gibt der Migrationsvorgang den Status der Migration in die Standardausgabe (STDOUT) aus. Bei Verwendung der `--report-file`-Option wird die Ausgabe auch in einer Datei gespeichert, die Sie angeben. 

Der `dotnet migrate`-Befehl unterstützt nur gültige *project.json*-Dateien von Preview 2. Dies bedeutet, dass damit keine alten DNX-Dateien oder *project.json*-Dateien von Preview 1 direkt in csproj migriert werden können. Sie müssen zunächst eine Migration in project.json-Dateien von Preview 2 und dann in csproj-Dateien ausführen. In Zukunft wird Unterstützung für Preview 1-Projekte hinzugefügt. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-t|--template-file <TEMPLATE_FILE>`

Für die Migration zu verwendende CSPROJ-Vorlagendatei. Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde. 

`-v|--sdk-package-version <VERSION>`

Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird. Der Standardwert ist die Version des SDK-Pakets in „dotnet-new“.

`-x|--xproj-file <FILE>`

Der Pfad zur XPROJ-Datei, die verwendet werden soll. Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.

`-s|--skip-project-references [Debug|Release]`

Die Migration von Projektverweisen wird übersprungen. Standardmäßig werden Projektverweise rekursiv migriert.

`-r|--report-file <REPORT_FILE>`

Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.

`--format-report-file-json <REPORT_FILE>`

Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.

`--skip-backup`

Das Verschieben der Dateien „project.json“, „global.json“ und „\*.xproj“ in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.

## <a name="examples"></a>Beispiele

Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:

`dotnet migrate`

Migrieren Sie alle Projekte, auf die die *global.json*-Datei verweist:

`dotnet migrate path/to/global.json`

Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten, und verwenden Sie eine bestimmte SDK-Version:

`dotnet migrate -s -v 1.0.0-preview4`
