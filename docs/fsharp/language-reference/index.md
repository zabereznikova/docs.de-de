---
title: F#-Sprachreferenz
description: Hier F# finden Sie Informationen zu sprach Features aus diesem Verweis zu sprach Token, Konzepten, Typen, Ausdrücken und vom Compiler unterstützten Erstellungs Themen.
ms.date: 05/16/2016
ms.openlocfilehash: bd9894176fa736b9eed939d72972e676e2bd2671
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552907"
---
# <a name="f-language-reference"></a>F#-Sprachreferenz

Dieser Abschnitt ist ein Verweis auf die F# Sprache, eine Programmiersprache mit mehreren Paradigmen, die auf .net abzielt. Die Sprache F# unterstützt funktionale, objektorientierte und imperative Programmiermodelle.

## <a name="f-tokens"></a>F#-Token

Die folgende Tabelle enthält Referenzthemen, die Tabellen der Schlüsselwörter, Symbole und Literale bereitstellen, die als Token in F# verwendet werden.

|Title|Beschreibung|
|-----|-----------|
|[Schlüsselwortreferenz](keyword-reference.md)|Enthält Links zu Informationen über alle F#-Schlüsselwörter.|
|[Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)|Enthält eine Tabelle mit Symbolen und Operatoren, die in der Sprache F# verwendet werden.|
|[Literale](literals.md)|Beschreibt die Syntax für literale Werte in F# und wie Typinformationen für F#-Literale angegeben werden.|

## <a name="f-language-concepts"></a>F#-Sprachkonzepte

Die folgende Tabelle listet die verfügbare Referenzthemen auf, die Sprachkonzepte beschreiben.

