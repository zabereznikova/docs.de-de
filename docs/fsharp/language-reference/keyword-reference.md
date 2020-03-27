---
title: Schlüsselwortreferenz
description: Hier finden Sie Links zu Informationen zu allen Schlüsselwörtern in der Sprache F.
f1_keywords:
- new_FS
- use_FS
- end_FS
- lsl_FS
- exception_FS
- asr_FS
- if_FS
- internal_FS
- default_FS
- in_FS
- lsr_FS
- open_FS
- static_FS
- assert_FS
- match_FS
- land_FS
- with_FS
- inherit_FS
- mutable_FS
- downto_FS
- false_FS
- sig_FS
- and_FS
- true_FS
- namespace_FS
- public_FS
- lxor_FS
- val_FS
- void_FS
- downcast_FS
- function_FS
- while_FS
- for_FS
- class_FS
- done_FS
- to_FS
- module_FS
- let_FS
- delegate_FS
- abstract_FS
- then_FS
- when_FS
- lazy_FS
- try_FS
- inline_FS
- do_FS
- upcast_FS
- begin_FS
- base_FS
- fun_FS
- struct_FS
- as_FS
- extern_FS
- null_FS
- lor_FS
- return_FS
- mod_FS
- private_FS
- of_FS
- or_FS
- member_FS
- type_FS
- rec_FS
- elif_FS
- override_FS
- interface_FS
- yield_FS
- else_FS
- finally_FS
- global_FS
- select_FS
- use!_FS
dev_langs:
- FSharp
ms.date: 11/04/2019
ms.openlocfilehash: 34959f471406643e85990c2c80a38a684759a7f9
ms.sourcegitcommit: b16eacb6f94a5b601882a861ad17cc5470a8d5d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80352306"
---
# <a name="keyword-reference"></a>Schlüsselwortreferenz

Dieses Thema enthält Links zu Informationen zu allen Schlüsselwörtern der Sprache F.

## <a name="f-keyword-table"></a>Schlüsselworttabelle

In der folgenden Tabelle sind alle Schlüsselwörter in alphabetischer Reihenfolge sowie kurze Beschreibungen und Links zu relevanten Themen mit weiteren Informationen aufgeführt.

