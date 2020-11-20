---
title: dotnet-Befehl
description: In diesem Artikel erfahren Sie mehr über den dotnet-Befehl (den generischen Treiber für die .NET-CLI) und dessen Verwendung.
ms.date: 11/11/2020
ms.openlocfilehash: 7a0c8f2eb7ab407bd725db56cbf31da4689970e4
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634024"
---
# <a name="dotnet-command"></a>dotnet-Befehl

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet`: Der generische Treiber für die .NET-CLI

## <a name="synopsis"></a>Übersicht

So erhalten Sie Informationen über die verfügbaren Befehle und die Umgebung

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

So führen Sie einen Befehl aus (erfordert eine SDK-Installation)

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

So führen Sie eine Anwendung aus

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

`--roll-forward` ist seit .NET Core 3.x verfügbar. Verwenden Sie `--roll-forward-on-no-candidate-fx` für .NET Core 2.x.

## <a name="description"></a>Beschreibung

Der Befehl `dotnet` hat zwei Funktionen:

- Er stellt Befehle für die Arbeit mit .NET-Projekten bereit.

  Beispielsweise erstellt [`dotnet build`](dotnet-build.md) ein Projekt. Jeder Befehl definiert seine eigenen Optionen und Argumente. Alle Befehle unterstützen die Option `--help` zum Ausdrucken einer kurzen Dokumentation über die Verwendung des Befehls.

- Er führt .NET-Anwendungen aus.

  Sie geben den Pfad zu einer `.dll`-Datei einer Anwendung zur Ausführung der Anwendung an.  Das Ausführen der Anwendung bedeutet, den Einstiegspunkt zu finden und auszuführen. Im Falle von Konsolen-Apps ist dies die `Main`-Methode. Beispiel: `dotnet myapp.dll` führt die Anwendung `myapp` aus. Weitere Informationen über Bereitstellungsoptionen finden Sie unter [.NET-Anwendungsbereitstellung](../deploying/index.md).

## <a name="options"></a>Optionen

Es gibt verschiedene Optionen für `dotnet` allein, für die Ausführung eines Befehls und für die Ausführung einer Anwendung.

### <a name="options-for-dotnet-by-itself"></a>Optionen für dotnet

Die folgenden Optionen gelten für `dotnet` allein. Beispielsweise `dotnet --info`. Sie drucken Informationen über die Umgebung aus.

- **`--info`**

  Gibt ausführliche Informationen über eine .NET-Installation und die Computerumgebung aus, z. B. das aktuelle Betriebssystem und den Commit-SHA für die .NET-Version

- **`--version`**

  Gibt die Version des verwendeten .NET SDK aus

- **`--list-runtimes`**

  Gibt eine Liste der installierten .NET-Runtimes aus. Eine x86-Version des SDK listet nur x86-Runtimes auf, und eine x64-Version des SDK listet nur x64-Runtimes auf.

- **`--list-sdks`**

  Gibt eine Liste der installierten .NET SDKs aus

- **`-h|--help`**

  Druckt eine Liste der verfügbaren Befehle aus.

### <a name="sdk-options-for-running-a-command"></a>SDK-Optionen zum Ausführen eines Befehls

Die folgenden Optionen gelten für `dotnet` mit einem Befehl. Beispielsweise `dotnet build --help`.

- **`-d|--diagnostics`**

  Ermöglicht die diagnostische Ausgabe.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Nicht in jedem Befehl unterstützt. Auf der Seite der einzelnen Befehle finden Sie heraus, ob diese Option verfügbar ist.

- **`-h|--help`**

  Gibt Dokumentation für einen bestimmten Befehl aus, z.B. `dotnet build --help`.

- **`command options`**

  Jeder Befehl definiert Optionen, die für diesen Befehl spezifisch sind. Eine Liste der verfügbaren Optionen finden Sie auf einer speziellen Befehlsseite.

### <a name="runtime-options"></a>Laufzeitoptionen

Die folgenden Optionen sind verfügbar, wenn `dotnet` eine Anwendung ausführt. Beispielsweise `dotnet myapp.dll --roll-forward Major`.

- **`--additionalprobingpath <PATH>`**

  Pfad, der die Suchrichtlinie und die zu suchenden Assemblys enthält.

- **`--additional-deps <PATH>`**

  Pfad zu einer zusätzlichen *.deps.json*-Datei. Eine *deps.json*-Datei enthält eine Liste mit Abhängigkeiten, Kompilierungsabhängigkeiten und Versionsinformationen, die verwendet werden, um Assemblykonflikte zu bearbeiten. Weitere Informationen finden Sie auf GitHub unter [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

- **`--depsfile <PATH_TO_DEPSFILE>`**

  Pfad zur *deps.json*-Datei. Eine Datei mit Namen *deps.json* ist eine Konfigurationsdatei, die Informationen zu Abhängigkeiten enthält, die zum Ausführen der Anwendung erforderlich sind. Diese Datei wird vom .NET SDK generiert.

- **`--runtimeconfig`**

  Der Pfad zu einer *runtimeconfig.json*-Datei. Eine *runtimeconfig.json*-Datei ist eine Konfigurationsdatei mit Einstellungen für die Runtime. Weitere Informationen finden Sie unter [Konfigurationseinstellungen für die .NET-Runtime](../run-time-config/index.md#runtimeconfigjson).

- **`--roll-forward <SETTING>`** **Verfügbar ab .NET Core SDK 3.0.**

  Steuert, wie der Rollforward auf die App angewendet wird. `SETTING` kann einer der folgenden Werte sein. Wenn nichts anderes angegeben wird, wird als Standard `Minor` verwendet.

  - `LatestPatch`: Rollforward zur höchsten Patchversion. Dies deaktiviert ein Rollforward zur Nebenversion.
  - `Minor`: Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist. Wenn die angeforderte Nebenversion vorhanden ist, wird die LatestPatch-Richtlinie verwendet.
  - `Major`: Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist. Wenn die angeforderte Hauptversion vorhanden ist, wird die Minor-Richtlinie verwendet.
  - `LatestMinor`: Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist. Für Komponentenhostingszenarien vorgesehen.
  - `LatestMajor`: Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist. Für Komponentenhostingszenarien vorgesehen.
  - `Disable`: Kein Rollforward. Nur Binden an angegebene Version. Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt. Dieser Wert wird nur zu Testzwecken empfohlen.

  Mit Ausnahme von `Disable` wird für alle Einstellungen die höchste verfügbare Patchversion verwendet.

  Das Rollforwardverhalten kann auch in einer Projektdateieigenschaft, einer Runtime-Konfigurationsdateieigenschaft und einer Umgebungsvariablen konfiguriert werden. Weitere Informationen finden Sie unter [Runtimerollforward der Hauptversion](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).

- **`--roll-forward-on-no-candidate-fx <N>`** **Verfügbar im .NET Core 2.x SDK.**

  Definiert ein Verhalten, wenn das erforderliche freigegebene Framework nicht verfügbar ist. `N` kann Folgendes sein:

  - `0` - Das Ausführen von Rollforward ist auch für die Nebenversion deaktiviert.
  - `1` - Rollforward wird in der Nebenversion, nicht aber in der Hauptversion, ausgeführt. Dies ist das Standardverhalten.
  - `2` - Rollforward wird in Neben- und Hauptversionen ausgeführt.

  Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).

  Ab .NET Core 3.0 wird diese Option durch `--roll-forward` abgelöst, und diese Option sollte stattdessen verwendet werden.

- **`--fx-version <VERSION>`**

  Version der .NET-Runtime, die zum Ausführen der Anwendung verwendet werden soll

  Diese Option überschreibt die Version des ersten Frameworkverweises in der `.runtimeconfig.json`-Datei der Anwendung. Dies bedeutet, dass sie nur dann wie erwartet funktioniert, wenn nur ein Frameworkverweis vorliegt. Wenn die Anwendung über mehrere Frameworkverweise verfügt, kann die Verwendung dieser Option zu Fehlern führen.

## <a name="dotnet-commands"></a>dotnet-Befehle

### <a name="general"></a>Allgemein

| Befehl                                       | Funktion                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | Erstellt eine .NET-Anwendung                                     |
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
[dotnet nuget push](dotnet-nuget-push.md) | Überträgt ein Paket auf den Server und veröffentlicht es.
[dotnet nuget locals](dotnet-nuget-locals.md) | Löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder den Ordner mit globalen Paketen auf dem Computer, oder listet diese Ressourcen auf.
[dotnet nuget add source](dotnet-nuget-add-source.md) | Hiermit fügen Sie eine NuGet-Quelle hinzu.
[dotnet nuget disable source](dotnet-nuget-disable-source.md) | Hiermit deaktivieren Sie eine NuGet-Quelle.
[dotnet nuget enable source](dotnet-nuget-enable-source.md) | Hiermit aktivieren Sie eine NuGet-Quelle.
[dotnet nuget list source](dotnet-nuget-list-source.md) | Hiermit werden alle konfigurierten NuGet-Quellen aufgelistet.
[dotnet nuget remove source](dotnet-nuget-remove-source.md) | Hiermit entfernen Sie eine NuGet-Quelle.
[dotnet nuget update source](dotnet-nuget-update-source.md) | Hiermit aktualisieren Sie eine NuGet-Quelle.

### <a name="global-tool-path-and-local-tools-commands"></a>Befehle für globale, Toolpfad- und lokale Tools

Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden. Sie können Tools selbst schreiben oder Drittanbietertools installieren. Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet. Weitere Informationen finden Sie unter [Übersicht über die .NET-Tools](global-tools.md). Globale und Toolpfadtools sind ab .NET Core SDK 2.1 verfügbar. Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.

Befehl | Funktion
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Installiert ein Tool auf dem Computer.
[dotnet tool list](dotnet-tool-list.md) | Listet alle globalen, Toolpfad- und lokalen Tools auf, die derzeit auf Ihrem Computer installiert sind.
[dotnet tool search](dotnet-tool-list.md) | Durchsucht NuGet.org nach Tools mit dem angegebenen Suchbegriff im Namen oder in den Metadaten
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Deinstalliert ein Tool von Ihrem Computer.
[dotnet tool update](dotnet-tool-update.md) | Aktualisiert ein Tool, das auf Ihrem Computer installiert ist.

### <a name="additional-tools"></a>Weitere Tools

Ab dem .NET Core SDK 2.1.300 stehen viele Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, jetzt als Teil des .NET SDK zur Verfügung. Diese Tools werden in der folgenden Tabelle aufgeführt:

| Tool                                              | Funktion                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Erstellt und verwaltet Entwicklungszertifikate.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Entity Framework Core-Befehlszeilentools.                    |
| sql-cache                                         | SQL Server-Cache-Befehlszeilentools.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Verwaltet die Entwicklung von Benutzergeheimnissen.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Startet einen Datei-Watcher, der einen Befehl ausführt, wenn sich Dateien ändern. |

Geben Sie `dotnet <tool-name> --help` ein, um weitere Informationen zu den einzelnen Tools zu erhalten.

## <a name="examples"></a>Beispiele

Erstellen einer neuen .NET-Konsolenanwendung:

```dotnetcli
dotnet new console
```

Erstellen eines Projekts und seiner Abhängigkeiten in einem vorgegebenen Verzeichnis:

```dotnetcli
dotnet build
```

Ausführen einer Anwendung:

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a>Umgebungsvariablen

- `DOTNET_ROOT`, `DOTNET_ROOT(x86)`

  Gibt den Speicherort der .NET-Runtimes an, wenn sie nicht am Standardspeicherort installiert sind. Der Standardspeicherort unter Windows ist `C:\Program Files\dotnet`. Der Standardspeicherort unter Linux und macOS ist `/usr/share/dotnet`. Diese Umgebungsvariable wird nur beim Ausführen von Anwendungen über generierte ausführbare Dateien (Apphosts) verwendet. `DOTNET_ROOT(x86)` wird stattdessen verwendet, wenn eine ausführbare 32-Bit-Datei auf einem 64-Bit-Betriebssystem ausgeführt wird.

- `NUGET_PACKAGES`

  Der Ordner für globale Pakete. Wenn er nicht festgelegt wird, wird standardmäßig `~/.nuget/packages` unter Unix oder `%userprofile%\.nuget\packages` unter Windows verwendet.

- `DOTNET_SERVICING`

  Gibt den Speicherort des Wartungsindex an, der vom freigegebenen Host verwendet wird, wenn die Laufzeit geladen wird.

- `DOTNET_NOLOGO`

  Gibt an, ob bei der ersten Ausführung .NET-Willkommensnachrichten und -Telemetriemeldungen angezeigt werden. Bei Festlegung auf `true` werden diese Meldungen unterdrückt (akzeptierte Werte: `true`, `1` oder `yes`), bei Festlegung auf `false` werden die Meldungen zugelassen (akzeptierte Werte: `false`, `0` oder `no`). Sofern nicht festgelegt, lautet der Standardwert `false`, und die Meldungen werden bei der ersten Ausführung angezeigt. Dieses Flag besitzt keine Auswirkung auf die Telemetrie (siehe `DOTNET_CLI_TELEMETRY_OPTOUT` zum Deaktivieren der Übermittlung von Telemetriedaten).

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  Gibt an, ob Daten zur Nutzung von .NET-Tools gesammelt und an Microsoft gesendet werden. Legen Sie `true` fest, um die Telemetriefunktion zu deaktivieren (Wert `true`, `1` oder `yes` wird akzeptiert). Legen Sie andernfalls `false` fest, um die Telemetriefunktionen zu aktivieren (Wert `false`, `0` oder `no` wird akzeptiert). Ohne Festlegung ist der Standardwert `false`, und die Telemetriefunktion ist aktiviert.

- `DOTNET_MULTILEVEL_LOOKUP`

  Gibt an, ob die .NET-Runtime, das gemeinsame Framework oder das SDK vom globalen Speicherort aus aufgelöst werden. Ohne Festlegung ist der Standardwert 1 (logisch `true`). Auf 0 (logisch `false`) festgelegt, damit keine Auflösung vom globalen Speicherort aus erfolgt und isolierte .NET-Installationen verwendet werden. Weitere Informationen zu Lookup mit mehreren Ebenen finden Sie unter [Multi-level SharedFX lookup (SharedFX-Lookup mit mehreren Ebenen)](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).

- `DOTNET_ROLL_FORWARD` **Verfügbar ab .NET Core 3.x.**

  Bestimmt das Rollforwardverhalten. Weitere Informationen finden Sie unter der Option `--roll-forward` weiter oben in diesem Artikel.

- `DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Verfügbar ab .NET Core 3.x.**

  Wenn diese Option auf `1` (aktiviert) festgelegt ist, wird das Rollforward von einer endgültigen Produktversion zu einer Vorabversion aktiviert. Wenn eine endgültige Releaseversion der .NET-Runtime angefordert wird, werden standardmäßig (`0` – deaktiviert) nur installierte endgültige Releaseversionen beim Rollforward berücksichtigt.

  Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).

