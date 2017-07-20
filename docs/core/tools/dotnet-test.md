---
title: "Befehl dotnet-test – .NET Core CLI | Microsoft-Dokumentation"
description: "Der Befehl „dotnet-Test“ wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet."
keywords: Dotnet-Test, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: Human Translation
ms.sourcegitcommit: 1cd1761d630f61a58f29d88e9342551d48cbc6a8
ms.openlocfilehash: 0537dbbdfa61503069f6329c4163278f2c9b0af3
ms.contentlocale: de-de
ms.lasthandoff: 06/20/2017

---

<a id="dotnet-test" class="xliff"></a>

#Dotnet-Test

<a id="name" class="xliff"></a>

## Name

`dotnet-test`: .NET-Testtreiber, der verwendet wird, um Komponententests auszuführen.

<a id="synopsis" class="xliff"></a>

## Übersicht

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

<a id="description" class="xliff"></a>

## Beschreibung

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet. Komponententests sind Konsolenanwendungsprojekte, die Abhängigkeiten vom Komponententest-Framework (z.B. MSTest, NUnit oder xUnit) und dotnet-Test Runner für das Komponententest-Framework aufweisen. Sie werden als NuGet-Pakete verpackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

Testprojekte müssen auch den Test Runner angeben. Dieser wird mit einem normalen `<PackageReference>`-Element angegeben, wie in der folgenden Beispielprojektdatei gezeigt:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<a id="options" class="xliff"></a>

## Optionen

`PROJECT`
    
Gibt den Pfad des Testprojekts an. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-s|--settings <SETTINGS_FILE>`

Einstellungen, die beim Ausführen von Tests verwendet werden. 

`-t|--list-tests`

Listen Sie alle ermittelten Tests im aktuellen Projekt auf. 

`--filter <EXPRESSION>`

Filtert Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks heraus. Weitere Informationen finden Sie im Abschnitt [Details zu Filteroptionen](#filter-option-details). Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad im Testlauf. 

`-l|--logger <LoggerUri/FriendlyName>`

Gibt eine Protokollierung für die Testergebnisse an. 

`-c|--configuration <CONFIGURATION>`

Konfiguration für die Erstellung. Der Standardwert ist `Debug`, aber die Konfiguration des Projekts könnte diese SDK-Standardeinstellung überschreiben.

`-f|--framework <FRAMEWORK>`

Sucht nach Testbinärdateien für ein bestimmtes [Framework](../../standard/frameworks.md).

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Aktiviert den Diagnosemodus für die Testplattform und schreibt Diagnosemeldungen in die angegebene Datei. 

`--no-build` 

Erstellt das Testprojekt nicht vor der Ausführung.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

<a id="examples" class="xliff"></a>

## Beispiele

Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:

`dotnet test` 

Führen Sie die Tests im Projekt `test1` durch:

`dotnet test ~/projects/test1/test1.csproj`

<a id="filter-option-details" class="xliff"></a>

## Details zu Filteroptionen

`--filter <EXPRESSION>`

`<Expression>` weist das Format `<property><operator><value>[|&<Expression>]` auf.

`<property>` ist ein Attribut von `Test Case`. Im Folgenden werden die Eigenschaften aufgeführt, die von gängigen Frameworks für Komponententests unterstützt werden:

| Testframework | Unterstützte Eigenschaften                                                                                      |
| :------------: | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>Name</li><li>ClassName</li><li>Priorität</li><li>TestCategory</li></ul> |
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

Sie können Ausdrücke in Klammern einschließen, wenn Sie bedingte Operatoren verwenden (Beispiel: `(Name~TestMethod1) | (Name~TestMethod2)`).

Weitere Informationen und Beispiele für die Verwendung der selektiven Komponententestfilterung finden Sie unter [Ausführen von selektiven Komponententests](../testing/selective-unit-tests.md).

<a id="see-also" class="xliff"></a>

## Siehe auch

[Frameworks und Ziele](../../standard/frameworks.md)   
[.NET Core Runtime-ID (RID)-Katalog](../rid-catalog.md)

