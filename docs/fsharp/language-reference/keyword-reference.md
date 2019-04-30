---
title: Schlüsselwortreferenz
description: Hier finden Sie Links zu Informationen über alle der F# Programmiersprachen-Schlüsselwörter.
ms.date: 05/16/2016
ms.openlocfilehash: d55846fe7c8d31454b6bc8684de75546800df7d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904097"
---
# <a name="keyword-reference"></a>Schlüsselwortreferenz

Dieses Thema enthält Links zu Informationen über alle F# Programmiersprachen-Schlüsselwörter.

## <a name="f-keyword-table"></a>F#Table-Schlüsselwort

Die folgende Tabelle zeigt alle F# Schlüsselwörter in alphabetischer Reihenfolge, sowie kurze Beschreibungen und Links zu relevanten Themen, die Informationen enthalten.

|Stichwort|Link|Beschreibung|
|-------|----|-----------|
|`abstract`|[Mitglieder](members/index.md)<br /><br />[Abstrakte Klassen](abstract-classes.md)|Gibt eine Methode, die entweder verfügt über keine Implementierung des Typs in der sie deklariert wird, oder ist virtuell und verfügt über eine Standardimplementierung.|
|`and`|[`let` Bindungen](functions/let-bindings.md)<br /><br />[Datensätze](records.md)<br /><br />[Mitglieder](members/index.md)<br /><br />[Einschränkungen](generics/constraints.md)|Verwendet, sich gegenseitig rekursiver Bindungen und Datensätze in Eigenschaftendeklarationen sowie mehrere Einschränkungen für generische Parameter.|
|`as`|[Klassen](classes.md)<br /><br />[Mustervergleich](Pattern-Matching.md)|Verwendet, um dem aktuelle Klassenobjekt ein Objekt benennen. Auch verwendet zum Benennen einer gesamten Muster in einem Mustervergleich.|
|`assert`|[Assertionen](assertions.md)|Zum Überprüfen von Code während des Debuggens verwendet.|
|`base`|[Klassen](classes.md)<br /><br />[Vererbung](inheritance.md)|Als Name des Objekts Basisklasse verwendet.|
|`begin`|[Ausführliche Syntax](verbose-syntax.md)|Gibt an den Anfang ein Codeblock, in ausführlicher Syntax.|
|`class`|[Klassen](classes.md)|In ausführlicher Syntax gibt den Anfang einer Klassendefinition.|
|`default`|[Mitglieder](members/index.md)|Zeigt eine Implementierung einer abstrakten Methode an. zusammen mit einer abstrakten Methodendeklaration verwendet, um eine virtuelle Methode zu erstellen.|
|`delegate`|[Delegaten](delegates.md)|Wird verwendet, um einen Delegaten zu deklarieren.|
|`do`|[do-Bindungen](functions/do-bindings.md)<br /><br />[Schleifen: `for...to` Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: `for...in` Ausdruck](loops-for-in-expression.md)<br /><br />[Schleifen: `while...do` Ausdruck](loops-while-do-expression.md)|In Schleifenkonstrukte oder zum Ausführen von imperativem Code verwendet.|
|`done`|[Ausführliche Syntax](verbose-syntax.md)|Gibt an das Ende eines Codeblocks in einem Ausdruck der Schleife, in ausführlicher Syntax.|
|`downcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Verwendet, um auf einen Typ zu konvertieren, die in der Vererbungskette niedriger ist.|
|`downto`|[Schleifen: `for...to` Ausdruck](loops-for-to-expression.md)|In einem `for` Ausdruck, der verwendet wird, wenn in umgekehrter Reihenfolge zu zählen.|
|`elif`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Bedingte Verzweigung verwendet. Eine Kurzform des `else if`.|
|`else`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Bedingte Verzweigung verwendet.|
|`end`|[Strukturen](structures.md)<br /><br />[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Datensätze](records.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Gibt an das Ende eines Abschnitts von Memberdefinitionen, in Typdefinitionen und Erweiterungen des Typs ist.<br /><br />In ausführlicher Syntax verwendet, um das Ende eines Codeblocks anzugeben, die mit beginnt die `begin` Schlüsselwort.|
|`exception`|[Ausnahmebehandlung](exception-handling/index.md)<br /><br />[Ausnahmetypen](exception-handling/exception-types.md)|Verwendet, um ein Ausnahmetyp deklariert.|
|`extern`|[Externe Funktionen](functions/external-functions.md)|Gibt an, dass ein deklariertes Programmelement in einem anderen binären oder einer Assembly definiert ist.|
|`false`|[Primitive Typen](primitive-types.md)|Als ein boolesches Literal verwendet.|
|`finally`|[Ausnahmen: Die `try...finally` Ausdruck](exception-handling/the-try-finally-expression.md)|Wird zusammen mit `try` Einführung ein Codeblocks, der ausgeführt wird, unabhängig davon, ob eine Ausnahme auftritt.|
|`fixed`|[behoben](fixed.md)|Verwendet einen Zeiger auf dem Stapel, um zu verhindern, dass der Garbage Collection "anheften".|
|`for`|[Schleifen: `for...to` Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)|In Schleifenkonstrukte verwendet.|
|`fun`|[Lambda-Ausdrücke: Das `fun`-Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md)|In Lambda-Ausdrücke, auch bekannt als anonyme Funktionen verwendet.|
|`function`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Lambda-Ausdrücke: Das Fun-Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md)|Als die kürzere Alternative verwendet die `fun` Schlüsselwort und `match` Ausdruck in einen Lambda-Ausdruck, der einen Musterabgleich für ein einzelnes Argument verfügt.|
|`global`|[Namespaces](namespaces.md)|Verwendet, um den Namespace der obersten Ebene .NET zu verweisen.|
|`if`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Bedingte Verzweigungen Konstrukte verwendet.|
|`in`|[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Verwendet von für Sequenzausdrücke und in ausführlicher Syntax zum Ausdrücken von Bindungen zu trennen.|
|`inherit`|[Vererbung](inheritance.md)|Dient zum Angeben von einer Basisklasse oder die Basisschnittstelle.|
|`inline`|[Funktionen](functions/index.md)<br /><br />[Inlinefunktionen](functions/inline-functions.md)|Verwendet, um anzugeben, dass ein, die direkt in der aufrufenden Code integriert werden soll.|
|`interface`|[Schnittstellen](interfaces.md)|Sie deklarieren und Implementieren von Schnittstellen verwendet.|
|`internal`|[Zugriffssteuerung](access-control.md)|Verwendet, um anzugeben, dass ein Element sichtbar ist innerhalb einer Assembly außerhalb davon hingegen nicht.|
|`lazy`|[Nicht strikte Ausdrücke](lazy-expressions.md)|Verwendet, um einen Ausdruck angeben, die ausgeführt werden, nur, wenn ein Ergebnis benötigt wird.|
|`let`|[`let` Bindungen](functions/let-bindings.md)|Zum Verknüpfen oder zu binden, einen Namen auf einen Wert oder die Funktion verwendet.|
|`let!`|[Asynchrone Workflows](asynchronous-workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Verwendet in asynchrone Workflows, um einen Namen auf das Ergebnis eine asynchrone Berechnung zu binden, oder, im anderen Berechnungsausdrücken verwendet, um einen Namen an ein Ergebnis zu binden, der den Typ der Berechnung wird.|
|`match`|[Vergleichsausdrücke](match-expressions.md)|Mit der Verzweigung von Vergleichen eines Werts mit einem Muster.|
|`match!`|[Berechnungsausdrücke](computation-expressions.md#match)|Verwendet, um Inline einen Aufruf zu einer Berechnung Ausdruck und das Muster auf ihr Ergebnis.|
|`member`|[Mitglieder](members/index.md)|Zum Deklarieren einer Eigenschaft oder Methode in einen Objekttyp verwendet.|
|`module`|[Module](modules.md)|Wird verwendet, um einen Namen mit einer Gruppe von verwandten Typen, Werte und Funktionen, damit sie von anderem Code logisch getrennt zuzuordnen.|
|`mutable`|[let-Bindungen](functions/let-bindings.md)|Wird verwendet, um eine Variable, d. h., einen Wert zu deklarieren, die geändert werden können.|
|`namespace`|[Namespaces](namespaces.md)|Wird verwendet, um einen Namen mit einer Gruppe von verwandten Typen und Module, damit sie von anderem Code logisch getrennt zuzuordnen.|
|`new`|[Konstruktoren](members/constructors.md)<br /><br />[Einschränkungen](generics/constraints.md)|Wird verwendet, um zu deklarieren, definieren Sie, oder rufen Sie einen Konstruktor, der erstellt oder ein Objekt erstellen kann.<br /><br />Auch verwendet in Einschränkungen für generische Typparameter, um anzugeben, dass ein Typ einen bestimmten Konstruktor besitzen muss.|
|`not`|[Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](generics/constraints.md)|Eigentlich kein Schlüsselwort. Allerdings `not struct` in Kombination dient als Einschränkung eines generischen Parameters.|
|`null`|[NULL-Werte](values/null-values.md)<br /><br />[Einschränkungen](generics/constraints.md)|Gibt das Fehlen eines Objekts an.<br /><br />Auch verwendet in Einschränkungen für generische Typparameter.|
|`of`|[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Delegaten](delegates.md)<br /><br />[Ausnahmetypen](exception-handling/exception-types.md)|In Unterscheidungs-Unions, um den Typ der Kategorien von Werten anzugeben, und klicken Sie in Deklarationen von Delegaten und der Ausnahme verwendet.|
|`open`|[Importdeklarationen: Das `open`-Schlüsselwort](import-declarations-the-open-keyword.md)|Verwendet, um den Inhalt von einem Namespace oder Modul ohne Qualifikation verfügbar zu machen.|
|`or`|[Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](generics/constraints.md)|Mit booleschen Bedingungen verwendet werden, als booleschen `or` Operator. Entspricht `||`.<br /><br />Auch verwendet in Membereinschränkungen.|
|`override`|[Mitglieder](members/index.md)|Verwendet, um eine Version einer abstrakten oder virtuellen Methode zu implementieren, der die Basisversion unterscheidet.|
|`private`|[Zugriffssteuerung](access-control.md)|Schränkt den Zugriff auf einen Member auf Code in den gleichen Typ oder Modul an.|
|`public`|[Zugriffssteuerung](access-control.md)|Ermöglicht den Zugriff auf einen Member von außerhalb des Typs.|
|`rec`|[Funktionen](functions/index.md)|Wird verwendet, um anzugeben, dass eine Funktion rekursiv ist.|
|`return`|[Asynchrone Workflows](Asynchronous-Workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Damit wird einen Wert, der als Ergebnis eines Ausdrucks für die Berechnung bereitgestellt angegeben.|
|`return!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Verwendet, um einen Ausdruck für die Berechnung anzugeben, dass bei der Auswertung, stellt das Ergebnis des Berechnungsausdrucks enthält.|
|`select`|[Abfrageausdrücke](query-expressions.md)|In Abfrageausdrücken verwendet, an welche Felder oder Spalten zu extrahieren. Beachten Sie, dass dies ein Kontextschlüsselwort, d. h., es ist dabei nicht um ein reserviertes Wort und es nur verhält sich wie ein Schlüsselwort in den entsprechenden Kontext.|
|`static`|[Mitglieder](members/index.md)|Damit wird angegeben, eine Methode oder Eigenschaft, die ohne eine Instanz eines Typs aufgerufen werden kann oder einem Wertmember, die von allen Instanzen eines Typs gemeinsam genutzt wird.|
|`struct`|[Strukturen](structures.md)<br /><br /> [Tupel](tuples.md)<br/><br/>[Einschränkungen](generics/constraints.md)|Wird verwendet, um einen Strukturtyp zu deklarieren.<br /><br/>Dient zum Angeben eines Tupels Struktur.<br/><br />Auch verwendet in Einschränkungen für generische Typparameter.<br /><br />Für die Kompatibilität mit OCaml in Moduldefinitionen verwendet.|
|`then`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Konstruktoren](members/constructors.md)|In bedingten Ausdrücken verwendet.<br /><br />Auch verwendet, um Nebeneffekte nach der objekterstellung.|
|`to`|[Schleifen: `for...to` Ausdruck](loops-for-to-expression.md)|Verwendet `for` Schleifen auf, um einen Bereich anzugeben.|
|`true`|[Primitive Typen](primitive-types.md)|Als ein boolesches Literal verwendet.|
|`try`|[Ausnahmen: Der try...with-Ausdruck](exception-handling/the-try-with-expression.md)<br /><br />[Ausnahmen: Der Versuch... try...finally-Ausdruck](exception-handling/the-try-finally-expression.md)|Verwendet, um einen Codeblock vorgestellt, die möglicherweise eine Ausnahme generiert. Wird zusammen mit `with` oder `finally`.|
|`type`|[F#-Typen](fsharp-types.md)<br /><br />[Klassen](classes.md)<br /><br />[Datensätze](records.md)<br /><br />[Strukturen](structures.md)<br /><br />[Enumerationen](enumerations.md)<br /><br />[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Typabkürzungen](type-abbreviations.md)<br /><br />[Maßeinheiten](units-of-measure.md)|Zum Deklarieren einer Klasse, Datensatz, Struktur, Unterscheidungs-Union, Enumerationstyp, Maßeinheit, oder geben Sie die Abkürzung verwendet.|
|`upcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Verwendet, um auf einen Typ zu konvertieren, der in der Vererbungskette höher ist.|
|`use`|[Ressourcenverwaltung: Das `use`-Schlüsselwort](resource-management-the-use-keyword.md)|Anstelle von `let` für Werte, die erfordern `Dispose` , aufgerufen werden, um Ressourcen freizugeben.|
|`use!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Anstelle von `let!` in asynchrone Workflows und anderen Berechnungsausdrücken für Werte, die erfordern `Dispose` , aufgerufen werden, um Ressourcen freizugeben.|
|`val`|[Explizite Felder: Das `val`-Schlüsselwort](members/explicit-fields-the-val-keyword.md)<br /><br />[Signaturen](signatures.md)<br /><br />[Mitglieder](members/index.md)|Verwendet in einer Signatur zum Angeben eines Werts oder in einem Typ um einen Member, in bestimmten Situationen deklarieren.|
|`void`|[Primitive Typen](primitive-types.md)|Gibt an, die .NET `void` Typ. Verwendet bei der Interaktion mit anderen .NET-Sprachen.|
|`when`|[Einschränkungen](generics/constraints.md)|Für die booleschen Bedingungen verwendet (*beim schützt*) bei musterübereinstimmungen und eine Einschränkungsklausel für einen generischen Typparameter einzuführen.|
|`while`|[Schleifen: `while...do` Ausdruck](loops-while-do-expression.md)|Führt eine Schleifenkonstruktion.|
|`with`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Objektausdrücke](object-expressions.md)<br /><br />[Kopieren und Aktualisieren von Datensatzausdrücken](copy-and-update-record-expressions.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausnahmen: Die `try...with` Ausdruck](exception-handling/the-try-with-expression.md)|Wird zusammen mit den `match` Schlüsselwort in musterabgleichsausdrücken. Auch verwendet in Object-Ausdrücke, Kopieren von Datensatzausdrücken und Erweiterungen des Typs, Memberdefinitionen einführen und Ausnahmehandler einführen.|
|`yield`|[Sequenzen](sequences.md)|In einem Sequenzausdruck verwendet, um einen Wert für eine Sequenz zu erzeugen.|
|`yield!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|In einem Berechnungsausdruck verwendet zum fügen Sie des Ergebnis eines Ausdrucks für die angegebene Berechnung auf eine Auflistung von Ergebnissen für den enthaltenden Ausdruck für die Berechnung.|

Die folgenden Token sind in F# reserviert werden, da sie in der Sprache mit OCaml Schlüsselwörter sind:

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

Bei Verwendung der `--mlcompatibility` -Compileroption verwenden, die oben aufgeführten Schlüsselwörter stehen zur Verwendung als Bezeichner.

Die folgenden Token werden als Schlüsselwörter für die zukünftige Erweiterung der Sprache F# reserviert:

* `atomic`
* `break`
* `checked`
* `component`
* `const`
* `constraint`
* `constructor`
* `continue`
* `eager`
* `event`
* `external`
* `functor`
* `include`
* `method`
* `mixin`
* `object`
* `parallel`
* `process`
* `protected`
* `pure`
* `sealed`
* `tailcall`
* `trait`
* `virtual`
* `volatile`

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)
- [Compileroptionen](compiler-options.md)
