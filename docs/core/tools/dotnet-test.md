---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 04/29/2020
ms.openlocfilehash: a5666cfe4c09b2b88d77b256fac922154c7d6bd7
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634382"
---
# <a name="dotnet-test"></a>dotnet test

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einer bestimmten Projektmappe verwendet. Mit dem Befehl `dotnet test` wird die Projektmappe erstellt und für jedes Testprojekt in der Projektmappe eine Testhostanwendung ausgeführt. Der Testhost führt Tests im angegebenen Projekt mithilfe eines Testframeworks aus, z. B. MSTest, NUnit oder xUnit, und meldet den Erfolg oder Fehler jedes Tests. Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben.

Bei Projekten mit mehreren Zielen werden Tests für jedes Zielframework ausgeführt. Der Testhost und das Komponententest-Framework werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

Wobei `Microsoft.NET.Test.Sdk` der Testhost und `xunit` das Testframework ist. Und `xunit.runner.visualstudio` ist ein Testadapter, der es dem xUnit-Framework ermöglicht, mit dem Testhost zu arbeiten.

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumente

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - Der Pfad zum Testprojekt.
  - Der Pfad zur Projektmappe.
  - Der Pfad zu einem Verzeichnis, das ein Projekt oder eine Projektmappe enthält.
  - Der Pfad zur *DLL*-Datei eines Testprojekts.

  Ist dieses Argument nicht angegeben, wird nach einem Projekt oder einer Projektmappe im aktuellen Verzeichnis gesucht.

## <a name="options"></a>Optionen

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  Der Pfad zu einem Verzeichnis, das nach zusätzlichen Testadaptern durchsucht werden soll. Nur *DLL*-Dateien mit dem Suffix `.TestAdapter.dll` werden untersucht. Wenn nichts angegeben ist, wird das Verzeichnis der Test-*DLL* durchsucht.

- **`--blame`**

  Führt die Tests im blame-Modus aus. Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen. Wenn ein Absturz erkannt wird, wird in `TestResults/<Guid>/<Guid>_Sequence.xml` eine Sequenzdatei erstellt, die die Reihenfolge der Tests erfasst, die vor dem Absturz ausgeführt wurden.

- **`--blame-crash`** (Verfügbar seit .NET 5.0 Preview SDK)

  Führt die Tests im Modus „Verantwortung zuweisen“ aus und erfasst ein Absturzabbild, wenn der Testhost unerwartet beendet wird. Diese Option hängt von der verwendeten Version von .NET, dem Fehlertyp und Betriebssystem ab.
  
  Für Ausnahmen in verwaltetem Code wird ab NET 5.0 automatisch ein Absturzabbild erfasst. Es wird ein Absturzabbild für den Testhost oder jegliche untergeordneten Prozesse generiert, die ebenfalls unter .NET 5.0 liefen und abgestürzt sind. Abstürze in nativem Code generieren keine Absturzabbild. Diese Option funktioniert unter Windows, macOS und Linux.
  
  Absturzabbilder in nativem Code oder bei Verwendung von .NET Core 3.1 oder früheren Versionen können unter Windows nur mithilfe von Procdump erfasst werden. Ein Verzeichnis, das *procdump.exe* und *procdump64.exe* enthält, muss in der PATH- oder PROCDUMP_PATH-Umgebungsvariablen enthalten sein. [Tools herunterladen](/sysinternals/downloads/procdump). Impliziert `--blame`.
  
  Um ein Absturzabbild aus einer nativen Anwendung zu erfassen, die unter .NET 5.0 oder höher läuft, kann die Verwendung von Procdump erzwungen werden, indem die Umgebungsvariable `VSTEST_DUMP_FORCEPROCDUMP` auf `1` festgelegt wird.

- **`--blame-crash-dump-type <DUMP_TYPE>`** (Verfügbar seit .NET 5.0 Preview SDK)

  Der Typ des zu erfassenden Absturzspeicherabbilds. Impliziert `--blame-crash`.

