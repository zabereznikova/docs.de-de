---
title: Einführung in die funktionale Programmierung mit F#
description: Lernen Sie die Grundlagen der funktionalen Programmierung mit F# kennen.
ms.date: 10/29/2018
ms.openlocfilehash: fc2aebe80de16b92942c3557c0e03c198883dde1
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740327"
---
# <a name="introduction-to-functional-programming-in-f"></a>Einführung in die funktionale Programmierung mit F\#

Die funktionale Programmierung ist ein Programmierstil, der die Verwendung von Funktionen und unveränderlichen Daten betont. Das Merkmal typisierter funktionaler Programmierung ist, dass die funktionale Programmierung mit statischen Typen kombiniert wird, z. B. F#. Im Allgemeinen werden die folgenden Konzepte bei der funktionalen Programmierung betont:

* Funktionen als primäre Konstrukte, die Sie verwenden
* Ausdrücke anstelle von Anweisungen
* Unveränderliche Werte vor Variablen
* Deklarative Programmierung vor imperativer Programmierung

In dieser Reihe lernen Sie Konzepte und Muster der funktionalen Programmierung mit F# kennen. Dabei erfahren Sie auch Einiges über F#.

## <a name="terminology"></a>Begriff

Wie andere Programmierparadigmen hat die funktionale Programmierung ein Vokabular, das Sie lernen müssen. Im Folgenden finden Sie einige gängige Begriffe, die Ihnen ständig begegnen werden:

* **Funktion**: Eine Funktion ist ein Konstrukt, das eine Ausgabe erzeugt, wenn es eine Eingabe erhält. Formeller gesagt, _weist_ sie ein Element aus einem Satz einem anderen Satz zu. Dieser Formalismus wird in vielerlei Hinsicht konkret, insbesondere bei der Verwendung von Funktionen, die Datensammlungen verarbeiten. Dies ist das grundlegendste (und wichtigste) Konzept der funktionalen Programmierung.
* **Ausdruck**: Ein Ausdruck ist ein Konstrukt im Code, das einen Wert erzeugt. In F# muss dieser Wert gebunden oder explizit ignoriert werden. Ein Ausdruck kann einfach durch einen Funktionsaufruf ersetzt werden.
* **Reinheit**: Reinheit als Eigenschaft einer Funktion bedeutet, dass ihr Rückgabewert für dieselben Argumente immer identisch ist und seine Auswertung keine Nebeneffekte hat. Eine reine Funktion hängt vollständig von ihren Argumenten ab.
* **Referenzielle Transparenz**: Referenzielle Transparenz als Eigenschaft einer Funktion bedeutet, dass sie durch ihre Ausgabe ersetzt werden kann, ohne dass das Verhalten eines Programms beeinträchtigt wird.
* **Unveränderlichkeit**: Unveränderlichkeit bedeutet, dass ein Wert nicht direkt geändert werden kann. Dies steht im Gegensatz zu Variablen, die sich direkt ändern können.

## <a name="examples"></a>Beispiele

In den folgenden Beispielen werden diese Kernkonzepte veranschaulicht.

### <a name="functions"></a>Functions

Das gängigste und grundlegendste Konstrukt der funktionalen Programmierung ist die Funktion. Im Folgenden finden Sie eine einfache Funktion, die einer Ganzzahl den Wert 1 hinzufügt:

```fsharp
let addOne x = x + 1
```

Ihre Typsignatur lautet wie folgt:

```fsharp
val addOne: x:int -> int
```

Die Signatur kann als „`addOne` nimmt einen `int`-Wert mit dem Namen `x` entgegen und erzeugt einen `int`-Wert“ gelesen werden. Formeller betrachtet, ist `addOne` die _Zuordnung_ eines Wert aus dem Satz ganzer Zahlen zum Satz ganzer Zahlen. Das `->`-Token bezeichnet diese Zuordnung. In F# können Sie in der Regel anhand der Funktionssignatur erkennen, was sie tut.

Warum ist die Signatur denn so wichtig? In der typisierten funktionalen Programmierung ist die Implementierung einer Funktion oft weniger wichtig als die eigentliche Typsignatur! Die Tatsache, dass `addOne` den Wert 1 zu einer Ganzzahl addiert, ist zur Laufzeit interessant, aber wenn Sie ein Programm erstellen, informiert Sie die Tatsache, dass es einen `int`-Wert annimmt und zurückgibt, darüber, wie Sie diese Funktion tatsächlich verwenden werden. Wenn Sie diese Funktion außerdem ordnungsgemäß (in Bezug auf ihre Typsignatur) verwenden, kann die Diagnose von Problemen nur innerhalb des Texts der `addOne`-Funktion erfolgen. Dies ist der Impuls hinter der typisierten funktionalen Programmierung.

