---
title: dotnet-Befehl
description: Erfahren Sie mehr über den dotnet-Befehl (den generischen Treiber für die .NET Core-CLI) und dessen Verwendung.
ms.date: 06/04/2018
ms.openlocfilehash: 7674529980623caa2291987bdeba52f50ce2fc2c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920550"
---
# <a name="dotnet-command"></a>dotnet-Befehl

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet`: Ein Tool für das Verwalten von .NET-Quellcode und Binärdateien.

## <a name="synopsis"></a>Übersicht

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a>Beschreibung

`dotnet` ist ein Tool für das Verwalten von .NET-Quellcode und Binärdateien. Es stellt Befehle zur Verfügung, die bestimmte Aufgaben erfüllen, z.B. [`dotnet build`](dotnet-build.md) und [`dotnet run`](dotnet-run.md). Jeder Befehl definiert seine eigenen Argumente. Geben Sie nach jedem Befehl `--help` ein, um auf eine kurze Hilfsdokumentation zuzugreifen.

`dotnet` kann zum Ausführen von Anwendungen verwendet werden, indem eine Anwendungs-DLL angegeben wird, z.B. `dotnet myapp.dll`. Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).

## <a name="options"></a>Optionen

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--additional-deps <PATH>`

Pfad zu einer zusätzlichen *.deps.json*-Datei.

`--additionalprobingpath <PATH>`

Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

`--depsfile`

Pfad zu einer *deps.json*-Datei.

Eine *deps.json*-Datei enthält eine Liste mit Abhängigkeiten, Kompilierungsabhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten. Weitere Informationen zu dieser Datei finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--fx-version <VERSION>`

Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.

`-h|--help`

Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`. `dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.

`--info`

Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.

`--list-runtimes`

Zeigt die installierten .NET Core-Runtimes an.

`--list-sdks`

Zeigt die installierten .NET Core-SDKs an.

`--roll-forward-on-no-candidate-fx <N>`

Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist. `N` kann Folgendes sein:

- `0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.
- `1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt. Dies ist das Standardverhalten.
- `2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.

 Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).

`--runtimeconfig`

Der Pfad zu einer *runtimeconfig.json*-Datei.

Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.

`--version`

Druckt die Version des verwendeten .NET Core-SDK aus.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--additional-deps <PATH>`

Pfad zu einer zusätzlichen *.deps.json*-Datei.

`--additionalprobingpath <PATH>`

Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

`--depsfile`

Pfad zu einer *deps.json*-Datei.

Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten. Weitere Informationen zu dieser Datei finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--fx-version <VERSION>`

Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.

`-h|--help`

Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`. `dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.

`--info`

Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.

`--roll-forward-on-no-candidate-fx`

 Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist. Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).

`--runtimeconfig`

Der Pfad zu einer *runtimeconfig.json*-Datei.

Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.

`--version`

Druckt die Version des verwendeten .NET Core-SDK aus.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

`--depsfile`

Pfad zu einer *deps.json*-Datei.

