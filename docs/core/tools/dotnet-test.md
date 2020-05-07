---
title: Befehl „dotnet test“
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624890"
---
# <a name="dotnet-test"></a>dotnet test

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet. Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde. Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet. Wenn alle Tests erfolgreich sind, gibt der Test Runner 0 (null) als Exitcode zurück. Wenn jedoch ein Test fehlschlägt, wird 1 zurückgegeben. Bei Projekten mit mehreren Zielen werden Tests für jedes Zielframework ausgeführt. Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumente

- **`PROJECT | SOLUTION`**

  Pfad zum Testprojekt oder zur Projektmappe. Wenn er nicht angegeben ist, wird standardmäßig das aktuelle Verzeichnis ausgewählt.

## <a name="options"></a>Optionen

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.

- **`--blame`**

  Führt die Tests im blame-Modus aus. Diese Option hilft beim Isolieren von fehlerhaften Tests, die den Absturz des Testhosts verursachen. In dem aktuellen Verzeichnis wird eine Ausgabedatei als *Sequence.xml* erstellt, die die Reihenfolge der ausgeführten Tests vor dem Absturz erfasst.

- **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  Aktiviert den Datensammler für den Testlauf. Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.

- **`-f|--framework <FRAMEWORK>`**

  Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).

- **`--filter <EXPRESSION>`**

  Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus. Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details). Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Gibt eine Protokollierung für die Testergebnisse an. Im Gegensatz zu MSBuild akzeptiert der Befehl „dotnet test“ keine Abkürzungen: verwenden Sie `-l "console;verbosity=detailed"` anstelle von `-l "console;v=d"`.

- **`--no-build`**

  Erstellt das Projekt nicht vor der Ausführung. Zudem wird das Flag `--no-restore` implizit festgelegt.

- **`--nologo`**

  Führen Sie Tests aus, ohne das Microsoft TestPlatform-Banner anzuzeigen. Verfügbar seit .NET Core 3.0 SDK.

- **`--no-restore`**

  Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind. Wenn nicht angegeben, ist der Standardpfad `./bin/<configuration>/<framework>/`.  Bei Projekten mit mehreren Zielframeworks (über die `TargetFrameworks`-Eigenschaft) müssen Sie auch `--framework` definieren, wenn Sie diese Option angeben. `dotnet test` führt Tests immer über das Ausgabeverzeichnis aus. Sie können <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> verwenden, um die Testobjekte im Ausgabeverzeichnis zu verarbeiten.

- **`-r|--results-directory <PATH>`**

  Das Verzeichnis, in dem die Testergebnisse gespeichert werden. Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt. Der Standardwert ist `TestResults` in dem Verzeichnis, das die Projektdatei enthält.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Die Zielruntime, für die Tests ausgeführt werden sollen.

- **`-s|--settings <SETTINGS_FILE>`**

  Die `.runsettings`-Datei, die zum Ausführen der Tests verwendet wird. Beachten Sie, dass das `TargetPlatform`-Element (x86|x64) keine Auswirkung auf `dotnet test` hat. Installieren Sie die x86-Version von .NET Core, um x86-Tests auszuführen. Die Bitanzahl der Datei *dotnet.exe*, die sich in diesem Pfad befindet, wird zum Ausführen von Tests verwendet. Weitere Informationen finden Sie in den folgenden Ressourcen:

  - [Konfigurieren von Komponententests mithilfe einer `.runsettings`-Datei.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Konfigurieren eines Testlaufs](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Listen Sie alle ermittelten Tests im aktuellen Projekt auf.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `minimal`. Weitere Informationen finden Sie unter <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- **`RunSettings`** -Argumente

  Argumente werden als `RunSettings`-Konfigurationen für den Test übergeben. Argumente werden als `[name]=[value]`-Paaren nach „-- “ angegeben (Beachten Sie das Leerzeichen nach --). Ein Leerzeichen wird verwendet, um mehrere `[name]=[value]`-Paare voneinander zu trennen.

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

- Mit dem folgenden Befehl führen Sie die Tests im aktuellen Verzeichnis aus und erstellen ein ausführliches Protokoll in der Konsole:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a>Details zu Filteroptionen

`--filter <EXPRESSION>`

`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.

`<property>` ist ein Attribut von `Test Case`. Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:

| Testframework | Unterstützte Eigenschaften                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>name</li><li>ClassName</li><li>Priorität</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Merkmale</li></ul>                                   |

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
| <code>&#124;</code> | ODER       |
| `&`                 | UND      |

Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).

Weitere Informationen und Beispiele zur Verwendung von selektiven Komponententestfiltern finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Siehe auch

- [Frameworks und Ziele](../../standard/frameworks.md)
- [.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)
- [Übergeben von runsettings-Argumenten über die Befehlszeile](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
