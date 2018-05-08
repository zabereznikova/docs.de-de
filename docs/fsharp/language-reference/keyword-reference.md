---
title: Schlüsselwortreferenz (F#)
description: Suchen Sie Links zu Informationen über alle f#-Schlüsselwörter.
ms.date: 05/16/2016
ms.openlocfilehash: 2cb2fbb3236fcfeebc801b467d657f031b8da55a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="keyword-reference"></a>Schlüsselwortreferenz

Dieses Thema enthält Links zu Informationen über alle F#-Schlüsselwörter.

## <a name="f-keyword-table"></a>Table-Schlüsselwort [F#]

Die folgende Tabelle zeigt alle F#-Schlüsselwörter in alphabetischer Reihenfolge, zusammen mit kurzen Beschreibungen und Links zu relevanten Themen, die Weitere Informationen enthalten.

|Stichwort|Link|Beschreibung|
|-------|----|-----------|
|`abstract`|[Mitglieder](members/index.md)<br /><br />[Abstrakte Klassen](abstract-classes.md)|Gibt eine Methode, die keine Implementierung entweder im Typ aufweist, in dem sie deklariert ist, oder die ist virtuell und einer standardmäßigen Implementierung.|
|`and`|[`let` Bindungen](functions/let-bindings.md)<br /><br />[Mitglieder](members/index.md)<br /><br />[Einschränkungen](generics/constraints.md)|Wechselseitig rekursive Bindungen in Eigenschaftendeklarationen sowie mit mehrere Einschränkungen für generische Parameter verwendet.|
|`as`|[Klassen](classes.md)<br /><br />[Mustervergleich](Pattern-Matching.md)|Verwendet, um dem aktuelle Klassenobjekt ein Objekt benennen. Auch verwendet zum Benennen einer gesamten Muster in einem Mustervergleich.|
|`assert`|[Assertionen](assertions.md)|Zum Überprüfen von Code während des Debuggens verwendet.|
|`base`|[Klassen](classes.md)<br /><br />[Vererbung](inheritance.md)|Als Name des Objekts Basisklasse verwendet.|
|`begin`|[Ausführliche Syntax](verbose-syntax.md)|Gibt an den Anfang eines Codeblocks, in ausführlicher Syntax.|
|`class`|[Klassen](classes.md)|In ausführlicher Syntax gibt den Anfang einer Klassendefinition.|
|`default`|[Mitglieder](members/index.md)|Zeigt eine Implementierung einer abstrakten Methode an. zusammen mit einer abstrakten Methodendeklaration verwendet, um eine virtuelle Methode zu erstellen.|
|`delegate`|[Delegaten](delegates.md)|Wird verwendet, um einen Delegaten zu deklarieren.|
|`do`|[do-Bindungen](functions/do-bindings.md)<br /><br />[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)<br /><br />[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|In Schleifenkonstrukte oder zum Ausführen von imperativen Codes verwendet.|
|`done`|[Ausführliche Syntax](verbose-syntax.md)|In ausführlicher Syntax gibt das Ende eines Codeblocks in einem Schleifenausdruck.|
|`downcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Verwendet, um auf einen Typ zu konvertieren, der in der Vererbungskette kleiner ist.|
|`downto`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|In einem `for` Ausdruck, der bei der Inventur in umgekehrter Reihenfolge verwendet.|
|`elif`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Bedingte Verzweigung verwendet. Kurzform von `else if`.|
|`else`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Bedingte Verzweigung verwendet.|
|`end`|[Strukturen](structures.md)<br /><br />[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Datensätze](records.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Gibt an das Ende eines Abschnitts Memberdefinitionen, Typdefinitionen und Erweiterungen.<br /><br />In ausführlicher Syntax verwendet, um das Ende eines Codeblocks anzugeben, die mit beginnt die `begin` Schlüsselwort.|
|`exception`|[Ausnahmebehandlung](exception-handling/index.md)<br /><br />[Ausnahmetypen](exception-handling/exception-types.md)|Wird verwendet, um einen Ausnahmetyp zu deklarieren.|
|`extern`|[Externe Funktionen](functions/external-functions.md)|Gibt an, dass ein Programmelement deklariert in einem anderen binären oder Assembly definiert ist.|
|`false`|[Primitive Typen](primitive-types.md)|Als ein boolesches Literal verwendet.|
|`finally`|[Ausnahmen: Der `try...finally`-Ausdruck](exception-handling/the-try-finally-expression.md)|Zusammen mit `try` einen Codeblock einführen, die ausgeführt wird, unabhängig davon, ob eine Ausnahme auftritt.|
|`fixed`|[feste](fixed.md)|Verwendet einen Zeiger auf den Stapel, um zu verhindern, dass der Garbage Collection "anheften".|
|`for`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)|Verwendet in Schleifenkonstrukte.|
|`fun`|[Lambda-Ausdrücke: Das `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md)|In Lambda-Ausdrücke, auch bekannt als anonyme Funktionen verwendet.|
|`function`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Lambda-Ausdrücke: Das Fun-Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md)|Als Alternative zu kürzeren verwendet die `fun` Schlüsselwort und ein `match` Ausdruck in einem Lambda-Ausdruck, der einen Mustervergleich für ein einzelnes Argument verfügt.|
|`global`|[Namespaces](namespaces.md)|Der Namespace der obersten Ebene .NET verweisen auf verwendet.|
|`if`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)|Bedingte Verzweigung Konstrukte verwendet.|
|`in`|[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Verwendet für Sequenzausdrücke und ausführliche Syntax zum Ausdrücken von Bindungen zu trennen.|
|`inherit`|[Vererbung](inheritance.md)|Wird verwendet, um eine Basisklasse oder die Basisschnittstelle anzugeben.|
|`inline`|[Funktionen](functions/index.md)<br /><br />[Inlinefunktionen](functions/inline-functions.md)|Verwendet, um eine Funktion anzugeben, die direkt in der aufrufenden Code integriert werden sollten.|
|`interface`|[Schnittstellen](interfaces.md)|Deklarieren und Implementieren von Schnittstellen verwendet.|
|`internal`|[Zugriffssteuerung](access-control.md)|Verwendet, um anzugeben, dass ein Element sichtbar ist innerhalb einer Assembly, aber nicht außerhalb davon.|
|`lazy`|[Verzögerte Berechnungen](lazy-computations.md)|Wird verwendet, um eine Berechnung anzugeben, die ausgeführt werden soll, nur, wenn ein Ergebnis benötigt wird.|
|`let`|[`let` Bindungen](functions/let-bindings.md)|Zum zuordnen, oder binden Sie einen Namen auf einen Wert oder eine Funktion verwendet.|
|`let!`|[Asynchrone Workflows](asynchronous-workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Verwendet in asynchrone Workflows einen Namen für das Ergebnis von eine asynchrone Berechnung zu binden oder in anderen Berechnungsausdrücke verwendet, um einen Namen zu einem Ergebnis zu binden, die Berechnung Typ aufweist.|
|`match`|[Vergleichsausdrücke](match-expressions.md)|Verwendet zum Verzweigen durch Vergleichen eines Werts mit einem Muster.|
|`member`|[Mitglieder](members/index.md)|Wird verwendet, um einer Eigenschaft oder Methode in einen Typ deklarieren.|
|`module`|[Module](modules.md)|Wird verwendet, um einen Namen mit einer Gruppe von verwandten Typen, Werte und Funktionen, um logisch aus anderem Code zu trennen zuzuordnen.|
|`mutable`|[let-Bindungen](functions/let-bindings.md)|Verwendet, um eine Variable, d. h. einen Wert zu deklarieren, die geändert werden können.|
|`namespace`|[Namespaces](namespaces.md)|Wird verwendet, um einen Namen mit einer Gruppe von verwandten Typen und Module, um logisch aus anderem Code zu trennen zuzuordnen.|
|`new`|[Konstruktoren](members/constructors.md)<br /><br />[Einschränkungen](generics/constraints.md)|Wird verwendet, um zu deklarieren, definieren Sie, oder rufen Sie einen Konstruktor, der erstellt oder ein Objekt erstellen kann.<br /><br />Auch verwendet in Einschränkungen für generische Typparameter, um anzugeben, dass ein Typ einen bestimmten Konstruktor besitzen muss.|
|`not`|[Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](generics/constraints.md)|Eigentlich kein Schlüsselwort. Allerdings `not struct` in Kombination wird als Einschränkung eines generischen Parameters verwendet.|
|`null`|[NULL-Werte](values/null-values.md)<br /><br />[Einschränkungen](generics/constraints.md)|Gibt das Fehlen eines Objekts an.<br /><br />Auch verwendet in den Einschränkungen für generische Typparameter.|
|`of`|[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Delegaten](delegates.md)<br /><br />[Ausnahmetypen](exception-handling/exception-types.md)|In Unterscheidungs-Unions, um den Typ der Kategorien von Werten anzugeben, und klicken Sie in Deklarationen von Delegaten und der Ausnahme verwendet.|
|`open`|[Importdeklarationen: Das `open`-Schlüsselwort](import-declarations-the-open-keyword.md)|Verwendet, um den Inhalt von einem Namespace oder Modul ohne Qualifizierung verfügbar zu machen.|
|`or`|[Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](generics/constraints.md)|Mit wahrheitsbedingungen verwendet wird, als boolescher Wert `or` Operator. Entspricht "||`.<br /><br />Auch verwendet in Membereinschränkungen.|
|`override`|[Mitglieder](members/index.md)|Verwendet eine Version einer abstrakten oder virtuellen Methode implementiert, die von der Basisversion abweicht.|
|`private`|[Zugriffssteuerung](access-control.md)|Schränkt den Zugriff auf einen Member für Code in den gleichen Typ oder Modul an.|
|`public`|[Zugriffssteuerung](access-control.md)|Ermöglicht den Zugriff auf einen Member von außerhalb des Typs.|
|`rec`|[Funktionen](functions/index.md)|Verwendet, um anzugeben, dass eine Funktion rekursiv ist.|
|`return`|[Asynchrone Workflows](Asynchronous-Workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Zum Angeben eines Werts, geben Sie als Ergebnis eines Ausdrucks für die Berechnung verwendet.|
|`return!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Verwendet, um einen Ausdruck für die Berechnung anzugeben, dass bei der Auswertung enthält das Ergebnis des enthaltenden Berechnungsausdrucks.|
|`select`|[Abfrageausdrücke](query-expressions.md)|Verwendet in Abfrageausdrücken an, welche Felder oder Spalten zu extrahieren. Beachten Sie, dass dies ein Kontextabhängiges Schlüsselwort, d. h. es ist nicht tatsächlich ein reserviertes Wort und es nur verhält sich wie ein Schlüsselwort im entsprechenden Kontext.|
|`static`|[Mitglieder](members/index.md)|Wird verwendet, um anzugeben, eine Methode oder Eigenschaft, die ohne eine Instanz eines Typs aufgerufen werden kann oder ein Wertemember, die von allen Instanzen eines Typs gemeinsam genutzt wird.|
|`struct`|[Strukturen](structures.md)<br /><br />[Einschränkungen](generics/constraints.md)|Wird verwendet, um einen Strukturtyp zu deklarieren.<br /><br />Auch verwendet in den Einschränkungen für generische Typparameter.<br /><br />Für die Kompatibilität mit OCaml in Moduldefinitionen verwendet.|
|`then`|[Bedingte Ausdrücke: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Konstruktoren](members/constructors.md)|In bedingten Ausdrücken verwendet.<br /><br />Verwendet auch Nebeneffekte nach Objektkonstruktion ausgeführt.|
|`to`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|Verwendet `for` Schleifen, um einen Bereich anzugeben.|
|`true`|[Primitive Typen](primitive-types.md)|Als ein boolesches Literal verwendet.|
|`try`|[Ausnahmen: Der try...with-Ausdruck](exception-handling/the-try-with-expression.md)<br /><br />[Ausnahmen: Wiederholen Sie dann... try...finally-Ausdruck](exception-handling/the-try-finally-expression.md)|Verwendet, um einen Codeblock einführen, die möglicherweise eine Ausnahme generiert. Zusammen mit `with` oder `finally`.|
|`type`|[F#-Typen](fsharp-types.md)<br /><br />[Klassen](classes.md)<br /><br />[Datensätze](records.md)<br /><br />[Strukturen](structures.md)<br /><br />[Enumerationen](enumerations.md)<br /><br />[Unterscheidbare Unions](discriminated-unions.md)<br /><br />[Typabkürzungen](type-abbreviations.md)<br /><br />[Maßeinheiten](units-of-measure.md)|Zum Deklarieren einer Klasse, Datensatz, Struktur, Unterscheidungs-Union, Enumerationstyp, Maßeinheit, oder geben Sie die Abkürzung verwendet.|
|`upcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Verwendet, um auf einen Typ zu konvertieren, der in der Vererbungskette höher ist.|
|`use`|[Ressourcenverwaltung: Das `use`-Schlüsselwort](resource-management-the-use-keyword.md)|Anstelle von `let` für Werte, die erfordern `Dispose` , aufgerufen werden, um Ressourcen freizugeben.|
|`use!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Anstelle von `let!` in asynchronen Workflows und anderen Berechnungsausdrücken für Werte, die erfordern `Dispose` , aufgerufen werden, um Ressourcen freizugeben.|
|`val`|[Explizite Felder: Das `val`-Schlüsselwort](members/explicit-fields-the-val-keyword.md)<br /><br />[Signaturen](signatures.md)<br /><br />[Mitglieder](members/index.md)|In einer Signatur zum Angeben eines Werts oder in einem Typ deklariert ein Element im eingeschränkten Situationen verwendet.|
|`void`|[Primitive Typen](primitive-types.md)|Gibt den `void` Typ. Verwendet bei der Interaktion mit anderen .NET-Sprachen.|
|`when`|[Einschränkungen](generics/constraints.md)|Verwendet für wahrheitsbedingungen (*Wenn Wächter*) auf musterübereinstimmungen und eine Einschränkungsklausel für einen generischen Typparameter einzuführen.|
|`while`|[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Führt eine Schleifenkonstruktion.|
|`with`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Objektausdrücke](object-expressions.md)<br /><br />[Kopieren und Aktualisieren von Datensatzausdrücken](copy-and-update-record-expressions.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausnahmen: Der `try...with`-Ausdruck](exception-handling/the-try-with-expression.md)|Zusammen mit den `match` Schlüsselwort in Mustervergleichsausdrücken. Auch verwendet in Objektausdrücke, Datensatz von Ausdrücken und typerweiterungen Memberdefinitionen einzuführen und Ausnahmehandler einzuführen.|
|`yield`|[Sequenzen](sequences.md)|Verwendet in einem Sequenzausdruck zur Erzeugung eines Werts für eine Sequenz.|
|`yield!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Verwendet in einen Ausdruck für die Berechnung auf das Ergebnis eines Ausdrucks für die angegebene Berechnung an eine Auflistung von Ergebnissen für den enthaltenden Berechnungsausdrucks angefügt werden soll.|

Die folgenden Token sind in f# reserviert werden, da sie Schlüsselwörter in der Sprache mit OCaml sind:

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

Bei Verwendung der `--mlcompatibility` (Compileroption), die oben aufgeführten Schlüsselwörter stehen zur Verwendung als Bezeichner.

Die folgenden Token sind als Schlüsselwörter für zukünftige Erweiterungen der Programmiersprache f# reserviert:

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
* `fixed`
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
[F#-Sprachreferenz](index.md)

[Symbol- und Operatorenreferenz](symbol-and-operator-reference/index.md)

[Compileroptionen](compiler-options.md)