- `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Verfügbar in .NET Core 2.x.**

  Deaktiviert Rollforward der Nebenversion, wenn `0` festgelegt ist. Weitere Informationen finden Sie unter [Rollforward](../whats-new/dotnet-core-2-1.md#roll-forward).

  Diese Einstellung wird in .NET Core 3.0 durch `DOTNET_ROLL_FORWARD` abgelöst. Stattdessen sollten die neuen Einstellungen verwendet werden.

- `DOTNET_CLI_UI_LANGUAGE`

  Legt die Sprache der CLI-Benutzeroberfläche mit einem Gebietsschemawert wie `en-us` fest. Die unterstützten Werte sind identisch mit denen für Visual Studio. Weitere Informationen finden Sie im Abschnitt zum Ändern der Sprache des Installationsprogramms in der [Visual Studio-Installationsdokumentation](/visualstudio/install/install-visual-studio). Es gelten die Regeln des .NET-Ressourcen-Managers, sodass Sie keine genaue Übereinstimmung auswählen müssen, sondern auch Nachfolger in der `CultureInfo`-Struktur auswählen können. Bei einer Festlegung auf `fr-CA` findet und verwendet die Befehlszeilenschnittstelle z. B. die `fr`-Übersetzungen. Wenn Sie eine nicht unterstützte Sprache festlegen, greift die Befehlszeilenschnittstelle auf Englisch zurück.

- `DOTNET_DISABLE_GUI_ERRORS`

  Für generierte ausführbare Dateien mit aktivierter Benutzeroberfläche – deaktiviert das Dialogfeld-Popupfenster, das normalerweise bei bestimmten Fehlerklassen angezeigt wird. Es schreibt nur an `stderr` und beendet sich nur in diesen Fällen.
  
- `DOTNET_ADDITIONAL_DEPS`

  Entspricht der CLI-Option `--additional-deps`.

- `DOTNET_RUNTIME_ID`

  Setzt die erkannte RID außer Kraft.

- `DOTNET_SHARED_STORE`

  Speicherort des „gemeinsamen Speichers“, auf den die Assemblyauflösung in einigen Fällen zurückgreift.

- `DOTNET_STARTUP_HOOKS`

  Liste der Assemblys zum Laden und Ausführen von Startuphooks.

- `DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Verfügbar ab .NET Core 3.x.**

  Gibt ein Verzeichnis an, in das eine Einzeldateianwendung vor der Ausführung extrahiert wird.

  Weitere Informationen finden Sie unter [Ausführbare Einzeldateien](../whats-new/dotnet-core-3-0.md#single-file-executables).

- `COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`

  Steuert die Diagnoseablaufverfolgung von den Hostingkomponenten wie `dotnet.exe`, `hostfxr` und `hostpolicy`.

  * `COREHOST_TRACE=[0/1]` – Standardwert ist `0` – Ablaufverfolgung deaktiviert. Wenn auf `1` festgelegt, ist die Diagnoseablaufverfolgung aktiviert.
  * `COREHOST_TRACEFILE=<file path>` – ist nur wirksam, wenn die Ablaufverfolgung über `COREHOST_TRACE=1` aktiviert wird. Wenn festgelegt, werden die Ablaufverfolgungsinformationen in die angegebene Datei geschrieben, andernfalls in `stderr`. **Verfügbar ab .NET Core 3.x.**
  * `COREHOST_TRACE_VERBOSITY=[1/2/3/4]` – Standardwert ist `4`. Die Einstellung wird nur verwendet, wenn die Ablaufverfolgung über `COREHOST_TRACE=1` aktiviert wird. **Verfügbar ab .NET Core 3.x.**
    * `4` – alle Ablaufverfolgungsinformationen werden geschrieben
    * `3` – nur Informationen, Warn- und Fehlermeldungen werden geschrieben
    * `2` – nur Warn- und Fehlermeldungen werden geschrieben
    * `1` – nur Fehlermeldungen werden geschrieben

  Die übliche Methode, ausführliche Ablaufverfolgungsinformationen zum Starten der Anwendung zu erhalten, besteht darin, vor der Ausführung der Anwendung `COREHOST_TRACE=1` und `COREHOST_TRACEFILE=host_trace.txt` festzulegen. Im aktuellen Verzeichnis wird eine neue Datei `host_trace.txt` mit detaillierten Informationen erstellt.

## <a name="see-also"></a>Siehe auch

- [Laufzeitkonfigurationsdateien](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [Konfigurationseinstellungen für die .NET-Runtime](../run-time-config/index.md)
