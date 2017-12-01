---
title: "dotnet-Befehl – .NET Core-CLI"
description: "Informationen zum dotnet-Befehl (generischer Treiber für die .NET Core CLI-Tools) und dessen Verwendung."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: bba8d77cda7538bf008dc0f510f9279d3c695c3d
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-command"></a>dotnet-Befehl

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet`: Allgemeiner Treiber für das Ausführen der Befehlszeilenbefehle.

## <a name="synopsis"></a>Übersicht

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbose] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [-v|--verbose] [--version]
```
---

## <a name="description"></a>Beschreibung

`dotnet` ist ein generischer Treiber für die Befehlszeilenschnittstellen-Toolkette (CLI). Bietet bei eigenständigem Aufruf kurze Anweisungen.

Jede bestimmte Funktion ist als Befehl implementiert. Um die Funktion zu verwenden, wird der Befehl nach `dotnet` angegeben, wie z.B. [`dotnet build`](dotnet-build.md). Alle Argumente nach dem Befehl sind die eigenen Argumente.

Nur bei [Framework-abhängigen Apps](../deploying/index.md) wird `dotnet` als eigenständiger Befehl verwendet. Geben Sie eine Anwendungs-DLL nach dem Verb `dotnet` an, um die Anwendung auszuführen (zum Beispiel `dotnet myapp.dll`).

## <a name="options"></a>Optionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--additionaldeps <PATH>`

Pfad zur zusätzlichen *deps.json* Datei.

`--additionalprobingpath <PATH>`

Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--fx-version <VERSION>`

Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl. Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.

`--info`

Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.

`--roll-forward-on-no-candidate-fx`

 Führt ein Rollforward auf ein geteiltes Framework ohne Kandidaten durch.

`-v|--verbose`

Aktiviert die ausführliche Ausgabe.

`--version`

Druckt die Version des verwendeten .NET Core-SDK aus.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--fx-version <VERSION>`

Version der installierten .NET Core-Laufzeit, die für die Ausführung der Anwendung verwendet werden soll.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl. Bei Verwendung mit `dotnet` wird auch eine Liste der verfügbaren Befehle gedruckt.

`--info`

Druckt nähere Informationen zu den CLI-Tools und der Umgebung, z.B. das aktuelle Betriebssystem, den Commit-SHA für die Version und weitere Informationen.

`-v|--verbose`

Aktiviert die ausführliche Ausgabe.

`--version`

Druckt die Version des verwendeten .NET Core-SDK aus.

---

## <a name="dotnet-commands"></a>dotnet-Befehle

### <a name="general"></a>Allgemein

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

| Befehl                             | Funktion                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Erstellt eine .NET Core-Anwendung.                                     |
| [dotnet clean](dotnet-clean.md)     | Bereinigen von Buildausgaben.                                              |
| [dotnet help](dotnet-help.md)       | Zeigt eine ausführlichere Onlinedokumentation für den Befehl.           |
| [dotnet migrate](dotnet-migrate.md) | Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.  |
| [dotnet msbuild](dotnet-msbuild.md) | Ermöglicht den Zugriff auf die MSBuild-Befehlszeile                        |
| [dotnet new](dotnet-new.md)         | Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.                |
| [dotnet pack](dotnet-pack.md)       | Erstellt ein NuGet-Paket aus Ihrem Code.                               |
| [dotnet publish](dotnet-publish.md) | Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung. |
| [dotnet restore](dotnet-restore.md) | Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.                  |
| [dotnet run](dotnet-run.md)         | Führt die Anwendung aus der Quelle aus.                                   |
| [dotnet sln](dotnet-sln.md)         | Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.       |
| [dotnet store](dotnet-store.md)     | Speichert Assemblys im Laufzeitpaketspeicher.                     |
| [dotnet test](dotnet-test.md)       | Führt Tests mit einem Test Runner aus.                                     |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

| Befehl                             | Funktion                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Erstellt eine .NET Core-Anwendung.                                     |
| [dotnet clean](dotnet-clean.md)     | Bereinigen von Buildausgaben.                                              |
| [dotnet migrate](dotnet-migrate.md) | Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.  |
| [dotnet msbuild](dotnet-msbuild.md) | Ermöglicht den Zugriff auf die MSBuild-Befehlszeile                        |
| [dotnet new](dotnet-new.md)         | Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.                |
| [dotnet pack](dotnet-pack.md)       | Erstellt ein NuGet-Paket aus Ihrem Code.                               |
| [dotnet publish](dotnet-publish.md) | Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung. |
| [dotnet restore](dotnet-restore.md) | Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.                  |
| [dotnet run](dotnet-run.md)         | Führt die Anwendung aus der Quelle aus.                                   |
| [dotnet sln](dotnet-sln.md)         | Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.       |
| [dotnet test](dotnet-test.md)       | Führt Tests mit einem Test Runner aus.                                     |

---

### <a name="project-references"></a>Projektverweise

Befehl | Funktion
--- | ---
[dotnet add reference](dotnet-add-reference.md) | Projektverweis hinzufügen.
[dotnet list reference](dotnet-list-reference.md) | Projektverweise auflisten.
[dotnet remove reference](dotnet-remove-reference.md) | Einen Projektverweis entfernen.

### <a name="nuget-packages"></a>NuGet-Pakete

Befehl | Funktion
--- | ---
[dotnet add package](dotnet-add-package.md) | Ein NuGet-Paket hinzufügen.
[dotnet remove package](dotnet-remove-package.md) | Ein NuGet-Paket entfernen.

### <a name="nuget-commands"></a>NuGet-Befehle

Befehl | Funktion
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Löscht ein Paket vom Server oder hebt dessen Auflistung auf.
[dotnet nuget locals](dotnet-nuget-locals.md) | Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.
[dotnet nuget push](dotnet-nuget-push.md) | Überträgt ein Paket auf den Server und veröffentlicht es.

## <a name="examples"></a>Beispiele

Initialisieren einer .NET Core-Konsolenanwendung, die kompiliert und ausgeführt werden kann:

`dotnet new console`

Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

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