### <a name="expressions"></a>Ausdrücke

Ausdrücke sind Konstrukte, die zu einem Wert ausgewertet werden. Im Gegensatz zu Anweisungen, die einfach eine Aktion ausführen, führen Ausdrücke eine Aktion aus, die einen Wert zurückgibt. Ausdrücke werden in der funktionalen Programmierung fast immer Anweisungen vorgezogen.

Betrachten Sie die obige Funktion `addOne`. Der Text von `addOne` ist ein Ausdruck:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

Das Ergebnis dieses Ausdrucks definiert den Ergebnistyp der `addOne`-Funktion. Beispielsweise könnte der Ausdruck, der diese Funktion bildet, in einen anderen Typ geändert werden, z. B. einen `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

Die Signatur der Funktion lautet nun:

```fsharp
val addOne: x:'a -> string
```

Da für jeden Typ in F# `ToString()` aufgerufen werden kann, wurde der Typ von `x` verallgemeinert ([automatische Verallgemeinerung](../language-reference/generics/automatic-generalization.md) genannt), und der resultierende Typ ist ein `string`.

Ausdrücke sind nicht nur die Texte von Funktionen. Sie können Ausdrücke verwenden, die einen Wert produzieren, den Sie an anderer Stelle verwenden. `if` ist gängig:

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

Der `if`-Ausdruck erzeugt einen Wert namens `result`. Beachten Sie, dass Sie `result` vollständig weglassen könnten, indem Sie den `if`-Ausdruck zum Text der `addOneIfOdd`-Funktion machen. Das Wichtigste, was Sie sich über Ausdrücke merken sollten, ist, dass sie einen Wert produzieren.

Ein besonderer Typ, `unit`, wird verwendet, wenn nichts zurückgegeben werden muss. Betrachten Sie als Beispiel diese einfache Funktion:

```fsharp
let printString (str: string) =
    printfn $"String is: {str}"
```

Die Signatur sieht wie folgt aus:

```fsharp
val printString: str:string -> unit
```

Der `unit`-Typ gibt an, dass kein tatsächlicher Wert zurückgegeben wird. Dies ist nützlich, wenn Sie über eine Routine verfügen, die „arbeiten“ muss, obwohl kein Wert vorhanden ist, der als Ergebnis der Arbeit zurückgegeben werden könnte.

Dies ist ein scharfer Kontrast zur imperativen Programmierung, bei der das entsprechende `if`-Konstrukt eine-Anweisung ist und das Erstellen von Werten häufig mit der Veränderung von Variablen erfolgt. In C# könnte der Code z. B. wie folgt geschrieben werden:

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

Beachten Sie, dass C# und andere Sprachen im C-Stil den [ternären Ausdruck](../../csharp/language-reference/operators/conditional-operator.md) unterstützen, der die ausdrucksbasierte bedingte Programmierung ermöglicht.

In der funktionalen Programmierung werden Werte selten mit Anweisungen verändert. Einige funktionale Sprachen unterstützen Anweisungen und Veränderungen, aber es ist nicht üblich, diese Konzepte in der funktionalen Programmierung zu verwenden.

### <a name="pure-functions"></a>Reine Funktionen

Wie bereits erwähnt, weisen reine Funktionen folgende Merkmale auf:

* Für dieselbe Eingabe wird immer derselbe Wert ausgewertet.
* Sie haben keine Nebeneffekte.

Es ist hilfreich, in diesem Kontext mathematische Funktionen zu betrachten. In der Mathematik sind Funktionen nur von ihren Argumenten abhängig und haben keine Nebeneffekte. In der mathematischen Funktion `f(x) = x + 1` hängt der Wert von `f(x)` nur vom Wert von `x` ab. Bei reinen Funktionen in der funktionalen Programmierung verhält es sich genauso.

Beachten Sie beim Schreiben einer reinen Funktion, dass die Funktion nur von ihren Argumenten abhängig sein und keine Aktionen ausführen darf, die zu einem Nebeneffekt führen.

Im Folgenden finden Sie ein Beispiel für eine Funktion, die nicht rein ist, da sie vom globalen, veränderbaren Zustand abhängt:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

Die `addOneToValue`-Funktion ist eindeutig nicht rein, da `value` jederzeit in einen anderen Wert als 1 geändert werden könnte. Dieses Muster der Abhängigkeit von einem globalen Wert muss in der funktionalen Programmierung vermieden werden.

Hier sehen Sie ein weiteres Beispiel für eine Funktion, die nicht rein ist, da sie einen Nebeneffekt hat:

```fsharp
let addOneToValue x =
    printfn $"x is %d{x}"
    x + 1