- **`--blame-crash-collect-always`** (Verfügbar seit .NET 5.0 Preview SDK)

  Erfasst ein Absturzabbild bei einer erwarteten und einer unerwarteten Beendigung des Testhosts.

- **`--blame-hang`** (Verfügbar seit .NET 5.0 Preview SDK)

  Hiermit werden Tests im Modus „Verantwortung zuweisen“ ausgeführt, und ein Blockadeabbild wird erfasst, wenn der Test länger als angegeben dauert.

- **`--blame-hang-dump-type <DUMP_TYPE>`** (Verfügbar seit .NET 5.0 Preview SDK)

  Der Typ des zu erfassenden Absturzspeicherabbilds. Möglich sind `full`, `mini` oder `none`. Wenn `none` angegeben wird, wird der Testhost bei einem Timeout beendet, es wird jedoch kein Abbild erfasst. Impliziert `--blame-hang`.

- **`--blame-hang-timeout <TIMESPAN>`** (Verfügbar seit .NET 5.0 Preview SDK)

  Testspezifisches Timeout, nach dem ein Blockadeabbild ausgelöst und der Testhostprozess und alle dessen untergeordneten Prozesse gesichert und beendet werden. Der Timeoutwert wird in einem der folgenden Formate angegeben:
  
  - 1.5h, 1.5hour, 1.5hours
  - 90m, 90min, 90minute, 90minutes
  - 5400s, 5400sec, 5400second, 5400seconds
  - 5400000ms, 5400000mil, 5400000millisecond, 5400000milliseconds

  Wenn keine Einheit verwendet wird (z. B. 5.400.000), wird angenommen, dass der Wert in Millisekunden angegeben wird. Bei Verwendung in Verbindung mit datenorientierten Tests hängt das Timeoutverhalten vom verwendeten Testadapter ab. Bei xUnit und NUnit wird das Timeout nach jedem Testfall erneuert. Für MSTest wird das Timeout für alle Testfälle verwendet. Diese Option wird unter Windows mit netcoreapp2.1 und höher, unter Linux mit netcoreapp3.1 und höher und unter macOS mit net5.0 und höher unterstützt. Impliziert `--blame` und `--blame-hang`.

- **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.

- **`--collect <DATA_COLLECTOR_NAME>`**

  Aktiviert den Datensammler für den Testlauf. Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).
  
  Um Code Coverage auf einer beliebigen Plattform zu erfassen, die von .NET Core unterstützt wird, installieren Sie [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) und verwenden die `--collect:"XPlat Code Coverage"`-Option.

  Unter Windows können Sie Code Coverage mithilfe der `--collect "Code Coverage"`-Option erfassen. Mit dieser Option wird eine *COVERAGE*-Datei generiert, die in Visual Studio 2019 Enterprise geöffnet werden kann. Weitere Informationen finden Sie unter [Verwenden von Code Coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) und [Anpassen der Code Coverage-Analyse](/visualstudio/test/customizing-code-coverage-analysis).

- **`-d|--diag <LOG_FILE>`**

  Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei sowie in benachbarte Dateien. Der Prozess, der die Meldungen protokolliert, bestimmt, welche Dateien erstellt werden, z. B. `*.host_<date>.txt` für das Testhostprotokoll und `*.datacollector_<date>.txt` für das Datensammlerprotokoll.

- **`-f|--framework <FRAMEWORK>`**

  Erzwingt die Verwendung von `dotnet` oder des .NET Framework-Testhosts für die Testbinärdateien. Mit dieser Option wird nur der zu verwendende Hosttyp bestimmt. Die tatsächliche zu verwendende Frameworkversion wird durch die *runtimeconfig.json* des Testprojekts bestimmt. Wenn nichts angegeben ist, wird das [TargetFramework-Assemblyattribut](/dotnet/api/system.runtime.versioning.targetframeworkattribute) verwendet, um den Hosttyp zu bestimmen. Wenn dieses Attribut von der *DLL* entfernt wird, wird der .NET Framework-Host verwendet.