|Title|Beschreibung|
|-----|-----------|
|[Funktionen](./functions/index.md)|Funktionen sind die grundlegende Einheit für die Ausführung des Programms in einer beliebigen Programmiersprache. So wie in anderen Sprachen auch, verfügt eine F#-Funktion über einen Namen, kann Parameter besitzen und Argumente verwenden und verfügt über Text. F# unterstützt auch funktionale Konstrukte der Programmierung, z.B. das Behandeln von Funktionen als Werte, Verwenden von unbenannten Funktionen als Ausdrücke, die Zusammensetzung von Funktionen zum Bilden neuer Funktionen, Funktionen mit Currying sowie die implizite Definition von Funktionen mit der teilweise Anwendung von Funktionsargumenten.|
|[F#-Typen](fsharp-types.md)|Beschreibt die Typen, die in F# verwendet werden und wie F#-Typen benannt und beschrieben werden.|
|[Typableitung](type-inference.md)|Beschreibt, wie der F#-Compiler die Typen von Werten, Variablen, Parameter und Rückgabewerte herleitet.|
|[Automatische Verallgemeinerung](./generics/automatic-generalization.md)|Beschreibt generische Konstrukte in F#.|
|[Vererbung](inheritance.md)|Beschreibt die Vererbung, die zur Modellierung der „ist-ein“-Beziehung oder von Untertypen in der objektorientierten Programmierung verwendet wird.|
|[Mitglieder](./members/index.md)|Beschreibt Member von F#-Objekttypen.|
|[Parameter und Argumente](Parameters-and-Arguments.md)|Beschreibt die Sprachunterstützung zum Definieren von Parametern und zum Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften. Enthält Informationen zur Übergabe als Verweis.|
|[Operatorüberladung](operator-overloading.md)|Beschreibt, wie arithmetische Operatoren in einer Klasse oder einem Datensatztyp sowie auf globaler Ebene überladen werden.|
|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Beschreibt die Unterstützung für Typumwandlungen in F#.|
|[Zugriffssteuerung](access-control.md)|Beschreibt die Zugriffssteuerung in F#. Zugriffssteuerung beschreibt, wie deklariert wird, welche Clients bestimmte Programmelemente verwenden können, z.B. Typen, Methoden, Funktionen usw.|
|[Mustervergleich](pattern-matching.md)|Beschreibt Muster,die Regeln zum Umwandeln von Eingabedaten sind, die in F# stets verwendet werden, um Vergleichsdaten mit einem Muster zu extrahieren, Daten in konstituierende Teile zu zerlegen oder Informationen aus Daten auf unterschiedliche Art zu extrahieren.|
|[Aktive Muster](active-patterns.md)|Beschreibt aktive Muster. Mit aktiven Mustern können Sie benannte Partitionen definieren, die Eingabedaten unterteilen. Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.|
|[Assertionen](assertions.md)|Beschreibt den Ausdruck `assert`, der eine Debugfunktion zum Testen eines Ausdrucks ist. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.|
|[Ausnahmebehandlung](./exception-handling/index.md)|Enthält Informationen über die Unterstützung für die Ausnahmebehandlung in der Sprache F#.|
|[Attribute](attributes.md)|Beschreibt die Attribute, mit denen Metadaten auf ein Programmierungskonstrukt angewendet werden können.|
|[Ressourcenverwaltung: Das `use`-Schlüsselwort](resource-management-the-use-keyword.md)|Beschreibt die Schlüsselwörter `use` und `using`, die die Initialisierung und Freigabe von Ressourcen steuern können.|
|[Namespaces](namespaces.md)|Beschreibt die Namespaceunterstützung in F#. Mit einem Namespace können Sie Code in Bereichen verwandter Funktionalität organisieren, indem Sie einen Namen an eine Gruppierung von Programmelementen anfügen.|
|[Module](modules.md)|Beschreibt Module. Ein F#-Modul ist eine Gruppierung von F#-Code, z.B. Werte, Typen und Funktionswerte in einem F#-Programm. Das Gruppieren von Code in Modulen hilft dabei, verwandten Code zusammen zu halten und Namenskonflikte in Ihrem Programm zu vermeiden.|
|[Importdeklarationen: Das `open`-Schlüsselwort](import-declarations-the-open-keyword.md)|Beschreibt, wie `open` funktioniert. Eine Importdeklaration gibt ein Modul oder einen Namespace an, auf dessen Elemente Sie ohne Angabe eines vollqualifizierten Namens verweisen können.|
|[Signaturen](signature-files.md)|Beschreibt Signaturen und Signaturdateien. Eine Signaturdatei enthält Informationen zu den öffentlichen Signaturen einer Reihe von F#-Programmelementen wie Typen, Namespaces und Modulen. Mit ihr kann der Zugriff auf diese Programmelemente angegeben werden.|
|[XML-Dokumentation](xml-documentation.md)|Beschreibt die Unterstützung für das Generieren von Dokumentationsdateien für XML-Dokumentkommentare, auch bekannt als Kommentare mit drei Schrägstrichen. Sie können die Dokumentation von Codekommentaren im Code in F# genau so wie in anderen .NET-Sprachen erstellen.|
|[Ausführliche Syntax](verbose-syntax.md)|Beschreibt die Syntax für F#-Konstrukte, wenn die einfache Syntax nicht aktiviert ist. Ausführliche Syntax wird durch die `#light "off"`-Direktive ganz oben in der Codedatei beschrieben.|

## <a name="f-types"></a>F#-Typen

Die folgende Tabelle enthält verfügbare Referenzthemen, die von F# unterstützte Typen beschreiben.

|Title|Beschreibung|
|-----|-----------|
|[Werte](./values/index.md)|Beschreibt Werte, die unveränderliche Mengen darstellen und einen bestimmten Typ aufweisen. Werte können Ganzzahlen oder Gleitkommazahlen, Zeichen oder Text, Listen, Sequenzen, Arrays, Tupeln, Unterscheidungs-Unions, Datensätze, Klassentypen oder Funktionswerte sein.|
|[Grundlegende Typen](basic-types.md)|Beschreibt die grundlegenden Typen, die in der F# Sprache verwendet werden. Darüber hinaus werden die entsprechenden Typen in .NET und die minimalen und maximalen Werte für jeden Typ bereitgestellt.|
|[Unit-Typ](unit-type.md)|Beschreibt den `unit`-Typ, der ein Typ ist, der das Fehlen eines bestimmten Werts beschreibt; der `unit`-Typ verfügt nur über einen einzigen Wert, der als Platzhalter fungiert, wenn kein anderer Wert vorhanden oder erforderlich ist.|
|[Zeichenfolgen](strings.md)|Beschreibt Zeichenfolgen in F#. Die `string`-Typ stellt unveränderlichen Text als eine Sequenz von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET Framework.|
|[Tupel](tuples.md)|Beschreibt Tupel, die Gruppierungen unbenannter aber sortierter Werte möglicher unterschiedlicher Typen sind.|
|[F#-Auflistungstypen](fsharp-collection-types.md)|Eine Übersicht der funktionalen Auflistungstypen von F#, einschließlich Typen für Arrays, Listen, Sequenzen (seq), Zuordnungen und Sätzen.|
|[Listen](lists.md)|Beschreibt Listen. Eine Liste in F# stellt eine geordnete, unveränderliche Reihe von Elementen desselben Typs dar.|
|[Optionen](options.md)|Beschreibt den Optionstyp. Eine Option in F# wird verwendet, wenn ein Wert möglicherweise vorhanden oder nicht vorhanden ist. Eine Option verfügt über einen zugrunde liegenden Typ und enthält möglicherweise einen Wert dieses Typs oder keinen Wert.|
|[Sequenzen](sequences.md)|Beschreibt Sequenzen. Eine Sequenz ist eine logische Reihe von Elementen eines einzigen Typs. Einzelne Sequenzelemente werden nur bei Bedarf berechnet, damit die Darstellung möglicherweise kleiner ist, als die Anzahl des Literal-Elements angibt.|
|[Arrays](arrays.md)|Beschreibt Arrays. Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.|
|[Datensätze](records.md)|Beschreibt Datensätze. Datensätze stellen einfache Aggregate benannter Werte dar, optional mit Membern.|
|[Unterscheidbare Unions](discriminated-unions.md)|Beschreibt diskriminierte Unions, die Unterstützung für Werte bieten, die eine Vielzahl verschiedener benannter Fälle sein können, und jeder Fall verfügt über unterschiedliche Werte und Typen.|
|[Enumerationen](enumerations.md)|Beschreibt, dass Enumerationen Typen sind, die über einen definierten Satz benannter Werte verfügen. Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.|
|[Referenzzellen](reference-cells.md)|Beschreibt Referenzzellen, die Speicherorte sind, die Ihnen ermöglichen, änderbare Werte mit Verweissemantik zu erstellen.|
|[Typabkürzungen](type-abbreviations.md)|Beschreibt Typabkürzungen, die alternative Namen für Typen sind.|
|[Klassen](classes.md)|Beschreibt Klassen, die Typen sind, die Objekte darstellen. Diese können über Eigenschaften, Methoden und Ereignisse verfügen.|
|[Strukturen](structures.md)|Beschreibt Strukturen, die kompakte Objekttypen darstellen, die für Typen, die nur eine geringe Datenmenge und ein einfaches Verhalten aufweisen, effizienter als eine Klasse sein können.|
|[Schnittstellen](interfaces.md)|Beschreibt die Schnittstellen, die Gruppen von verwandten Elementen angeben, die von anderen Klassen implementiert werden.|
|[Abstrakte Klassen](abstract-classes.md)|Beschreibt abstrakte Klassen, die Klassen sind, die einige oder alle Member nicht implementiert lassen, damit Implementierungen von abgeleiteten Klassen bereitgestellt werden können.|
|[Typerweiterungen](type-extensions.md)|Beschreibt Typerweiterungen, mit denen Sie einem zuvor definierten Objekttyp neue Member hinzufügen können.|
|[Flexible Typen](flexible-types.md)|Beschreibt flexible Typen. Eine Anmerkung flexibler Typen ist ein Hinweis, dass ein Parameter, eine Variable oder ein Wert über einen Typ verfügt, der mit dem angegebenen Typ kompatibel ist. Die Kompatibilität wird durch die Position in einer objektorientierten Hierarchie von Klassen oder Schnittstellen bestimmt.|
|[Delegaten](delegates.md)|Beschreibt Delegaten, die einen Funktionsaufruf als Objekt darstellen.|
|[Maßeinheiten](units-of-measure.md)|Beschreibt Maßeinheiten. Gleitkommawerte in F# können zugeordnete Maßeinheiten besitzen, die in der Regel verwendet werden, um Länge, Volumen, Masse und usw. anzugeben.|
|[Typanbieter](../tutorials/type-providers/index.md)|Beschreibt Typanbieter und stellt Links zu exemplarischen Vorgehensweisen zur Verwendung des integrierten Typanbieters bereit, um auf Datenbanken und Webdienste zuzugreifen.|

## <a name="f-expressions"></a>F#-Ausdrücke

Die folgende Tabelle enthält Themen, in denen F#-Ausdrücke beschrieben werden.

|Title|Beschreibung|
|-----|-----------|
|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Beschreibt den `if...then...else`-Ausdruck, der unterschiedliche Codezweige ausführt und je nach angegebenem booleschen Ausdruck ebenso einen anderen Wert ergibt.|
|[Vergleichsausdrücke](match-expressions.md)|Beschreibt den `match`-Ausdruck, der die Verzweigungssteuerung bereitstellt, die auf dem Vergleich eines Ausdrucks mit einer Reihe von Mustern basiert.|
|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|Beschreibt den `for...to`-Ausdruck, der zum Durchlaufen einer Schleife eines Wertebereichs einer Schleifenvariable verwendet wird.|
|[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)|Beschreibt den `for...in`-Ausdruck, ein Schleifenkonstrukt, das zum Durchlaufen der Übereinstimmungen eines Musters in einer aufzählbaren Auflistung verwendet wird, z.B. eine Reihe von Ausdrücken, eine Sequenz, Liste, ein Array oder ein anderes Konstrukt, das die Enumeration unterstützt.|
|[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Beschreibt den `while...do`-Ausdruck, der verwendet wird, um iterative Ausführung (Schleifen) auszuführen, während eine bestimmte Testbedingung erfüllt ist.|
|[Objektausdrücke](object-expressions.md)|Beschreibt Objektausdrücke, die Ausdrücke darstellen, die neue Instanzen eines dynamisch erstellten anonymen Objekttyps erstellen, der auf einem vorhandenen Basistyp, einer Schnittstelle oder einem Satz von Schnittstellen basiert.|
|[Nicht strikte Ausdrücke](lazy-expressions.md)|Beschreibt verzögerte Ausdrücke, bei denen es sich um Berechnungen handelt, die nicht sofort ausgewertet werden, sondern stattdessen ausgewertet werden, wenn das Ergebnis tatsächlich benötigt wird.|
|[Berechnungsausdrücke](computation-expressions.md)|Beschreibt Berechnungsausdrücke in F#, die eine bequeme Syntax für das Schreiben von Berechnungen bereitstellen, die mithilfe von Ablaufsteuerungskonstrukten und Bindungen sequenziert und kombiniert werden können. Sie können verwendet werden, um eine einfache Syntax für *monads* bereitstellen, eine Funktion zur funktionalen Programmierung, die zur Verwaltung von Daten, Steuereffekte und Nebenwirkungen in funktionalen Programmen verwendet werden können. Ein Typ eines Berechnungsausdrucks, der asynchrone Workflow, bietet Unterstützung für asynchrone und gleichzeitige Berechnungen. Weitere Informationen finden Sie unter [Asynchrone Workflows](asynchronous-workflows.md).|
|[Asynchrone Workflows](asynchronous-workflows.md)|Beschreibt asynchrone Workflows, eine Sprachfunktion, mit der Sie asynchronen Code in einer Weise schreiben können, die der Methode zum Schreiben von synchronem Code sehr ähnlich ist.|
|[Zitieren von Code](code-quotations.md)|Beschreibt Codezitate, eine Sprachfunktion, die das programmgesteuerte Generieren und Arbeiten mit F#-Codeausdrücken ermöglicht.|
|[Abfrageausdrücke](query-expressions.md)|Beschreibt die Abfrageausdrücke, ein Sprachfeature, das LINQ für F# implementiert, und mit dem Sie Abfragen für eine Datenquelle oder eine aufzählbare Auflistung schreiben können.|

## <a name="compiler-supported-constructs"></a>Vom Compiler unterstützte Konstrukte

Die folgende Tabelle enthält Themen, die bestimmte compilerunterstützte Konstrukte enthalten.

|Topic|Beschreibung|
|-----|-----------|
|[Compileroptionen](compiler-options.md)|Beschreibt die Befehlszeilenoptionen für den F#-Compiler.|
|[Compileranweisungen](compiler-directives.md)|Beschreibt Prozessor- und Compileranweisungen.|
|[Quellzeilen-, Datei- und Pfadbezeichner](source-line-file-path-identifiers.md)|Beschreibt die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__`, die integrierte Werte darstellen, mit denen Sie auf die Zeilennummer der Quelle sowie auf das Verzeichnis und den Dateinamen in Ihrem Code zugreifen können.|
