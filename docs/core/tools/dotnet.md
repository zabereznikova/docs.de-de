---
title: "Befehl „dotnet“ – .NET Core-CLI | Microsoft-Dokumentation"
description: "Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung."
keywords: dotnet, CLI, CLI-Befehle, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/20/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 256e468e-eaaa-4715-b5fb-8cbddcf80e69
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: a470403e703ffb55de3d91cd5334c09bf11be06d
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-command"></a>dotnet-Befehl

## <a name="name"></a>Name

`dotnet`: Allgemeiner Treiber für das Ausführen der Befehlszeilenbefehle.

## <a name="synopsis"></a>Übersicht

`dotnet [command] [arguments] [--version] [--info] [-d|--diagnostics] [-v|--verbose] [--fx-version] [--additionalprobingpath] [-h|--help]`

## <a name="description"></a>Beschreibung

`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI). Bietet bei eigenständigem Aufruf kurze Anweisungen.

Jede bestimmte Funktion ist als Befehl implementiert. Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md). Alle Argumente nach dem Befehl sind die eigenen Argumente.

Nur bei [Framework-abhängigen Apps](../app-types.md) wird `dotnet` als eigenständiger Befehl verwendet. Geben Sie eine Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen (zum Beispiel `dotnet myapp.dll`).

## <a name="options"></a>Optionen

`-v|--verbose`

Aktiviert die ausführliche Ausgabe.

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--fx-version <VERSION>`

Version des installierten freigegebenen Frameworks, die für die Ausführung der Anwendung verwendet werden soll.

`--additionalprobingpath <PATH>`

Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

`--version`

Druckt die Version der CLI-Tools.

`--info`

Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl. Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.

## <a name="dotnet-commands"></a>dotnet-Befehle

### <a name="general"></a>Allgemein

Befehl | Funktion
--- | ---
[dotnet-build](dotnet-build.md) | Erstellt eine .NET Core-Anwendung.
[dotnet-clean](dotnet-clean.md) | Bereinigen Sie Buildausgabe(n).
[dotnet-migrate](dotnet-migrate.md) | Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.
[dotnet-msbuild](dotnet-msbuild.md) | Ermöglicht den Zugriff auf die MSBuild-Befehlszeile
[dotnet-new](dotnet-new.md) | Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.
[dotnet-pack](dotnet-pack.md) | Erstellt ein NuGet-Paket aus Ihrem Code.
[dotnet-publish](dotnet-publish.md) | Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung.
[dotnet-restore](dotnet-restore.md) | Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.
[dotnet-run](dotnet-run.md) | Führt die Anwendung aus der Quelle aus.
[dotnet-sln](dotnet-sln.md) | Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.
[dotnet-test](dotnet-test.md) | Führt Tests mit einem Test Runner aus.

### <a name="project-references"></a>Projektverweise

Befehl | Funktion
--- | ---
[dotnet-add-Verweis](dotnet-add-reference.md) | Projektverweis hinzufügen.
[dotnet-list-Verweis](dotnet-list-reference.md) | Projektverweise auflisten.
[dotnet-remove-Verweis](dotnet-remove-reference.md) | Einen Projektverweis entfernen.

### <a name="nuget-packages"></a>NuGet-Pakete

Befehl | Funktion
--- | ---
[dotnet-add-Paket](dotnet-add-package.md) | Ein NuGet-Paket hinzufügen.
[dotnet-remove-Paket](dotnet-remove-package.md) | Ein NuGet-Paket entfernen.

### <a name="nuget-commands"></a>NuGet-Befehle

Befehl | Funktion
--- | ---
[dotnet-nuget delete](dotnet-nuget-delete.md) | Löscht ein Paket vom Server oder hebt dessen Auflistung auf.
[dotnet-nuget locals](dotnet-nuget-locals.md) | Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.
[dotnet-nuget push](dotnet-nuget-push.md) | Überträgt ein Paket auf den Server und veröffentlicht es.

## <a name="examples"></a>Beispiele

Initialisieren einer .NET Core-Konsolenanwendung, die kompiliert und ausgeführt werden kann:

`dotnet new console`

Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:

`dotnet restore`

Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:

`dotnet build`

Führen Sie eine Framework-abhängige Anwendung mit dem Namen `myapp.dll` aus:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Umgebungsvariablen

`DOTNET_PACKAGES`

Der Cache des primären Pakets. Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%HOME%\NuGet\Packages` unter Windows verwendet.

`DOTNET_SERVICING`

Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden. Legen Sie sie auf `true` fest, um die Telemetriefunktion zu deaktivieren (Werte `true`, `1` oder `yes` werden akzeptiert); legen Sie sie andernfalls auf `false` fest, um die Telemetriefunktionen zu aktivieren (Werte `false`, `0` oder `no` werden akzeptiert). Wenn sie nicht festgelegt wird, ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.