Eine *deps.json*-Datei enthält eine Liste mit (Kompilierungs-)Abhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten. Weitere Informationen zu dieser Datei finden Sie auf [GitHub unter Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

`-d|--diagnostics`

Ermöglicht die diagnostische Ausgabe.

`--fx-version <VERSION>`

Version der .NET Core-Runtime, die zum Ausführen der Anwendung verwendet werden soll.

`-h|--help`

Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`. `dotnet --help` gibt eine Liste der verfügbaren Befehle zurück.

`--info`

Gibt ausführliche Informationen über eine .NET Core-Installation und die Computerumgebung aus, z.B. das aktuelle Betriebssystem und den Commit-SHA für die .NET Core-Version.

`--runtimeconfig`

Der Pfad zu einer *runtimeconfig.json*-Datei.

Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md#runtimeconfigjson).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.

`--version`

Druckt die Version des verwendeten .NET Core-SDK aus.

---

## <a name="dotnet-commands"></a>dotnet-Befehle

### <a name="general"></a>Allgemein

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

| Befehl                                       | Funktion                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | Erstellt eine .NET Core-Anwendung.                                     |
| [dotnet build-server](dotnet-build-server.md) | Interagiert mit Servern, die von einem Build gestartet wurden.                          |
| [dotnet clean](dotnet-clean.md)               | Bereinigen von Buildausgaben.                                                |
| [dotnet help](dotnet-help.md)                 | Zeigt eine ausführlichere Onlinedokumentation für den Befehl.           |
| [dotnet migrate](dotnet-migrate.md)           | Migriert ein gültiges Preview 2-Projekt in ein .NET Core SDK 1.0-Projekt.  |
| [dotnet msbuild](dotnet-msbuild.md)           | Ermöglicht den Zugriff auf die MSBuild-Befehlszeile                        |
| [dotnet new](dotnet-new.md)                   | Initialisiert ein C#- oder F#-Projekt für eine bestimmte Vorlage.                |
| [dotnet pack](dotnet-pack.md)                 | Erstellt ein NuGet-Paket aus Ihrem Code.                               |
| [dotnet publish](dotnet-publish.md)           | Veröffentlicht eine .NET Framework-abhängige oder eigenständige Anwendung. |
| [dotnet restore](dotnet-restore.md)           | Stellt die Abhängigkeiten für eine bestimmte Anwendung wieder her.                  |
| [dotnet run](dotnet-run.md)                   | Führt die Anwendung aus der Quelle aus.                                   |
| [dotnet sln](dotnet-sln.md)                   | Optionen zum Hinzufügen, Entfernen und Listen von Projekten in einer Projektmappendatei.       |
| [dotnet store](dotnet-store.md)               | Speichert Assemblys im Laufzeitpaketspeicher.                     |
| [dotnet test](dotnet-test.md)                 | Führt Tests mit einem Test Runner aus.                                     |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

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
[dotnet add reference](dotnet-add-reference.md) | Fügt einen Projektverweis hinzu.
[dotnet list reference](dotnet-list-reference.md) | Listet Projektverweise auf.
[dotnet remove reference](dotnet-remove-reference.md) | Entfernt einen Projektverweis.

### <a name="nuget-packages"></a>NuGet-Pakete

Befehl | Funktion
--- | ---
[dotnet add package](dotnet-add-package.md) | Fügt ein NuGet-Paket hinzu.
[dotnet remove package](dotnet-remove-package.md) | Entfernt ein NuGet-Paket.

### <a name="nuget-commands"></a>NuGet-Befehle

Befehl | Funktion
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Löscht ein Paket vom Server oder hebt dessen Auflistung auf.
[dotnet nuget locals](dotnet-nuget-locals.md) | Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.
[dotnet nuget push](dotnet-nuget-push.md) | Überträgt ein Paket auf den Server und veröffentlicht es.

### <a name="global-tools-commands"></a>Befehle für globale Tools

[Globale .NET Core-Tools](global-tools.md) sind beginnend mit .NET Core SDK 2.1.300 verfügbar:

Befehl | Funktion
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Installiert ein Global Tool auf dem Computer.
[dotnet tool list](dotnet-tool-list.md) | Listet alle globalen Tools auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Deinstalliert ein Global-Tool von Ihrem Computer.
[dotnet tool update](dotnet-tool-update.md) | Aktualisiert ein Global Tool auf dem Computer.

### <a name="additional-tools"></a>Weitere Tools

Beginnend mit .NET Core SDK 2.1.300 steht eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET Core SDK zur Verfügung. Diese Tools werden in der folgenden Tabelle aufgeführt:

| Tool                                              | Funktion                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Erstellt und verwaltet Entwicklungszertifikate.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Entity Framework Core-Befehlszeilentools.                    |
| sql-cache                                         | SQL Server-Cache-Befehlszeilentools.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Verwaltet die Entwicklung von Benutzergeheimnissen.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern. |

Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.

## <a name="examples"></a>Beispiele

Erstellt eine neue .NET Core-Konsolenanwendung:

`dotnet new console`

Wiederherstellen von Abhängigkeiten für eine bestimmte Anwendung:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:

`dotnet build`

Führen Sie eine Anwendungs-DLL aus, z.B. `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Umgebungsvariablen

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`DOTNET_PACKAGES`

Der Ordner für globale Pakete. Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.

`DOTNET_SERVICING`

Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden. Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert). Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert). Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.

`DOTNET_MULTILEVEL_LOOKUP`

Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden. Wenn nicht, ist der Standardwert `true`. Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert). Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist. Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`DOTNET_PACKAGES`

Der Cache des primären Pakets. Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.

`DOTNET_SERVICING`

Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden. Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert). Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert). Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.

`DOTNET_MULTILEVEL_LOOKUP`

Gibt an, ob die .NET Core-Runtime, das freigegebene Framework oder das SDK vom globalen Speicherort aus aufgelöst werden. Wenn nicht, ist der Standardwert `true`. Wenn der Wert auf `false` festgelegt wird, wird nicht vom globalen Speicherort aus aufgelöst und es gibt isolierte .NET Core-Installationen (die Werte `0` oder `false` werden akzeptiert). Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`DOTNET_PACKAGES`

Der Cache des primären Pakets. Wenn er nicht festgelegt wird, wird standardmäßig `$HOME/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.

`DOTNET_SERVICING`

Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Gibt an, ob Daten zur Nutzung von .NET Core-Tools gesammelt und an Microsoft gesendet werden. Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert). Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert). Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.

---

## <a name="see-also"></a>Siehe auch

- [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [Konfigurationseinstellungen für die .NET Core-Runtime](../run-time-config/index.md)
