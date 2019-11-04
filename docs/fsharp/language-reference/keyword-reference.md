---
title: Schlüsselwortreferenz
description: Hier finden Sie Links zu Informationen über alle F# sprach Schlüsselwörter.
ms.date: 05/16/2016
ms.openlocfilehash: 2be6d078653a4595cbdfe97be7aab8e3b3c10ea9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425087"
---
# <a name="keyword-reference"></a>Schlüsselwortreferenz

Dieses Thema enthält Links zu Informationen über alle F# sprach Schlüsselwörter.

## <a name="f-keyword-table"></a>F#Schlüsselwort Tabelle

In der folgenden Tabelle werden F# Alle Schlüsselwörter in alphabetischer Reihenfolge sowie kurze Beschreibungen und Links zu relevanten Themen angezeigt, die weitere Informationen enthalten.

|Stichwort|Link|Beschreibung|
|-------|----|-----------|
|`abstract`|[Mitglieder](./members/index.md)<br /><br />[Abstrakte Klassen](abstract-classes.md)|Gibt eine Methode an, die entweder keine Implementierung in dem Typ hat, in dem Sie deklariert ist oder virtuell ist und über eine Standard Implementierung verfügt.|
|`and`|[`let` Bindungen](./functions/let-bindings.md)<br /><br />[Datensätze](records.md)<br /><br />[Mitglieder](./members/index.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Wird für gegenseitig rekursive Bindungen und Datensätze, in Eigenschafts Deklarationen und mit mehreren Einschränkungen für generische Parameter verwendet.|
|`as`|[Klassen](classes.md)<br /><br />[Mustervergleich](Pattern-Matching.md)|Wird verwendet, um dem aktuellen Klassenobjekt einen Objektnamen zu übergeben. Wird auch verwendet, um einem gesamten Muster einen Namen innerhalb einer Muster Übereinstimmung zu übergeben.|
|`assert`|[Assertionen](assertions.md)|Dient zum Überprüfen von Code während des Debuggens.|
|`base`|[Klassen](classes.md)<br /><br />[Vererbung](inheritance.md)|Wird als Name des Basisklassen Objekts verwendet.|
|`begin`|[Ausführliche Syntax](verbose-syntax.md)|Gibt in ausführlicher Syntax den Anfang eines Code Blocks an.|
|`class`|[Klassen](classes.md)|Gibt in ausführlicher Syntax den Anfang einer Klassendefinition an.|
|`default`|[Mitglieder](./members/index.md)|Gibt eine Implementierung einer abstrakten Methode an. wird zusammen mit einer abstrakten Methoden Deklaration zum Erstellen einer virtuellen Methode verwendet.|
|`delegate`|[Delegaten](delegates.md)|Wird zum Deklarieren eines Delegaten verwendet.|
|`do`|[do-Bindungen](./functions/do-bindings.md)<br /><br />[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)<br /><br />[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Wird in Schleifen Konstrukten oder zum Ausführen von imperativem Code verwendet.|
|`done`|[Ausführliche Syntax](verbose-syntax.md)|Gibt in ausführlicher Syntax das Ende eines Code Blocks in einem Schleifen Ausdruck an.|
|`downcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Wird verwendet, um in einen Typ zu konvertieren, der in der Vererbungs Kette niedriger ist.|
|`downto`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|In einem `for` Ausdruck verwendet, wenn in umgekehrter Reihenfolge gezählt wird.|
|`elif`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Wird bei der bedingten Verzweigung verwendet. Eine Kurzform `else if`.|
|`else`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Wird bei der bedingten Verzweigung verwendet.|
|`end`|[Strukturen](structures.md)<br /><br />[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Datensätze](records.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Gibt in Typdefinitionen und Typerweiterungen das Ende eines Abschnitts von Element Definitionen an.<br /><br />In ausführlicher Syntax wird verwendet, um das Ende eines Code Blocks anzugeben, der mit dem `begin`-Schlüsselwort beginnt.|
|`exception`|[Ausnahmebehandlung](./exception-handling/index.md)<br /><br />[Ausnahmetypen](./exception-handling/exception-types.md)|Wird verwendet, um einen Ausnahmetyp zu deklarieren.|
|`extern`|[Externe Funktionen](./functions/external-functions.md)|Gibt an, dass ein deklariertes Programmelement in einer anderen Binärdatei oder Assembly definiert ist.|
|`false`|[Primitive Typen](basic-types.md)|Wird als boolesches Literale verwendet.|
|`finally`|[Ausnahmen: Der `try...finally`-Ausdruck](./exception-handling/the-try-finally-expression.md)|Wird in Verbindung mit `try` verwendet, um einen Codeblock einzuführen, der unabhängig davon ausgeführt wird, ob eine Ausnahme auftritt.|
|`fixed`|[Festen](fixed.md)|Wird verwendet, um einen Zeiger auf den Stapel zu "anheften", um eine Garbage Collection zu verhindern.|
|`for`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)|Wird in Schleifen Konstrukten verwendet.|
|`fun`|[Lambda-Ausdrücke: das `fun`-Schlüsselwort](./functions/lambda-expressions-the-fun-keyword.md)|Wird in Lambda Ausdrücken verwendet, auch als anonyme Funktionen bezeichnet.|
|`function`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Lambda-Ausdrücke: das fun-Schlüsselwort](./functions/lambda-expressions-the-fun-keyword.md)|Wird als kürzere Alternative zum `fun`-Schlüsselwort und einem `match` Ausdruck in einem Lambda Ausdruck verwendet, der einen Muster Vergleich für ein einzelnes Argument aufweist.|
|`global`|[Namespaces](namespaces.md)|Wird verwendet, um auf den .NET-Namespace der obersten Ebene zu verweisen.|
|`if`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Wird in bedingten Verzweigungs Konstrukten verwendet.|
|`in`|[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Wird für Sequenz Ausdrücke und in ausführlicher Syntax zum Trennen von Ausdrücken von Bindungen verwendet.|
|`inherit`|[Vererbung](inheritance.md)|Wird verwendet, um eine Basisklasse oder Basisschnittstelle anzugeben.|
|`inline`|[Funktionen](./functions/index.md)<br /><br />[Inlinefunktionen](./functions/inline-functions.md)|Wird verwendet, um eine Funktion anzugeben, die direkt in den Code des Aufrufers integriert werden soll.|
|`interface`|[Schnittstellen](interfaces.md)|Wird zum Deklarieren und Implementieren von Schnittstellen verwendet.|
|`internal`|[Zugriffssteuerung](access-control.md)|Wird verwendet, um anzugeben, dass ein Member innerhalb einer Assembly, aber nicht außerhalb des Elements sichtbar ist.|
|`lazy`|[Nicht strikte Ausdrücke](lazy-expressions.md)|Wird verwendet, um einen Ausdruck anzugeben, der nur ausgeführt werden soll, wenn ein Ergebnis benötigt wird.|
|`let`|[`let` Bindungen](./functions/let-bindings.md)|Wird verwendet, um einen Namen einem Wert oder einer Funktion zuzuordnen oder zu binden.|
|`let!`|[Asynchrone Workflows](asynchronous-workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Wird in asynchronen Workflows verwendet, um einen Namen an das Ergebnis einer asynchronen Berechnung zu binden, oder in anderen Berechnungs Ausdrücken, die zum Binden eines Namens an ein Ergebnis des Berechnungs Typs verwendet werden.|
|`match`|[Vergleichsausdrücke](match-expressions.md)|Wird zum Verzweigen verwendet, indem ein-Wert mit einem Muster verglichen wird.|
|`match!`|[Berechnungsausdrücke](computation-expressions.md#match)|Wird verwendet, um einen aufzurufenden Berechnungs Ausdruck aufzurufen und Muster Übereinstimmungen für das Ergebnis zu erreichen|
|`member`|[Mitglieder](./members/index.md)|Wird verwendet, um eine Eigenschaft oder Methode in einem Objekttyp zu deklarieren.|
|`module`|[Module](modules.md)|Wird verwendet, um einen Namen einer Gruppe verwandter Typen, Werte und Funktionen zuzuordnen, um ihn logisch von anderem Code zu trennen.|
|`mutable`|[let-Bindungen](./functions/let-bindings.md)|Wird verwendet, um eine Variable zu deklarieren, d. h. einen Wert, der geändert werden kann.|
|`namespace`|[Namespaces](namespaces.md)|Wird verwendet, um einen Namen einer Gruppe verwandter Typen und Modulen zuzuordnen, um ihn logisch von anderem Code zu trennen.|
|`new`|[Konstruktoren](./members/constructors.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Wird verwendet, um einen Konstruktor zu deklarieren, zu definieren oder aufzurufen, mit dem ein Objekt erstellt oder erstellt werden kann.<br /><br />Wird auch in generischen Parameter Einschränkungen verwendet, um anzugeben, dass ein Typ über einen bestimmten Konstruktor verfügen muss.|
|`not`|[Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Nicht tatsächlich ein Schlüsselwort. Allerdings wird `not struct` in Kombination als generische Parameter Einschränkung verwendet.|
|`null`|[NULL-Werte](./values/null-values.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Gibt an, dass ein Objekt nicht vorhanden ist.<br /><br />Wird auch in generischen Parameter Einschränkungen verwendet.|
|`of`|[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Delegaten](delegates.md)<br /><br />[Ausnahmetypen](./exception-handling/exception-types.md)|Wird in Unterscheidungs-Unions verwendet, um den Typ der Kategorien von Werten anzugeben, und in Delegaten-und Ausnahme Deklarationen.|
|`open`|[Importdeklarationen: Das `open`-Schlüsselwort](import-declarations-the-open-keyword.md)|Wird verwendet, um den Inhalt eines Namespaces oder Moduls ohne Qualifizierung verfügbar zu machen.|
|`or`|[Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Wird mit booleschen Bedingungen als boolescher `or` Operator verwendet. Entspricht `||`.<br /><br />Wird auch in Member-Einschränkungen verwendet.|
|`override`|[Mitglieder](./members/index.md)|Wird verwendet, um eine Version einer abstrakten oder virtuellen Methode zu implementieren, die sich von der Basisversion unterscheidet.|
|`private`|[Zugriffssteuerung](access-control.md)|Schränkt den Zugriff auf einen Member auf Code im gleichen Typ oder Modul ein.|
|`public`|[Zugriffssteuerung](access-control.md)|Ermöglicht den Zugriff auf einen Member außerhalb des Typs.|
|`rec`|[Funktionen](./functions/index.md)|Wird verwendet, um anzugeben, dass eine Funktion rekursiv ist.|
|`return`|[Asynchrone Workflows](Asynchronous-Workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Wird verwendet, um einen Wert anzugeben, der als Ergebnis eines Berechnungs Ausdrucks bereitgestellt werden soll.|
|`return!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Wird verwendet, um einen Berechnungs Ausdruck anzugeben, der bei der Auswertung das Ergebnis des enthaltenden Berechnungs Ausdrucks bereitstellt.|
|`select`|[Abfrageausdrücke](query-expressions.md)|Wird in Abfrage Ausdrücken verwendet, um anzugeben, welche Felder oder Spalten extrahiert werden sollen. Beachten Sie, dass es sich hierbei um ein kontextbezogenes Schlüsselwort handelt. Dies bedeutet, dass es sich nicht um ein reserviertes Wort handelt, sondern nur wie ein Schlüsselwort im entsprechenden Kontext|
|`static`|[Mitglieder](./members/index.md)|Wird verwendet, um eine Methode oder Eigenschaft anzugeben, die ohne eine Instanz eines Typs aufgerufen werden kann, oder ein Wertmember, der von allen Instanzen eines Typs gemeinsam verwendet wird.|
|`struct`|[Strukturen](structures.md)<br /><br /> [Tupel](tuples.md)<br/><br/>[Einschränkungen](./generics/constraints.md)|Wird verwendet, um einen Strukturtyp zu deklarieren.<br /><br/>Wird verwendet, um ein strukturtupel anzugeben.<br/><br />Wird auch in generischen Parameter Einschränkungen verwendet.<br /><br />Wird für die ocaml-Kompatibilität in Modul Definitionen verwendet.|
|`then`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Konstruktoren](./members/constructors.md)|Wird in bedingten Ausdrücken verwendet.<br /><br />Wird auch verwendet, um Nebeneffekte nach der Objekt Erstellung auszuführen.|
|`to`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|Wird in `for` Schleifen verwendet, um einen Bereich anzugeben.|
|`true`|[Primitive Typen](basic-types.md)|Wird als boolesches Literale verwendet.|
|`try`|[Ausnahmen: der Try... with-Ausdruck](./exception-handling/the-try-with-expression.md)<br /><br />[Ausnahmen: der Try... Ausdruck zum Schluss](./exception-handling/the-try-finally-expression.md)|Wird verwendet, um einen Codeblock einzuführen, der möglicherweise eine Ausnahme generiert. Wird in Verbindung mit `with` oder `finally`verwendet.|
|`type`|[F#-Typen](fsharp-types.md)<br /><br />[Klassen](classes.md)<br /><br />[Datensätze](records.md)<br /><br />[Strukturen](structures.md)<br /><br />[Enumerationen](enumerations.md)<br /><br />[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Typabkürzungen](type-abbreviations.md)<br /><br />[Maßeinheiten](units-of-measure.md)|Dient zum Deklarieren einer Klasse, eines Datensatzes, einer Struktur, einer Unterscheidungs Union, eines Enumerationstyps, einer Maßeinheit oder einer typabkürzung.|
|`upcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Wird verwendet, um in einen Typ zu konvertieren, der in der Vererbungs Kette höher ist.|
|`use`|[Ressourcenverwaltung: Das `use`-Schlüsselwort](resource-management-the-use-keyword.md)|Wird anstelle von `let` für Werte verwendet, die erfordern, dass `Dispose` aufgerufen werden, um Ressourcen freizugeben.|
|`use!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Wird anstelle von `let!` in asynchronen Workflows und anderen Berechnungs Ausdrücken für Werte verwendet, die erfordern, dass `Dispose` aufgerufen werden, um Ressourcen freizugeben.|
|`val`|[Explizite Felder: Das `val`-Schlüsselwort](./members/explicit-fields-the-val-keyword.md)<br /><br />[Signaturen](signature-files.md)<br /><br />[Mitglieder](./members/index.md)|Wird in einer Signatur verwendet, um einen Wert anzugeben, oder in einem Typ, um einen Member in eingeschränkten Situationen zu deklarieren.|
|`void`|[Primitive Typen](basic-types.md)|Gibt den .net-`void` Typ an. Wird verwendet, wenn mit anderen .NET-Sprachen interagiert wird.|
|`when`|[Einschränkungen](./generics/constraints.md)|Wird für boolesche Bedingungen (*Wenn Wächter*) für Muster Übereinstimmungen verwendet und eine Einschränkungs Klausel für einen generischen Typparameter eingeführt.|
|`while`|[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Führt ein Schleifen Konstrukt ein.|
|`with`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Objektausdrücke](object-expressions.md)<br /><br />[Kopieren und Aktualisieren von Datensatzausdrücken](copy-and-update-record-expressions.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausnahmen: Der `try...with`-Ausdruck](./exception-handling/the-try-with-expression.md)|Wird in Übereinstimmung mit dem `match`-Schlüsselwort in Muster Vergleichs Ausdrücken verwendet. Wird auch in Objekt Ausdrücken verwendet, das Kopieren von Ausdrücken und die Typerweiterungen zum Einführen von Element Definitionen und das Einführen von Ausnahme Handlern.|
|`yield`|[Sequenzen](sequences.md)|Wird in einem Sequenz Ausdruck verwendet, um einen Wert für eine Sequenz zu erhalten.|
|`yield!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Wird in einem Berechnungs Ausdruck verwendet, um das Ergebnis eines angegebenen Berechnungs Ausdrucks an eine Auflistung von Ergebnissen für den enthaltenden Berechnungs Ausdruck anzufügen.|

Die folgenden Token sind in F# reserviert, weil Sie Schlüsselwörter in der ocaml-Sprache sind:

- `asr`
- `land`
- `lor`
- `lsl`
- `lsr`
- `lxor`
- `mod`
- `sig`

Wenn Sie die `--mlcompatibility`-Compileroption verwenden, sind die obigen Schlüsselwörter zur Verwendung als Bezeichner verfügbar.

Die folgenden Token sind als Schlüsselwörter für zukünftige Erweiterungen der F# Sprache reserviert:

- `atomic`
- `break`
- `checked`
- `component`
- `const`
- `constraint`
- `constructor`
- `continue`
- `eager`
- `event`
- `external`
- `functor`
- `include`
- `method`
- `mixin`
- `object`
- `parallel`
- `process`
- `protected`
- `pure`
- `sealed`
- `tailcall`
- `trait`
- `virtual`
- `volatile`

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)
- [Compileroptionen](compiler-options.md)
