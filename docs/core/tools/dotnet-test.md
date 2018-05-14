---
title: dotnet test-Befehl – .NET Core-CLI
description: Der Befehl „dotnet test“ wird zum Ausführen von Unittests in einem bestimmten Projekt verwendet.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: d85ca0bf75baa94e63358bd66d11bc29e8b9284b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-test"></a>dotnet test

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.

## <a name="synopsis"></a>Übersicht

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)


```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]
dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]
dotnet test [-h|--help]
```
---

## <a name="description"></a>description

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet. Mit dem `dotnet test`-Befehl wird die Testlauf-Konsolenanwendung gestartet, die für ein Projekt angegeben wurde. Durch den Testlauf werden Tests ausgeführt, die für ein Komponententestframework (z.B. MSTest, NUnit oder xUnit) definiert wurden, und der Erfolg oder Misserfolg der einzelnen Testausführungen wird gemeldet. Der Testlauf und die Komponententestbibliothek werden als NuGet-Pakete gepackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

In Testprojekten wird der Testlauf mittels eines normalen `<PackageReference>`-Elements angegeben, wie in der folgenden Beispielprojektdatei gezeigt wird:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>Argumente

`PROJECT`

Gibt den Pfad des Testprojekts an. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.

## <a name="options"></a>Optionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Aktiviert den Datensammler für den Testlauf. Weitere Informationen finden Sie unter [Monitor and analyze test run (Überwachen und Analysieren eines Testlaufs)](https://aka.ms/vstest-collect).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.

`-f|--framework <FRAMEWORK>`

Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).

`--filter <EXPRESSION>`

Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus. Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details). Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-l|--logger <LoggerUri/FriendlyName>`

Gibt eine Protokollierung für die Testergebnisse an.

`--no-build`

Erstellt das Testprojekt nicht vor der Ausführung.

`--no-restore`

Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.

`-r|--results-directory <PATH>`

Das Verzeichnis, in dem die Testergebnisse gespeichert werden. Das angegebene Verzeichnis wird erstellt, wenn es noch nicht vorhanden ist.

`-s|--settings <SETTINGS_FILE>`

Einstellungen, die beim Ausführen von Tests verwendet werden.

`-t|--list-tests`

Listen Sie alle ermittelten Tests im aktuellen Projekt auf.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf.

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei.

`-f|--framework <FRAMEWORK>`

Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).

`--filter <EXPRESSION>`

Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus. Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details). Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-l|--logger <LoggerUri/FriendlyName>`

Gibt eine Protokollierung für die Testergebnisse an.

`--no-build`

Erstellt das Testprojekt nicht vor der Ausführung.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.

`-s|--settings <SETTINGS_FILE>`

Einstellungen, die beim Ausführen von Tests verwendet werden.

`-t|--list-tests`

Listen Sie alle ermittelten Tests im aktuellen Projekt auf.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

---

## <a name="examples"></a>Beispiele

Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:

`dotnet test`

Führen Sie die Tests im Projekt `test1` durch:

`dotnet test ~/projects/test1/test1.csproj`

## <a name="filter-option-details"></a>Details zu Filteroptionen

`--filter <EXPRESSION>`

`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.

`<property>` ist ein Attribut von `Test Case`. Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:

| Testframework | Unterstützte Eigenschaften                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>name</li><li>ClassName</li><li>Priorität</li><li>TestCategory</li></ul> |
| Xunit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Merkmale</li></ul>                                   |

`<operator>` beschreibt die Beziehung zwischen der Eigenschaft und dem Wert:

| Operator | Funktion        |
| :------: | --------------- |
| `=`      | Genaue Übereinstimmung     |
| `!=`     | Keine genaue Übereinstimmung |
| `~`      | Enthält        |

`<value>` ist eine Zeichenfolge. Bei allen Suchvorgängen ist die Groß-/Kleinschreibung nicht relevant.

Ein Ausdruck ohne `<operator>` gilt automatisch als `contains` für die `FullyQualifiedName`-Eigenschaft (`dotnet test --filter xyz` ist beispielsweise identisch mit `dotnet test --filter FullyQualifiedName~xyz`).

Ausdrücke können mit bedingten Operatoren verknüpft werden:

| Operator | Funktion |
| :------: | :------: |
| <code>&#124;</code>      | ODER       |
| `&`      | UND      |

Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (z.B. `(Name~TestMethod1) | (Name~TestMethod2)`).

Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Siehe auch

 [Frameworks und Ziele](../../standard/frameworks.md)  
 [.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)
