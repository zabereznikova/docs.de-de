---
title: Sprachreferenz
description: Hier finden Sie Informationen zu F#-Sprachfeatures, von diesem Verweis bis hin zu Sprachtoken, Konzepten, Typen, Ausdrücken und vom Compiler unterstützte Erstellungsthemen.
ms.date: 08/13/2020
ms.openlocfilehash: 02711489c214c1fcdb2da80f30bff63d67769c17
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558152"
---
# <a name="f-language-reference"></a>F#-Sprachreferenz

Dieser Abschnitt ist eine Sprachreferenz für F#, eine Programmiersprache mit vielen Paradigmen, die auf .NET ausgerichtet ist. Die Sprache F# unterstützt funktionale, objektorientierte und imperative Programmiermodelle.

## <a name="f-core-library-api-reference"></a>API-Referenz zur F# Core-Bibliothek

Die [API-Referenz zur F# Core-Bibliothek (FSharp.Core)](https://fsharp.github.io/fsharp-core-docs/) ist die Referenz für alle Namespaces, Module, Typen und Funktionen der F# Core-Bibliothek.

## <a name="f-tokens"></a>F#-Token

Die folgende Tabelle enthält Referenzartikel, die Tabellen mit Schlüsselwörtern, Symbolen und Literalen enthalten, die als Token in F# verwendet werden.

|Titel|BESCHREIBUNG|
|-----|-----------|
|[Schlüsselwortreferenz](keyword-reference.md)|Enthält Links zu Informationen über alle F#-Schlüsselwörter.|
|[Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)|Enthält eine Tabelle mit Symbolen und Operatoren, die in der Sprache F# verwendet werden.|
|[Literale](literals.md)|Beschreibt die Syntax für literale Werte in F# und wie Typinformationen für F#-Literale angegeben werden.|

## <a name="f-language-concepts"></a>F#-Sprachkonzepte

Die folgende Tabelle listet die verfügbare Referenzthemen auf, die Sprachkonzepte beschreiben.

|Titel|BESCHREIBUNG|
|-----|-----------|
|[Funktionen](./functions/index.md)|Funktionen sind die grundlegende Einheit für die Ausführung des Programms in einer beliebigen Programmiersprache. So wie in anderen Sprachen auch, verfügt eine F#-Funktion über einen Namen, kann Parameter besitzen und Argumente verwenden und verfügt über Text. F# unterstützt auch funktionale Konstrukte der Programmierung, z.B. das Behandeln von Funktionen als Werte, Verwenden von unbenannten Funktionen als Ausdrücke, die Zusammensetzung von Funktionen zum Bilden neuer Funktionen, Funktionen mit Currying sowie die implizite Definition von Funktionen mit der teilweise Anwendung von Funktionsargumenten.|
|[F#-Typen](fsharp-types.md)|Beschreibt die Typen, die in F# verwendet werden und wie F#-Typen benannt und beschrieben werden.|
|[Typableitung](type-inference.md)|Beschreibt, wie der F#-Compiler die Typen von Werten, Variablen, Parametern und Rückgabewerten ableitet.|
|[Automatische Verallgemeinerung](./generics/automatic-generalization.md)|Beschreibt generische Konstrukte in F#.|
|[Vererbung](inheritance.md)|Beschreibt die Vererbung, die zur Modellierung der „ist-ein“-Beziehung oder von Untertypen in der objektorientierten Programmierung verwendet wird.|
|[Mitglieder](./members/index.md)|Beschreibt Member von F#-Objekttypen.|
|[Parameter und Argumente](Parameters-and-Arguments.md)|Beschreibt die Sprachunterstützung zum Definieren von Parametern und zum Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften. Enthält Informationen zur Übergabe als Verweis.|
|[Operatorüberladung](operator-overloading.md)|Beschreibt, wie arithmetische Operatoren in einer Klasse oder einem Datensatztyp sowie auf globaler Ebene überladen werden.|
|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Beschreibt die Unterstützung für Typumwandlungen in F#.|
|[Zugriffssteuerung](access-control.md)|Beschreibt die Zugriffssteuerung in F#. Mit der Zugriffssteuerung wird deklariert, welche Clients bestimmte Programmelemente wie Typen, Methoden oder Funktionen verwenden können.|
|[Mustervergleich](pattern-matching.md)|Beschreibt Muster, die als Regeln zur Transformation von Eingangsdaten für die gesamte F#-Sprache verwendet werden: Mithilfe von Mustern können Sie Daten vergleichen, zerlegen oder auf verschiedene Weise Informationen aus diesen extrahieren.|
|[Aktive Muster](active-patterns.md)|Beschreibt aktive Muster. Mit aktiven Mustern können Sie benannte Partitionen definieren, die Eingabedaten unterteilen. Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.|
|[Assertionen](assertions.md)|Beschreibt den Ausdruck `assert`, der eine Debugfunktion zum Testen eines Ausdrucks ist. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.|
|[Ausnahmebehandlung](./exception-handling/index.md)|Enthält Informationen über die Unterstützung für die Ausnahmebehandlung in der Sprache F#.|
|[attributes](attributes.md)|Beschreibt die Attribute, mit denen Metadaten auf ein Programmierungskonstrukt angewendet werden können.|
|[Ressourcenverwaltung: Das `use`-Schlüsselwort](resource-management-the-use-keyword.md)|Beschreibt die Schlüsselwörter `use` und `using`, die die Initialisierung und Freigabe von Ressourcen steuern können.|
|[namespaces](namespaces.md)|Beschreibt die Namespaceunterstützung in F#. Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.|
|[Module](modules.md)|Beschreibt Module. Ein F#-Modul ist eine Gruppierung von F#-Code, z.B. Werte, Typen und Funktionswerte in einem F#-Programm. Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.|
|[Importdeklarationen: Das `open`-Schlüsselwort](import-declarations-the-open-keyword.md)|Beschreibt, wie `open` funktioniert. Eine Importdeklaration gibt ein Modul oder einen Namespace an, auf dessen Elemente Sie ohne Angabe eines vollqualifizierten Namens verweisen können.|
|[Signaturen](signature-files.md)|Beschreibt Signaturen und Signaturdateien. Eine Signaturdatei enthält Informationen zu den öffentlichen Signaturen einer Reihe von F#-Programmelementen wie Typen, Namespaces und Modulen. Mit ihr kann der Zugriff auf diese Programmelemente angegeben werden.|
|[XML-Dokumentation](xml-documentation.md)|Beschreibt die Unterstützung für das Generieren von Dokumentationsdateien für XML-Dokumentkommentare, auch bekannt als Kommentare mit drei Schrägstrichen. Sie können die Dokumentation aus Codekommentaren in F# genau wie in anderen .NET-Sprachen erstellen.|
|[Ausführliche Syntax](verbose-syntax.md)|Beschreibt die Syntax für F#-Konstrukte, wenn die einfache Syntax nicht aktiviert ist. Ausführliche Syntax wird durch die `#light "off"`-Direktive ganz oben in der Codedatei beschrieben.|
|[Formatieren von Nur-Text](plaintext-formatting.md)|Hier erfahren Sie, wie Sie sprintf und andere Nur-Text-Formatierungen in F#-Anwendungen und -Skripts verwenden.|

## <a name="f-types"></a>F#-Typen

Die folgende Tabelle enthält verfügbare Referenzthemen, die von F# unterstützte Typen beschreiben.

|Titel|BESCHREIBUNG|
|-----|-----------|
|[Werte](./values/index.md)|Beschreibt Werte, die unveränderliche Mengen darstellen und einen bestimmten Typ aufweisen. Werte können Ganzzahlen oder Gleitkommazahlen, Zeichen oder Text, Listen, Sequenzen, Arrays, Tupeln, Unterscheidungs-Unions, Datensätze, Klassentypen oder Funktionswerte sein.|
|[Standardtypen](basic-types.md)|Beschreibt die grundlegenden Typen, die in der Sprache F# verwendet werden. Darüber hinaus werden die entsprechenden Typen in .NET und die minimalen und maximalen Werte für jeden Typ bereitgestellt.|
|[Unit-Typ](unit-type.md)|Beschreibt den `unit`-Typ, der ein Typ ist, der das Fehlen eines bestimmten Werts beschreibt; der `unit`-Typ verfügt nur über einen einzigen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder erforderlich ist.|
|[Zeichenfolgen](strings.md)|Beschreibt Zeichenfolgen in F#. Die `string`-Typ stellt unveränderlichen Text als eine Sequenz von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET Framework.|
|[Tupel](tuples.md)|Beschreibt Tupel, die Gruppierungen unbenannter aber sortierter Werte möglicher unterschiedlicher Typen sind.|
|[F#-Auflistungstypen](fsharp-collection-types.md)|Eine Übersicht der funktionalen Auflistungstypen von F#, einschließlich Typen für Arrays, Listen, Sequenzen (seq), Zuordnungen und Sätzen.|
|[Listen](lists.md)|Beschreibt Listen. Eine Liste in F# stellt eine geordnete, unveränderliche Reihe von Elementen desselben Typs dar.|
|[Optionen](options.md)|Beschreibt den Optionstyp. Eine Option in F# wird verwendet, wenn ein Wert möglicherweise vorhanden oder nicht vorhanden ist. Eine Option verfügt über einen zugrunde liegenden Typ und enthält möglicherweise einen Wert dieses Typs oder keinen Wert.|
|[Sequenzen](sequences.md)|Beschreibt Sequenzen. Eine Sequenz ist eine logische Reihe von Elementen eines einzigen Typs. Einzelne Sequenzelemente werden nur bei Bedarf berechnet, sodass die Darstellung kleiner als die Anzahl der Literalelemente sein kann.|
|[Arrays](arrays.md)|Beschreibt Arrays. Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.|
|[Datensätze](records.md)|Beschreibt Datensätze. Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.|
|[Unterscheidungs-Unions](discriminated-unions.md)|Beschreibt unterscheidbare Unions, die Werte verschiedenster benannter Fälle unterstützen können, die jeweils unterschiedliche Werte und Typen aufweisen.|
|[Enumerationen](enumerations.md)|Beschreibt, dass Enumerationen Typen sind, die über einen definierten Satz benannter Werte verfügen. Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.|
|[Referenzzellen](reference-cells.md)|Beschreibt Referenzzellen, die Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.|
|[Typabkürzungen](type-abbreviations.md)|Beschreibt Typabkürzungen, die alternative Namen für Typen sind.|
|[Klassen](classes.md)|Beschreibt Klassen, die Typen sind, die Objekte darstellen. Diese können über Eigenschaften, Methoden und Ereignisse verfügen.|
|[Strukturen](structures.md)|Beschreibt Strukturen, die kompakte Objekttypen darstellen, die für Typen, die nur eine geringe Datenmenge und ein einfaches Verhalten aufweisen, effizienter als eine Klasse sein können.|
|[Schnittstellen](interfaces.md)|Beschreibt die Schnittstellen, die Gruppen von verwandten Elementen angeben, die von anderen Klassen implementiert werden.|
|[Abstrakte Klassen](abstract-classes.md)|Beschreibt abstrakte Klassen, die Klassen sind, die einige oder alle Member nicht implementiert lassen, damit Implementierungen von abgeleiteten Klassen bereitgestellt werden können.|
|[Typerweiterungen](type-extensions.md)|Beschreibt Typerweiterungen, mit denen Sie einem zuvor definierten Objekttyp neue Member hinzufügen können.|
|[Flexible Typen](flexible-types.md)|Beschreibt flexible Typen. Eine flexible Typanmerkung gibt an, dass ein Parameter, eine Variable oder ein Wert einen Typ aufweist, der mit dem angegebenen Typ kompatibel ist. Die Kompatibilität wird durch die Position in einer objektorientierten Hierarchie der Klassen oder Schnittstellen bestimmt.|
|[Delegaten](delegates.md)|Beschreibt Delegaten, die einen Funktionsaufruf als Objekt darstellen.|
|[Maßeinheiten](units-of-measure.md)|Beschreibt Maßeinheiten. Gleitkommawerte in F# können zugeordnete Maßeinheiten besitzen, die in der Regel verwendet werden, um Länge, Volumen, Masse und usw. anzugeben.|
|[Typanbieter](../tutorials/type-providers/index.md)|Beschreibt Typanbieter und stellt Links zu exemplarischen Vorgehensweisen zur Verwendung des integrierten Typanbieters bereit, um auf Datenbanken und Webdienste zuzugreifen.|

## <a name="f-expressions"></a>F#-Ausdrücke

Die folgende Tabelle enthält Themen, in denen F#-Ausdrücke beschrieben werden.

|Titel|BESCHREIBUNG|
|-----|-----------|
|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Beschreibt den `if...then...else`-Ausdruck, der unterschiedliche Codezweige ausführt und je nach angegebenem booleschen Ausdruck ebenso einen anderen Wert ergibt.|
|[Vergleichsausdrücke](match-expressions.md)|Beschreibt den `match`-Ausdruck, der die Verzweigungssteuerung bereitstellt, die auf dem Vergleich eines Ausdrucks mit einer Reihe von Mustern basiert.|
|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|Beschreibt den `for...to`-Ausdruck, der zum Durchlaufen einer Schleife eines Wertebereichs einer Schleifenvariable verwendet wird.|
|[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)|Beschreibt den `for...in`-Ausdruck, ein Schleifenkonstrukt, das zum Durchlaufen der Übereinstimmungen eines Musters in einer aufzählbaren Auflistung verwendet wird, z.B. eine Reihe von Ausdrücken, eine Sequenz, Liste, ein Array oder ein anderes Konstrukt, das die Enumeration unterstützt.|
|[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Beschreibt den `while...do`-Ausdruck, der verwendet wird, um iterative Ausführung (Schleifen) auszuführen, während eine bestimmte Testbedingung erfüllt ist.|
|[Objektausdrücke](object-expressions.md)|Beschreibt Objektausdrücke, die Ausdrücke darstellen, die neue Instanzen eines dynamisch erstellten anonymen Objekttyps erstellen, der auf einem vorhandenen Basistyp, einer Schnittstelle oder einem Satz von Schnittstellen basiert.|
|[Nicht strikte Ausdrücke](lazy-expressions.md)|Beschreibt verzögerte Ausdrücke, also Berechnungen, die nicht sofort ausgewertet werden, sondern erst dann, wenn das Ergebnis tatsächlich benötigt wird.|
|[Berechnungsausdrücke](computation-expressions.md)|Beschreibt Berechnungsausdrücke in F#, die eine bequeme Syntax für das Schreiben von Berechnungen bereitstellen, die mithilfe von Ablaufsteuerungskonstrukten und Bindungen sequenziert und kombiniert werden können. Sie können verwendet werden, um eine einfache Syntax für *monads* bereitstellen, ein Feature zur funktionalen Programmierung, das zur Verwaltung von Daten, Steuerelementen und Nebenwirkungen in funktionalen Programmen verwendet werden können. Ein Typ eines Berechnungsausdrucks, der asynchrone Workflow, bietet Unterstützung für asynchrone und gleichzeitige Berechnungen. Weitere Informationen finden Sie unter [Asynchrone Workflows](asynchronous-workflows.md).|
|[Asynchrone Workflows](asynchronous-workflows.md)|Beschreibt asynchrone Workflows, eine Sprachfunktion, mit der Sie asynchronen Code in einer Weise schreiben können, die der Methode zum Schreiben von synchronem Code sehr ähnlich ist.|
|[Zitieren von Code](code-quotations.md)|Beschreibt Codezitate, eine Sprachfunktion, die das programmgesteuerte Generieren und Arbeiten mit F#-Codeausdrücken ermöglicht.|
|[Abfrageausdrücke](query-expressions.md)|Beschreibt die Abfrageausdrücke, ein Sprachfeature, das LINQ für F# implementiert, und mit dem Sie Abfragen für eine Datenquelle oder eine aufzählbare Auflistung schreiben können.|

## <a name="compiler-supported-constructs"></a>Vom Compiler unterstützte Konstrukte

Die folgende Tabelle enthält Themen, die bestimmte compilerunterstützte Konstrukte enthalten.

|Thema|BESCHREIBUNG|
|-----|-----------|
|[Compileroptionen](compiler-options.md)|Beschreibt die Befehlszeilenoptionen für den F#-Compiler.|
|[Compileranweisungen](compiler-directives.md)|Beschreibt Prozessor- und Compileranweisungen.|
|[Quellzeilen-, Datei- und Pfadbezeichner](source-line-file-path-identifiers.md)|Beschreibt die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__`, die integrierte Werte darstellen, mit denen Sie auf die Zeilennummer der Quelle sowie auf das Verzeichnis und den Dateinamen in Ihrem Code zugreifen können.|