- **`--filter <EXPRESSION>`**

  Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus. Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details). Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

- **`-l|--logger <LOGGER>`**

  Gibt eine Protokollierung für die Testergebnisse an. Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.

- **`--no-build`**

  Erstellt das Projekt nicht vor der Ausführung. Zudem wird das Flag `--no-restore` implizit festgelegt.

- **`--nologo`**

  Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen. Verfügbar seit .NET Core 3.0 SDK.

- **`--no-restore`**

  Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind. Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.  Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben. `dotnet test` führt Tests immer über das Ausgabeverzeichnis aus. Sie können <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> verwenden, um die Testobjekte im Ausgabeverzeichnis zu verarbeiten.

- **`-r|--results-directory <RESULTS_DIR>`**

  Das Verzeichnis, in dem die Testergebnisse gespeichert werden. Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt. Der Standardwert ist `TestResults` in dem Verzeichnis, das die Projektdatei enthält.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Die Zielruntime, für die Tests ausgeführt werden sollen.

- **`-s|--settings <SETTINGS_FILE>`**

  Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird. Das `TargetPlatform`-Element (x86|x64) hat keine Auswirkung auf `dotnet test`. Installieren Sie die x86-Version von .NET Core, um x86-Tests auszuführen. Die Bitanzahl der Datei *dotnet.exe*, die sich in diesem Pfad befindet, wird zum Ausführen von Tests verwendet. Weitere Informationen finden Sie in den folgenden Ressourcen:

  - [Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Konfigurieren eines Testlaufs](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Hiermit werden die gefundenen Tests aufgelistet, anstatt sie auszuführen.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `minimal`. Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- **`RunSettings`** -Argumente

 Inline-`RunSettings` werden als die letzten Argumente auf der Befehlszeile nach „-- “ (beachten Sie das Leerzeichen hinter „--“) übergeben. Inline-`RunSettings` werden als `[name]=[value]`-Paare angegeben. Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.

  Ein Beispiel: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

  Weitere Informationen finden Sie unter [Übergeben von RunSettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).

## <a name="examples"></a>Beispiele

- Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:

  ```dotnetcli
  dotnet test
  ```

- Führen Sie die Tests im Projekt `test1` durch:

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und generieren eine Testergebnisdatei im TRX-Format:

  ```dotnetcli
  dotnet test --logger trx
  ```

- Führen Sie die Tests im Projekt im aktuellen Verzeichnis aus, und generieren Sie eine Code-Coverage-Datei (nach der Installation der Integration von [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md)-Collectors):

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- Führen Sie die Tests im Projekt im aktuellen Verzeichnis aus, und generieren Sie eine Code Coverage-Datei (nur Windows):

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- Mit dem folgenden Befehl führen Sie die Tests in dem Projekt im aktuellen Verzeichnis aus und melden Tests, die während des Absturzes des Testhosts in Arbeit waren:

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a>Details zu Filteroptionen

`--filter <EXPRESSION>`

`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.

`<property>` ist ein Attribut von `Test Case`. Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:

| Testframework | Unterstützte Eigenschaften                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>name</li><li>ClassName</li><li>Priorität</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Merkmale</li></ul>                                   |
| NUnit          | <ul><li>FullyQualifiedName</li><li>name</li><li>TestCategory</li><li>Priorität</li></ul>                                   |

`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:

| Operator | Funktion        |
| :------: | --------------- |
| `=`      | Genaue Übereinstimmung     |
| `!=`     | Keine genaue Übereinstimmung |
| `~`      | Enthält        |
| `!~`     | Enthält nicht    |

`<value>` ist eine Zeichenfolge. Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.

Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).

Ausdrücke können mit bedingten Operatoren verknüpft werden:

| Operator            | Funktion |
| ------------------- | -------- |
| <code>&#124;</code> | ODER       |
| `&`                 | UND      |

Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).

Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Siehe auch

- [Frameworks und Ziele](../../standard/frameworks.md)
- [.NET-Runtime-ID-Katalog (RID)](../rid-catalog.md)
- [Übergeben von runsettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
