---
title: Einführung in die funktionale Programmierung mit F#
description: Lernen Sie die Grundlagen der funktionalen F#Programmierung in kennen.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424709"
---
# <a name="introduction-to-functional-programming-in-f"></a>Einführung in die funktionale Programmierung in F\#

Die funktionale Programmierung ist ein Programmierstil, der die Verwendung von Funktionen und unveränderlichen Daten betont. Die typisierte funktionale Programmierung ist, wenn die funktionale Programmierung mit statischen Typen kombiniert wird F#, z. b. mit. Im Allgemeinen werden die folgenden Konzepte bei der funktionalen Programmierung hervorgehoben:

* Funktionen als primäre Konstrukte, die Sie verwenden
* Ausdrücke anstelle von Anweisungen
* Unveränderliche Werte für Variablen
* Deklarative Programmierung über imperative Programmierung

In dieser Reihe werden Konzepte und Muster der funktionalen Programmierung mithilfe F#von untersucht. Dabei lernen Sie auch etwas F# kennen.

## <a name="terminology"></a>Terminologie

Die funktionale Programmierung, wie andere Programmierparadigmen, enthält ein Vokabular, das Sie schließlich erlernen müssen. Im folgenden finden Sie einige gängige Begriffe, die Sie in der gesamten Zeit sehen werden:

* **Function** : eine Funktion ist ein Konstrukt, das eine Ausgabe erzeugt, wenn eine Eingabe angegeben wird. Formal wird ein Element aus einem _Satz einem anderen_ Satz zugeordnet. Diese Formalität wird in vielerlei Hinsicht auf den konkreten angehoben, insbesondere bei der Verwendung von Funktionen, die auf Daten Auflistungen angewendet werden. Es ist das grundlegendste (und wichtigste) Konzept bei der funktionalen Programmierung.
* **Ausdruck** : ein Ausdruck ist ein Konstrukt in Code, der einen Wert erzeugt. In F#muss dieser Wert gebunden oder explizit ignoriert werden. Ein Ausdruck kann trivial durch einen Funktions aufzurufen ersetzt werden.
* **Purity** -Purity ist eine Eigenschaft einer Funktion, sodass Ihr Rückgabewert für dieselben Argumente immer identisch ist und die Auswertung keine Nebeneffekte hat. Eine reine Funktion hängt vollständig von ihren Argumenten ab.
* **Referenzielle Transparenz** : referentielle Transparenz ist eine Eigenschaft von Ausdrücken, die Sie durch ihre Ausgabe ersetzen können, ohne das Verhalten eines Programms zu beeinträchtigen.
* **Unveränderlichkeit** : Unveränderlichkeit bedeutet, dass ein Wert nicht direkt geändert werden kann. Dies steht im Gegensatz zu Variablen, die sich direkt ändern können.

## <a name="examples"></a>Beispiele

Die folgenden Beispiele veranschaulichen diese grundlegenden Konzepte.

### <a name="functions"></a>Funktionen

Das gängigste und grundlegendste Konstrukt bei der funktionalen Programmierung ist die-Funktion. Im folgenden finden Sie eine einfache Funktion, die einer Ganzzahl 1 hinzufügt:

```fsharp
let addOne x = x + 1
```

Die Typsignatur lautet wie folgt:

```fsharp
val addOne: x:int -> int
```

Die Signatur kann mit dem Namen "`addOne` akzeptiert eine `int` mit dem Namen `x` und erzeugt eine `int`". Formal wird _`addOne` einen Wert_ aus dem Satz von ganzen Zahlen dem Satz von ganzen Zahlen zuordnet. Das `->` Token bezeichnet diese Zuordnung. In F#können Sie in der Regel die Funktions Signatur überprüfen, um einen Eindruck davon zu erhalten, was Sie tut.

Warum ist die Signatur also wichtig? Bei der typisierten funktionalen Programmierung ist die Implementierung einer Funktion oft weniger wichtig als die tatsächliche Typsignatur. Die Tatsache, dass `addOne` den Wert 1 zu einer Ganzzahl addiert, ist zur Laufzeit interessant, aber wenn Sie ein Programm erstellen, ist die Tatsache, dass es eine `int` akzeptiert und zurückgibt, so informiert, wie Sie diese Funktion tatsächlich verwenden werden. Wenn Sie diese Funktion außerdem ordnungsgemäß (in Bezug auf Ihre Typsignatur) verwenden, kann die Diagnose von Problemen nur innerhalb des Texts der `addOne` Funktion erfolgen. Dies ist der Impuls hinter der typisierten funktionalen Programmierung.