|Schlüsselwort|Link|Beschreibung|
|-------|----|-----------|
|`abstract`|[Member](./members/index.md)<br /><br />[Abstrakte Klassen](abstract-classes.md)|Gibt eine Methode an, die entweder keine Implementierung in dem Typ hat, in dem sie deklariert wird, oder die virtuell ist und über eine Standardimplementierung verfügt.|
|`and`|[`let`Bindungen](./functions/let-bindings.md)<br /><br />[Datensätze](records.md)<br /><br />[Member](./members/index.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Wird in rekursiven Bindungen und Datensätzen, in Eigenschaftsdeklarationen und mit mehreren Einschränkungen für generische Parameter verwendet.|
|`as`|[Klassen](classes.md)<br /><br />[Musterabgleich](Pattern-Matching.md)|Wird verwendet, um dem aktuellen Klassenobjekt einen Objektnamen zu geben. Wird auch verwendet, um einem ganzen Muster innerhalb einer Musterübereinstimmung einen Namen zu geben.|
|`assert`|[Assertionen](assertions.md)|Wird verwendet, um Code während des Debuggens zu überprüfen.|
|`base`|[Klassen](classes.md)<br /><br />[Vererbung](inheritance.md)|Wird als Name des Basisklassenobjekts verwendet.|
|`begin`|[Ausführliche Syntax](verbose-syntax.md)|Gibt in der ausführlichen Syntax den Anfang eines Codeblocks an.|
|`class`|[Klassen](classes.md)|Gibt in der ausführlichen Syntax den Anfang einer Klassendefinition an.|
|`default`|[Member](./members/index.md)|Gibt eine Implementierung einer abstrakten Methode an. zusammen mit einer abstrakten Methodendeklaration verwendet, um eine virtuelle Methode zu erstellen.|
|`delegate`|[Delegaten](delegates.md)|Wird verwendet, um einen Delegaten zu deklarieren.|
|`do`|[do-Bindungen](./functions/do-bindings.md)<br /><br />[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: `for...in`-Ausdruck](loops-for-in-expression.md)<br /><br />[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Wird in Schleifenkonstrukten oder zum Ausführen von Imperativecode verwendet.|
|`done`|[Ausführliche Syntax](verbose-syntax.md)|Gibt in der ausführlichen Syntax das Ende eines Codeblocks in einem Schleifenausdruck an.|
|`downcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Wird zum Konvertieren in einen Typ verwendet, der in der Vererbungskette niedriger ist.|
|`downto`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|In `for` einem Ausdruck, der beim Zählen in umgekehrter Reihenfolge verwendet wird.|
|`elif`|[Bedingte Ausdrücke:`if...then...else`](conditional-expressions-if-then-else.md)|Wird in bedingten Verzweigungen verwendet. Eine kurze `else if`Form von .|
|`else`|[Bedingte Ausdrücke:`if...then...else`](conditional-expressions-if-then-else.md)|Wird in bedingten Verzweigungen verwendet.|
|`end`|[Strukturen](structures.md)<br /><br />[Unterscheidungs-Unions](discriminated-unions.md)<br /><br />[Datensätze](records.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Gibt in Typdefinitionen und Typerweiterungen das Ende eines Abschnitts von Memberdefinitionen an.<br /><br />In ausführlicher Syntax wird verwendet, um das Ende eines `begin` Codeblocks anzugeben, der mit dem Schlüsselwort beginnt.|
|`exception`|[Ausnahmebehandlung](./exception-handling/index.md)<br /><br />[Ausnahmetypen](./exception-handling/exception-types.md)|Wird verwendet, um einen Ausnahmetyp zu deklarieren.|
|`extern`|[Externe Funktionen](./functions/external-functions.md)|Gibt an, dass ein deklariertes Programmelement in einer anderen Binärdatei oder Assembly definiert ist.|
|`false`|[Primitive Typen](basic-types.md)|Wird als boolesches Literal verwendet.|
|`finally`|[Ausnahmen: Der `try...finally`-Ausdruck](./exception-handling/the-try-finally-expression.md)|Wird zusammen `try` mit dem Einleiten eines Codeblocks verwendet, der unabhängig davon ausgeführt wird, ob eine Ausnahme auftritt.|
|`fixed`|[Korrigiert](fixed.md)|Wird verwendet, um einen Zeiger auf dem Stapel zu "fixieren", um zu verhindern, dass er garbage collected wird.|
|`for`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)<br /><br />[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)|Wird in Schleifenkonstrukten verwendet.|
|`fun`|[Lambda-Ausdrücke: Das `fun` Schlüsselwort](./functions/lambda-expressions-the-fun-keyword.md)|Wird in Lambdaausdrücken verwendet, die auch als anonyme Funktionen bezeichnet werden.|
|`function`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Lambda-Ausdrücke: Das lustige Keyword](./functions/lambda-expressions-the-fun-keyword.md)|Wird als kürzere `fun` Alternative zum `match` Schlüsselwort und als Ausdruck in einem Lambda-Ausdruck verwendet, der Musterübereinstimmungen für ein einzelnes Argument aufweist.|
|`global`|[Namespaces](namespaces.md)|Wird verwendet, um auf den .NET-Namespace der obersten Ebene zu verweisen.|
|`if`|[Bedingte Ausdrücke:`if...then...else`](conditional-expressions-if-then-else.md)|Wird in bedingten Verzweigungskonstrukten verwendet.|
|`in`|[Schleifen: for...in-Ausdruck](loops-for-in-expression.md)<br /><br />[Ausführliche Syntax](verbose-syntax.md)|Wird für Sequenzausdrücke und in ausführlicher Syntax verwendet, um Ausdrücke von Bindungen zu trennen.|
|`inherit`|[Vererbung](inheritance.md)|Wird verwendet, um eine Basisklasse oder Basisschnittstelle anzugeben.|
|`inline`|[Funktionen](./functions/index.md)<br /><br />[Inlinefunktionen](./functions/inline-functions.md)|Wird verwendet, um eine Funktion anzugeben, die direkt in den Code des Aufrufers integriert werden soll.|
|`interface`|[Schnittstellen](interfaces.md)|Wird zum Deklarieren und Implementieren von Schnittstellen verwendet.|
|`internal`|[Zugriffssteuerung](access-control.md)|Wird verwendet, um anzugeben, dass ein Element innerhalb einer Baugruppe sichtbar ist, aber nicht außerhalb.|
|`lazy`|[Nicht strikte Ausdrücke](lazy-expressions.md)|Wird verwendet, um einen Ausdruck anzugeben, der nur ausgeführt werden soll, wenn ein Ergebnis erforderlich ist.|
|`let`|[`let`Bindungen](./functions/let-bindings.md)|Wird verwendet, um einem Wert oder einer Funktion einen Namen zuzuordnen oder zu binden.|
|`let!`|[Asynchrone Workflows](asynchronous-workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Wird in asynchronen Workflows verwendet, um einen Namen an das Ergebnis einer asynchronen Berechnung zu binden, oder in anderen Berechnungsausdrücken, um einen Namen an ein Ergebnis zu binden, das vom Berechnungstyp ist.|
|`match`|[Vergleichsausdrücke](match-expressions.md)|Wird verwendet, um einen Wert mit einem Muster zu vergleichen.|
|`match!`|[Berechnungsausdrücke](computation-expressions.md#match)|Wird verwendet, um einen Aufruf eines Berechnungsausdrucks und eines Musters für das Ergebnis inlinezu.|
|`member`|[Member](./members/index.md)|Wird verwendet, um eine Eigenschaft oder Methode in einem Objekttyp zu deklarieren.|
|`module`|[Module](modules.md)|Wird verwendet, um einen Namen einer Gruppe verwandter Typen, Werte und Funktionen zuzuordnen, um ihn logisch von anderem Code zu trennen.|
|`mutable`|[let-Bindungen](./functions/let-bindings.md)|Wird verwendet, um eine Variable zu deklarieren, d. h. einen Wert, der geändert werden kann.|
|`namespace`|[Namespaces](namespaces.md)|Wird verwendet, um einen Namen einer Gruppe verwandter Typen und Module zuzuordnen, um ihn logisch von anderem Code zu trennen.|
|`new`|[Konstruktoren](./members/constructors.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Wird verwendet, um einen Konstruktor zu deklarieren, zu definieren oder aufzurufen, der ein Objekt erstellt oder erstellen kann.<br /><br />Wird auch in generischen Parametereinschränkungen verwendet, um anzugeben, dass ein Typ über einen bestimmten Konstruktor verfügen muss.|
|`not`|[Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Eigentlich kein Schlüsselwort. `not struct` In Kombination wird jedoch als generische Parametereinschränkung verwendet.|
|`null`|[NULL-Werte](./values/null-values.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Gibt das Fehlen eines Objekts an.<br /><br />Wird auch in generischen Parametereinschränkungen verwendet.|
|`of`|[Unterscheidungs-Unions](discriminated-unions.md)<br /><br />[Delegaten](delegates.md)<br /><br />[Ausnahmetypen](./exception-handling/exception-types.md)|Wird in diskriminierten Unions verwendet, um den Typ der Wertekategorien anzugeben, sowie in Delegat- und Ausnahmedeklarationen.|
|`open`|[Importdeklarationen: Das `open`-Schlüsselwort](import-declarations-the-open-keyword.md)|Wird verwendet, um den Inhalt eines Namespace oder Moduls ohne Qualifikation verfügbar zu machen.|
|`or`|[Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)<br /><br />[Einschränkungen](./generics/constraints.md)|Wird mit booleschen Bedingungen `or` als boolescher Operator verwendet. Entspricht `||`.<br /><br />Wird auch in Elementeinschränkungen verwendet.|
|`override`|[Member](./members/index.md)|Wird verwendet, um eine Version einer abstrakten oder virtuellen Methode zu implementieren, die sich von der Basisversion unterscheidet.|
|`private`|[Zugriffssteuerung](access-control.md)|Beschränkt den Zugriff auf einen Member auf Code in demselben Typ oder Modul.|
|`public`|[Zugriffssteuerung](access-control.md)|Ermöglicht den Zugriff auf ein Element von außerhalb des Typs.|
|`rec`|[Funktionen](./functions/index.md)|Wird verwendet, um anzugeben, dass eine Funktion rekursiv ist.|
|`return`|[Asynchrone Workflows](Asynchronous-Workflows.md)<br /><br />[Berechnungsausdrücke](computation-expressions.md)|Wird verwendet, um einen Wert anzugeben, der als Ergebnis eines Berechnungsausdrucks angegeben werden soll.|
|`return!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Wird verwendet, um einen Berechnungsausdruck anzugeben, der bei der Auswertung das Ergebnis des enthaltenden Berechnungsausdrucks liefert.|
|`select`|[Abfrageausdrücke](query-expressions.md)|Wird in Abfrageausdrücken verwendet, um anzugeben, welche Felder oder Spalten extrahiert werden sollen. Beachten Sie, dass dies ein kontextbezogenes Schlüsselwort ist, was bedeutet, dass es sich nicht um ein reserviertes Wort handelt und es nur wie ein Schlüsselwort in einem geeigneten Kontext wirkt.|
|`static`|[Member](./members/index.md)|Wird verwendet, um eine Methode oder Eigenschaft anzugeben, die ohne eine Instanz eines Typs oder ein Wertmember aufgerufen werden kann, das von allen Instanzen eines Typs gemeinsam genutzt wird.|
|`struct`|[Strukturen](structures.md)<br /><br /> [Tupel](tuples.md)<br/><br/>[Einschränkungen](./generics/constraints.md)|Wird verwendet, um einen Strukturtyp zu deklarieren.<br /><br/>Wird verwendet, um ein Struktur-Tupel anzugeben.<br/><br />Wird auch in generischen Parametereinschränkungen verwendet.<br /><br />Wird für die OCaml-Kompatibilität in Moduldefinitionen verwendet.|
|`then`|[Bedingte Ausdrücke:`if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[Konstruktoren](./members/constructors.md)|Wird in bedingten Ausdrücken verwendet.<br /><br />Wird auch verwendet, um Nebenwirkungen nach der Objektkonstruktion durchzuführen.|
|`to`|[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)|Wird `for` in Schleifen verwendet, um einen Bereich anzugeben.|
|`true`|[Primitive Typen](basic-types.md)|Wird als boolesches Literal verwendet.|
|`try`|[Ausnahmen: Der try...with-Ausdruck](./exception-handling/the-try-with-expression.md)<br /><br />[Ausnahmen: Der try...finally-Ausdruck](./exception-handling/the-try-finally-expression.md)|Wird verwendet, um einen Codeblock einzuführen, der eine Ausnahme generieren könnte. Wird zusammen `with` `finally`mit oder verwendet.|
|`type`|[F#-Typen](fsharp-types.md)<br /><br />[Klassen](classes.md)<br /><br />[Datensätze](records.md)<br /><br />[Strukturen](structures.md)<br /><br />[Enumerationen](enumerations.md)<br /><br />[Unterscheidungs-Unions](discriminated-unions.md)<br /><br />[Typabkürzungen](type-abbreviations.md)<br /><br />[Maßeinheiten](units-of-measure.md)|Wird verwendet, um eine Klasse, einen Datensatz, eine Struktur, eine diskriminierte Union, einen Enumerationstyp, eine Maßeinheit oder eine Typabkürzung zu deklarieren.|
|`upcast`|[Umwandlung und Konvertierungen](casting-and-conversions.md)|Wird verwendet, um in einen Typ zu konvertieren, der in der Vererbungskette höher ist.|
|`use`|[Ressourcenverwaltung: Das `use`-Schlüsselwort](resource-management-the-use-keyword.md)|Wird anstelle `let` von Werten `Dispose` verwendet, die aufgerufen werden müssen, um Ressourcen freizugeben.|
|`use!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Wird anstelle `let!` von asynchronen Workflows und anderen `Dispose` Berechnungsausdrücken für Werte verwendet, die aufgerufen werden müssen, um Ressourcen freizugeben.|
|`val`|[Explizite Felder: Das `val` Schlüsselwort](./members/explicit-fields-the-val-keyword.md)<br /><br />[Signaturen](signature-files.md)<br /><br />[Member](./members/index.md)|Wird in einer Signatur verwendet, um einen Wert anzugeben, oder in einem Typ, um einen Member in begrenzten Situationen zu deklarieren.|
|`void`|[Primitive Typen](basic-types.md)|Gibt den `void` .NET-Typ an. Wird bei der Zusammenarbeit mit anderen .NET-Sprachen verwendet.|
|`when`|[Einschränkungen](./generics/constraints.md)|Wird für boolesche Bedingungen *(wenn Wächter*) für Musterübereinstimmungen verwendet, und zum Einführen einer Einschränkungsklausel für einen generischen Typparameter.|
|`while`|[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)|Führt ein Schleifenkonstrukt ein.|
|`with`|[Vergleichsausdrücke](match-expressions.md)<br /><br />[Objektausdrücke](object-expressions.md)<br /><br />[Kopieren und Aktualisieren von Datensatzausdrücken](copy-and-update-record-expressions.md)<br /><br />[Typerweiterungen](type-extensions.md)<br /><br />[Ausnahmen: Der `try...with`-Ausdruck](./exception-handling/the-try-with-expression.md)|Wird zusammen `match` mit dem Schlüsselwort in Musterübereinstimmenden ausdrücken verwendet. Wird auch in Objektausdrücken, Datensatzkopierausdrücken und Typerweiterungen verwendet, um Elementdefinitionen einzuführen und Ausnahmehandler einzuführen.|
|`yield`|[Listen](lists.md), [Arrays](arrays.md), [Sequenzen](sequences.md)|Wird in einem Listen-, Array- oder Sequenzausdruck verwendet, um einen Wert für eine Sequenz zu erzeugen. In der Regel kann weggelassen werden, wie es in den meisten Situationen implizit ist.|
|`yield!`|[Berechnungsausdrücke](computation-expressions.md)<br /><br />[Asynchrone Workflows](asynchronous-workflows.md)|Wird in einem Berechnungsausdruck verwendet, um das Ergebnis eines bestimmten Berechnungsausdrucks an eine Sammlung von Ergebnissen für den enthaltenden Berechnungsausdruck anzuhängen.|

Die folgenden Token sind in F reserviert, da es sich um Schlüsselwörter in der OCaml-Sprache handelt:

- `asr`
- `land`
- `lor`
- `lsl`
- `lsr`
- `lxor`
- `mod`
- `sig`

Wenn Sie `--mlcompatibility` die Compileroption verwenden, stehen die oben genannten Schlüsselwörter für die Verwendung als Bezeichner zur Verfügung.

Die folgenden Token sind als Schlüsselwörter für die zukünftige Erweiterung der F-Sprache reserviert:

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

- [Sprachreferenz](index.md)
- [Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md)
- [Compileroptionen](compiler-options.md)
