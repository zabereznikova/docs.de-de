---
title: Befehl dotnet | Microsoft-Dokumentation
description: "Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung."
keywords: dotnet, CLI, CLI-Befehle, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 256e468e-eaaa-4715-b5fb-8cbddcf80e69
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: e3eedff7d98245bd63d758236840568eabd05445
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-command"></a>dotnet-Befehl

## <a name="name"></a>Name

`dotnet`: Allgemeiner Treiber für das Ausführen der Befehlszeilenbefehlen

## <a name="synopsis"></a>Übersicht

```
dotnet [command] [arguments] [--version] [--info] [-d|--diagnostics] [-v|--verbose]
dotnet [-h|--help]
```

## <a name="description"></a>Beschreibung

`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI). Allein aufgerufen gibt er kurze Anweisungen.

Jede bestimmte Funktion ist als Befehl implementiert. Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md). Alle Argumente nach dem Befehl sind die eigenen Argumente.

Nur bei portablen Apps wird `dotnet` als ein eigenständiger Befehl verwendet. Geben Sie einfach eine portable Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen.

## <a name="options"></a>Optionen

`-v|--verbose`

Aktiviert die ausführliche Ausgabe.

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--version`

Druckt die Version der CLI-Tools.

`--info`

Druckt weitere Informationen zu den CLI-Tools, z.B. das aktuelle Betriebssystem, SHA für die Version committen, usw.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl. Bei Verwendung nur mit `dotnet`, wird auch eine Liste der verfügbaren Befehle gedruckt.

## <a name="dotnet-commands"></a>dotnet-Befehle

Die folgenden Befehle sind für dotnet vorhanden:

* [dotnet-new](dotnet-new.md)
  * Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.
* [dotnet-restore](dotnet-restore.md)
  * Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.
* [dotnet-build](dotnet-build.md)
  * Erstellt eine .NET Core-Anwendung.
* [dotnet-publish](dotnet-publish.md)
  * Veröffentlicht eine portable oder eigenständige .NET-Anwendung.
* [dotnet-run](dotnet-run.md)
  * Führt die Anwendung aus der Quelle aus.
* [dotnet-test](dotnet-test.md)
  * Führt Tests mit einem Testprogramm durch, das in der Datei „project.json“ angegeben ist.
* [dotnet-pack](dotnet-pack.md)
  * Erstellt ein NuGet-Paket aus Ihrem Code.
* [dotnet-migrate](dotnet-migrate.md)
  * Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.
* [dotnet-msbuild](dotnet-msbuild.md)
  * Ermöglicht den Zugriff auf die MSBuild-Befehlszeile
* [dotnet-clean](dotnet-clean.md)
  * Bereinigen Sie Buildausgabe(n).
* [dotnet-sln](dotnet-sln.md)
  * Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.
* Befehle zur Projektänderung
  * Verweise: Hinzufügen, Entfernen und Listen von Projekt-zu-Projekt-Verweisen.
    * [dotnet-add-Verweis](dotnet-add-reference.md)
    * [dotnet-remove-Verweis](dotnet-remove-reference.md)
    * [dotnet-list-Verweis](dotnet-list-reference.md)
  * Pakete: Hinzufügen und Entfernen von NuGet-Paketen in einem Projekt.
    * [dotnet-add-Paket](dotnet-add-package.md)
    * [dotnet-remove-Paket](dotnet-remove-package.md)

## <a name="examples"></a>Beispiele

Initialisieren einer .NET Core-Konsolenanwendung, die kompiliert und ausgeführt werden kann:

`dotnet new console`

Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:

`dotnet restore`

Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:

`dotnet build`

Ausführen einer portablen App namens `myapp.dll`: `dotnet myapp.dll`

## <a name="environment"></a>Umgebung

`DOTNET_PACKAGES`

Der Cache des primären Pakets. Wenn nichts festgelegt ist, wird standardmäßig „$HOME/.nuget/packages unter Unix oder %HOME%\NuGet\Packages“ unter Windows ausgewählt.

`DOTNET_SERVICING`

Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden. `true`zum Deaktivieren der Telemetriefunktion (Werte „true“, „1“ oder „yes“ akzeptiert); andernfalls `false` (Werte „false“, „0“ oder „no“ akzeptiert). Wenn nicht festgelegt, gilt standardmäßig `false`, d.h. die Telemetriefunktion ist aktiviert.