```

Obwohl diese Funktion nicht von einem globalen Wert abhängt, schreibt sie den Wert `x` in die Ausgabe des Programms. Dies ist zwar grundsätzlich nicht falsch, bedeutet aber, dass die Funktion nicht rein ist. Wenn ein anderer Teil des Programms von programmexternen Elementen wie z. B. dem Ausgabepuffer abhängt, kann der Aufruf dieser Funktion sich auf diesen anderen Teil des Programms auswirken.

Durch Entfernen der `printfn`-Anweisung wird die Funktion rein:

```fsharp
let addOneToValue x = x + 1
```

Diese Funktion ist zwar nicht grundsätzlich _besser_ als die vorherige Version mit der `printfn`-Anweisung, aber es ist gewährleistet, dass sie nichts anderes tut als einen Wert zurückzugeben. Wenn diese Funktion beliebig oft aufgerufen wird, wird immer das gleiche Ergebnis erzielt: Sie erzeugt lediglich einen Wert. Die durch Reinheit garantierte Vorhersagbarkeit ist etwas, das viele funktionale Programmierer anstreben.

### <a name="immutability"></a>Unveränderlichkeit.

Schließlich ist Unveränderlichkeit eines der grundlegendsten Konzepte der typisierten funktionalen Programmierung. In F# sind alle Werte standardmäßig unveränderbar. Dies bedeutet, dass sie nicht direkt bearbeitet werden können, sofern Sie sie nicht explizit als veränderbar markieren.

In der Praxis bedeutet das Arbeiten mit unveränderlichen Werten, dass Sie Ihren Programmierungsansatz von „Ich muss etwas ändern“ in „Ich muss einen neuen Wert erzeugen“ ändern.

Wenn Sie z. B. 1 einem Wert hinzufügen, wird ein neuer Wert erzeugt, nicht der vorhandene Wert geändert:

```fsharp
let value = 1
let secondValue = value + 1
```

In F# ändert der folgende Code **nicht** die `value`-Funktion; stattdessen wird eine Gleichheitsüberprüfung durchgeführt:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Einige funktionale Programmiersprachen unterstützen die Änderung überhaupt nicht. In F# wird sie unterstützt, ist aber nicht das Standardverhalten für Werte.

Dieses Konzept erstreckt sich sogar noch weiter auf Datenstrukturen. In der funktionalen Programmierung weisen unveränderliche Datenstrukturen wie z. B. Sätze (und viele weitere) eine andere Implementierung auf, als Sie vielleicht anfänglich erwarten. Konzeptionell ändert etwas wie das Hinzufügen eines Elements zu einem Satz den Satz nicht, sondern produziert einen _neuen_ Satz mit dem hinzugefügten Wert. Im Hintergrund wird dies häufig durch eine andere Datenstruktur erreicht, die eine effiziente Nachverfolgung eines Werts ermöglicht, damit die entsprechende Darstellung der Daten als Ergebnis angegeben werden kann.

Dieser Stil des Arbeitens mit Werten und Datenstrukturen ist äußerst wichtig, da er Sie zwingt, jeden Vorgang, der etwas ändert, so zu behandeln, als schaffe er eine neue Version dieses Elements. Dies ermöglicht die Konsistenz von Aspekten wie Gleichheit und Vergleichbarkeit in Ihren Programmen.

## <a name="next-steps"></a>Nächste Schritte

Im nächsten Abschnitt werden Funktionen ausführlich behandelt und verschiedene Möglichkeiten untersucht, wie Sie sie in der funktionalen Programmierung verwenden können.

[Funktionen erster Klasse](first-class-functions.md) untersucht Funktionen gründlich und zeigt Ihnen, wie Sie sie in verschiedenen Kontexten verwenden können.

## <a name="further-reading"></a>Weitere nützliche Informationen

Die Reihe [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) (Funktional denken) ist eine weitere großartige Ressource, um mehr über die funktionale Programmierung mit F# zu erfahren. Sie behandelt die Grundlagen der funktionalen Programmierung auf pragmatische und leicht lesbare Weise, wobei die Konzepte mit F#-Funktionen veranschaulicht verwendet.