### <a name="expressions"></a>Ausdrücke

Ausdrücke sind Konstrukte, die zu einem Wert ausgewertet werden. Im Gegensatz zu-Anweisungen, die eine Aktion ausführen, können Ausdrücke eine Aktion durchführen, die einen Wert zurückgibt. Ausdrücke werden fast immer anstelle von-Anweisungen in der funktionalen Programmierung verwendet.

Sehen Sie sich die vorherige Funktion an, `addOne`. Der Text des `addOne` ist ein Ausdruck:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

Dies ist das Ergebnis dieses Ausdrucks, der den Ergebnistyp der `addOne` Funktion definiert. Beispielsweise könnte der Ausdruck, der diese Funktion bildet, in einen anderen Typ geändert werden, z. b. ein `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

Die Signatur der Funktion ist jetzt:

```fsharp
val addOne: x:'a -> string
```

Da für jeden Typ F# in `ToString()` aufgerufen werden kann, wurde der Typ des `x` generisch (sogenannte [Automatische Generalisierung](../language-reference/generics/automatic-generalization.md)), und der resultierende Typ ist eine `string`.

Ausdrücke sind nicht nur die Funktions Texte. Sie können Ausdrücke verwenden, die einen Wert verursachen, den Sie an anderer Stelle verwenden. Eine gängige `if`ist:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

Der `if` Ausdruck erzeugt einen Wert mit dem Namen `result`. Beachten Sie, dass Sie `result` vollständig weglassen können, indem Sie den `if` Ausdruck zum Text der `addOneIfOdd`-Funktion führen. Der wichtigste Punkt, den Sie sich an Ausdrücken merken müssen, ist, dass Sie einen Wert ergeben.

Es gibt einen besonderen Typ, `unit`, der verwendet wird, wenn nichts zurückgegeben werden muss. Sehen Sie sich beispielsweise diese einfache Funktion an:

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

Die Signatur sieht wie folgt aus:

```fsharp
val printString: str:string -> unit
```

Der `unit`-Typ gibt an, dass kein tatsächlicher Wert zurückgegeben wird. Dies ist nützlich, wenn Sie über eine Routine verfügen, die "arbeiten" muss, obwohl kein Wert vorhanden ist, der als Ergebnis der Arbeit zurückgegeben werden muss.

Dies ist ein starker Kontrast zur imperativen Programmierung, bei der das entsprechende `if` Konstrukt eine-Anweisung ist, und das Erstellen von Werten wird häufig mit veränderenden Variablen erreicht. In C#könnte der Code z. b. wie folgt geschrieben werden:

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

Beachten Sie, dass C# und andere Sprachen im C-Stil den [ternären Ausdruck](../../csharp/language-reference/operators/conditional-operator.md)unterstützen, der die Ausdrucks basierte bedingte Programmierung ermöglicht.

Bei der funktionalen Programmierung ist es selten, Werte mit-Anweisungen zu mutieren. Obwohl einige funktionale Sprachen Anweisungen und mutations unterstützen, ist es nicht üblich, diese Konzepte bei der funktionalen Programmierung zu verwenden.

### <a name="pure-functions"></a>Reine Funktionen

Wie bereits erwähnt, sind reine Funktionen Funktionen, die:

* Wertet immer denselben Wert für dieselbe Eingabe aus.
* Hat keine Nebenwirkungen.

Es ist hilfreich, mathematische Funktionen in diesem Kontext zu betrachten. In der Mathematik sind Funktionen nur von ihren Argumenten abhängig und haben keine Nebeneffekte. In der mathematischen Funktions `f(x) = x + 1`hängt der Wert von `f(x)` nur vom Wert von `x`ab. Reine Funktionen bei der funktionalen Programmierung sind auf dieselbe Weise.

Beim Schreiben einer reinen Funktion muss die Funktion nur von ihren Argumenten abhängen und keine Aktionen ausführen, die zu einem Nebeneffekt führen.

Im folgenden finden Sie ein Beispiel für eine nicht reine Funktion, da Sie vom globalen, veränderbaren Zustand abhängt:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

Die `addOneToValue` Funktion ist eindeutig, da `value` jederzeit geändert werden kann, um einen anderen Wert als 1 zu haben. Dieses Muster von, abhängig von einem globalen Wert, muss bei der funktionalen Programmierung vermieden werden.

Im folgenden finden Sie ein weiteres Beispiel für eine nicht reine Funktion, da Sie einen Nebeneffekt durchführt:

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

Obwohl diese Funktion nicht von einem globalen Wert abhängt, schreibt Sie den Wert `x` in die Ausgabe des Programms. Obwohl es in der Tat nichts falsches gibt, bedeutet dies, dass die Funktion nicht rein ist. Wenn ein anderer Teil des Programms von einem externen Programm, z. b. dem Ausgabepuffer, abhängt, kann sich das Aufrufen dieser Funktion auf diesen anderen Teil des Programms auswirken.

Wenn Sie die `printfn`-Anweisung entfernen, wird die-Funktion rein:

```fsharp
let addOneToValue x = x + 1
```

Obwohl diese Funktion nicht grundsätzlich _besser_ als die vorherige Version mit der `printfn`-Anweisung ist, gewährleistet Sie, dass all diese Funktion einen Wert zurückgibt. Wenn diese Funktion beliebig oft aufgerufen wird, wird das gleiche Ergebnis erzielt: Sie erzeugt lediglich einen Wert. Die von der Reinheit gegebene Vorhersagbarkeit ist etwas, das viele funktionale Programmierer anstreben.

### <a name="immutability"></a>Unveränderlichkeit

Und schließlich ist eines der grundlegendsten Konzepte der typisierten funktionalen Programmierung Unveränderlichkeit. In F#sind alle Werte standardmäßig unveränderlich. Dies bedeutet, dass Sie nicht direkt bearbeitet werden können, es sei denn, Sie markieren Sie explizit als änderbar.

In der Praxis bedeutet das Arbeiten mit unveränderlichen Werten, dass Sie Ihren Ansatz für die Programmierung von "Ich muss etwas ändern", in "Ich muss einen neuen Wert entwickeln" ändern.

Wenn Sie z. b. 1 zu einem Wert hinzufügen, wird ein neuer Wert erzeugt, der die vorhandene nicht muziiert:

```fsharp
let value = 1
let secondValue = value + 1
```

In F#mutiert der folgende Code die `value`-Funktion **nicht** . Stattdessen wird eine Gleichheits Überprüfung durchführt:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Einige funktionale Programmiersprachen unterstützen überhaupt keine Mutation. In F#wird es unterstützt, aber es ist nicht das Standardverhalten für-Werte.

Dieses Konzept erstreckt sich noch weiter auf Datenstrukturen. Bei der funktionalen Programmierung weisen unveränderliche Datenstrukturen, wie z. b. Mengen (und viele weitere), eine andere Implementierung auf als Sie anfänglich erwarten. Konzeptionell bedeutet das Hinzufügen eines Elements zu einem Satz nicht, dass der Satz geändert wird, sondern es wird eine _neue_ Menge mit dem hinzugefügten Wert erstellt. Im Unterschied wird dies häufig durch eine andere Datenstruktur erreicht, die eine effiziente Nachverfolgung eines Werts ermöglicht, damit die entsprechende Darstellung der Daten als Ergebnis angegeben werden kann.

Diese Art der Arbeit mit Werten und Datenstrukturen ist äußerst wichtig, da Sie zwingt, jeden Vorgang zu behandeln, der etwas so ändert, als ob eine neue Version der Aufgabe erstellt wird. Dies ermöglicht es, dass Dinge wie Gleichheit und Vergleichbarkeit in ihren Programmen einheitlich sind.

## <a name="next-steps"></a>Nächste Schritte

Im nächsten Abschnitt werden Funktionen ausführlich behandelt und verschiedene Möglichkeiten erläutert, wie Sie Sie bei der funktionalen Programmierung verwenden können.

[Erstklassige Funktionen](first-class-functions.md) untersucht Funktionen tief und zeigt, wie Sie Sie in verschiedenen Kontexten verwenden können.

## <a name="further-reading"></a>Weiterführende Themen

Die [denkende funktionale](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) Reihe ist eine weitere großartige Ressource, um mehr F#über die funktionale Programmierung mit zu erfahren. Sie behandelt die Grundlagen der funktionalen Programmierung auf eine pragmatische und leicht lesbare Weise, indem F# Sie Funktionen zum Veranschaulichen der Konzepte verwendet.
