---
title: Einführung in die funktionale Programmierung mit F#
description: Lernen Sie die Grundlagen der funktionalen Programmierung in F#.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724477"
---
# <a name="introduction-to-functional-programming-in-f"></a>Einführung in die funktionale Programmierung mit F# #

Funktionale Programmierung ist eine Art der Programmierung, die die Verwendung von Funktionen und Daten mit unveränderlicher betont. Typisierte funktionaler Programmierung ist funktionaler Programmierung mit statischen Typen, z. B. in Kombination mit ist F#. Die folgenden Begriffe werden in der Regel bei der funktionalen Programmierung hervorgehoben:

* Funktionen als die primären Konstrukte, die Sie verwenden
* Ausdrücke anstelle von Anweisungen
* Unveränderliche Werte Variablen
* Deklarative Programmierung häufiger über imperative Programmierung

In der gesamten Reihe, müssen Sie untersuchen, Konzepte und Muster in die funktionale Programmierung mit F#. Dabei erfahren Sie, einige F# zu.

## <a name="terminology"></a>Terminologie

Funktionale Programmierung, wie die anderen Paradigmen, enthält ein Vokabular, das Sie irgendwann einmal um zu erfahren. Hier sind einige allgemeine Begriffe, die Sie ständig sehen:

* **Funktion** -Funktion ist ein Konstrukt, das erzeugt eine Ausgabe, wenn eine Eingabe angegeben. Formeller gesehen, es _ordnet_ ein Element aus einem zu einer anderen Gruppe festgelegt. Diese formalismus ist in die konkreten in vielerlei Hinsicht transformiert, vor allem bei Verwendung von Funktionen, die ausgeführt werden Auflistungen von Daten. Es ist die grundlegende (und wichtige) Konzept bei der funktionalen Programmierung. 
* **Ausdruck** -ein Ausdruck ist ein Konstrukt in Code, der einen Wert erzeugt. In F#, muss dieser Wert gebunden oder explizit ignoriert werden. Ein Ausdruck kann einfach durch einen Funktionsaufruf ersetzt werden.
* **Reinheit** -Reinheit ist eine Eigenschaft einer Funktion, sodass der Rückgabewert immer für den gleichen Argumenten identisch ist und dass seine Bewertung keine Nebeneffekte hat. Eine reine Funktion hängt gänzlich von den Argumenten.
* **Referenzieller Transparenz** -referenzieller Transparenz ist eine Eigenschaft von Ausdrücken aus, sodass sie mit ihrer Ausgabe ersetzt werden können, ohne ein Programmverhalten.
* **Unveränderlichkeit** -Immutabilität bedeutet, dass ein Wert kann nicht direkt geändert. Dies ist im Gegensatz zu Variablen, die direktes ändern können.

## <a name="examples"></a>Beispiele

Die folgenden Beispiele veranschaulichen diese kernbegriffe.

### <a name="functions"></a>Funktionen

Die meisten allgemeinen und grundlegenden Konstrukt bei der funktionalen Programmierung ist die Funktion. Hier ist eine einfache Funktion, die eine ganze Zahl 1 hinzufügt:

```fsharp
let addOne x = x + 1
```

Die Typsignatur lautet wie folgt aus:

```fsharp
val addOne: x:int -> int
```

Die Signatur gelesen werden kann, wie "`addOne` akzeptiert eine `int` mit dem Namen `x` und erzeugt eine `int`". Formeller gesehen `addOne` ist _Zuordnung_ einen Wert aus dem Satz von ganzen Zahlen auf den Satz von ganzen Zahlen. Die `->` Token gibt an, diese Zuordnung. In F#, in der Regel sehen Sie sich die Signatur für die Sie bekommen eine Vorstellung für welche Aktion er ausführt.

Warum also ist die Signatur wichtig? In typisierte, funktionale Programmierung, die Implementierung einer Funktion wird häufig weniger wichtiger als die tatsächliche Typsignatur! Die Tatsache, `addOne` fügt der Wert 1 in eine ganze Zahl ist interessant, zur Laufzeit jedoch beim Konstruieren Sie ein Programm, die Tatsache, die akzeptiert und gibt eine `int` ist, was darüber informiert, wie Sie diese Funktion tatsächlich verwenden werden. Darüber hinaus sobald Sie diese Funktion ordnungsgemäß (in Bezug auf seine Typsignatur) verwenden, Diagnose von Problemen kann erfolgen nur innerhalb des Texts der `addOne` Funktion. Dies ist der Grund hinter typisierte funktionale Programmierung.

### <a name="expressions"></a>Ausdrücke

Ausdrücke sind Konstrukte, die zu einem Wert ausgewertet. Im Gegensatz zu Anweisungen, die eine Aktion ausführen zu können, können Ausdrücke betrachtet werden, der eine Aktion, die einen Wert zurück gibt. Ausdrücke werden fast immer zugunsten von Anweisungen, die bei der funktionalen Programmierung verwendet.

Betrachten Sie die vorherige Funktion `addOne`. Der Text der `addOne` ist ein Ausdruck:

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

Es ist das Ergebnis dieses Ausdrucks, das den Ergebnistyp des definiert die `addOne` Funktion. Beispielsweise konnte der Ausdruck, der diese Funktion bildet geändert werden, um einen anderen Typ, z. B. eine `string`:

```fsharp
let addOne x = x.ToString() + "1"
```

Die Signatur der Funktion lautet jetzt:

```fsharp
val addOne: x:'a -> string
```

Seit jeden Typ im F# können `ToString()` aufgerufen, der Typ des `x` wurde als generisches (namens [automatische Verallgemeinerung](../language-reference/generics/automatic-generalization.md)), und der resultierende Typ ist ein `string`.

Ausdrücke sind nicht nur die Texte der Funktionen. Sie können Ausdrücke verwenden, die einen Wert zu erzeugen, die, den Sie an anderer Stelle verwenden. Eine allgemeine er `if`:

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

Die `if` -Ausdruck liefert einen Wert mit dem `result`. Beachten Sie, die Sie auslassen `result` vollständig, wodurch die `if` Ausdruck den Text von der `addOneIfOdd` Funktion. Das wichtigste über Ausdrücke zu merken ist, dass sie einen Wert erzeugen.

Es ist ein spezieller Typ, `unit`, die verwendet wird, wenn nichts zurückgegeben. Betrachten Sie beispielsweise diese einfache Funktion:

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

Die Signatur sieht folgendermaßen aus:

```fsharp
val printString: str:string -> unit
```

Die `unit` Typ gibt an, dass keine tatsächlichen Wert zurückgegeben wird. Dies ist nützlich, wenn Sie eine Routine verfügen, die muss "funktionieren" auch wenn kein Wert als Ergebnis dieser Arbeit zurückgegeben.

Dies ist in den starken Kontrast zu imperativen Programmierung, in denen die entsprechende `if` Konstrukt ist eine Anweisung, und die Werte erzeugen erfolgt häufig mit veränderliche Variablen. Z. B. in C#, der Code wie folgt geschrieben werden kann:

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

Es ist erwähnenswert, die C# und anderen c-Sprachen unterstützen die [ternärer Ausdruck](../../csharp/language-reference/operators/conditional-operator.md), wodurch für die bedingte Programmierung auf Ausdrücken beruhende.

Bei der funktionalen Programmierung ist es nur selten, dass die Werte mit Anweisungen zu verändern. Obwohl einige funktionalen Sprachen Anweisungen und Mutation unterstützen, ist es nicht üblich, dass diese Konzepte bei der funktionalen Programmierung verwendet.

### <a name="pure-functions"></a>Reine Funktionen

Wie bereits erwähnte, reine Funktionen sind Funktionen, die:

* Überprüfen Sie immer auf den gleichen Wert für die gleiche Eingabe.
* Haben Sie keine nachteiligen Auswirkungen.

Es ist hilfreich, mathematische Funktionen, die in diesem Zusammenhang zu betrachten. In der Mathematik Funktionen nur abhängig von ihrer Argumente und müssen keine keine Nebeneffekte. In der mathematischen Funktion `f(x) = x + 1`, den Wert der `f(x)` hängt nur von den Wert der `x`. Reine Funktionen bei der funktionalen Programmierung sind die gleiche Weise.

Wenn Sie eine reine Funktion schreiben, muss die Funktion nur abhängig von den Argumenten und nicht ausgeführt werden alle Aktionen, die einen Nebeneffekt führt.

Hier ist ein Beispiel einer nicht reine Funktion auf, da sie global und änderbaren Zustand abhängt:

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

Die `addOneToValue` -Funktion ist deutlich unsauberen, da `value` kann jederzeit auf einen anderen Wert als 1 geändert werden. Dieses Muster der abhängig von einem globalen Wert ist, die bei der funktionalen Programmierung vermieden werden.

Hier ist ein weiteres Beispiel für eine nicht reine Funktion, da sie einen Nebeneffekt ausführt:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

Obwohl diese Funktion nicht von einem globalen Wert abhängig ist, schreibt er den Wert der `x` an die Ausgabe des Programms. Obwohl es nichts wirklich falsch ist, dabei, bedeutet dies, dass diese Funktion keine reine ist.

Entfernen der `printfn` Anweisung schließlich ist die Funktion rein:

```fsharp
let addOneToValue x = x + 1
```

Obwohl diese Funktion nicht grundsätzlich ist _besser_ als die vorherige Version mit der `printfn` -Anweisung, dies garantiert, dass alle mit dieser Funktion ist einen Wert zurückgeben. Aufrufen von dieser Funktion einmal oder 1 Milliarden Mal wird noch Ergebnis in das gleiche: nur einen Wert erzeugt. Diese Vorhersagbarkeit ist hilfreich bei der funktionalen Programmierung, da dies bedeutet, dass reiner Funktion Referenziell transparent ist.

### <a name="referential-transparency"></a>Referenzieller Transparenz

Referenzieller Transparenz ist eine Eigenschaft der Ausdrücke und Funktionen. Für einen Ausdruck Referenziell transparent sein müssen sie mit den sich ergebenden Wert ersetzt werden, ohne das Programm Verhalten zu ändern können. Alle reine Funktionen sind Referenziell transparent.

Wie bei reinen Funktionen kann es hilfreich, referenzieller Transparenz aus mathematischer Sicht vorstellen sein. In der mathematischen Ausdruck `y = f(x)`, `f(x)` kann durch das Ergebnis der Funktion ersetzt werden und sie werden gleich `y`. Dies gilt gleichermaßen für referenzieller Transparenz bei der funktionalen Programmierung.

Rufen Sie die zuvor definierte `addOneIfOdd` zweimal funktionieren:

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

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

Wir können alle Funktionsaufrufe durch Ersetzen der Hauptteil der Funktion, und Ersetzen Sie dabei das Argument `input` mit einzelnen Werten:

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

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

Beide `res1` und `res2` denselben Wert haben, als ob die Funktion aufgerufen wurde, gibt an, dass, `addOneIfOdd` Referenziell transparent ist.

Darüber hinaus muss eine Funktion keine reinen auch Referenziell transparent sein. Erwägen Sie eine vorherige Definition von `addOneTovalue`:

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

Jeder Aufruf dieser Funktion kann auch durch Text ersetzt werden, und die Punkte erfolgt jedes Mal:

* Der Wert, bevor Sie hinzugefügt wird, wird an die Ausgabe ausgegeben.
* Der Wert hinzugefügt wird "1" wurde "

Beim Programmieren in F#, es ist häufig referenzieller Transparenz, die das Ziel, anstatt Reinheit ist. Es ist jedoch weiterhin empfohlen, die reine Funktionen geschrieben werden, wenn möglich.

### <a name="immutability"></a>Unveränderlichkeit

Schließlich ist einer der wichtigsten Konzepte, typisierte, funktionale Programmierung Unveränderlichkeit. In F#, alle Werte sind standardmäßig nicht verändert werden. Das bedeutet, dass sie mutiert werden können, es sei denn, Sie explizit als änderbaren markieren.

In der Praxis bedeutet arbeiten mit unveränderlichen Werten an, dass Sie Ihren Ansatz mit der Programmierung von "muss ich etwas ändern" ändern, auf "Ich möchte einen neuen Wert zu erzeugen.".

Hinzufügen von 1 auf einen Wert bedeutet beispielsweise, erzeugen einen neuen Wert, der nicht mutierende der vorhandenen Dateigruppe:

```fsharp
let value = 1
let secondValue = value + 1
```

In F#, der folgende Code macht **nicht** geändert wird, die `value` funktionieren; stattdessen wird eine Überprüfung auf Gleichheit:

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

Einige funktionalen Programmiersprachen unterstützen überhaupt keine Veränderung. In F#, wird unterstützt, aber es ist nicht das Standardverhalten für Werte.

Dieses Konzept wird auch weiter auf Datenstrukturen erweitert. Bei der funktionalen Programmierung erwarten wie z. B. Sätze (und viele mehr) haben eine andere Implementierung als Anfangs vielleicht unveränderliche Datenstrukturen. Konzeptionell etwas Hinzufügen eines Elements zu einer Gruppe die Gruppe nicht geändert wird, erzeugt es ein _neue_ mit den hinzugefügten Wert festgelegt. Im Hintergrund wird dies häufig durch eine andere Datenstruktur erreicht, die ermöglicht, die zum Nachverfolgen von effizient eines Werts, damit die entsprechende Darstellung der Daten daher angegeben werden kann.

Diese Art der Arbeiten mit Werten und Datenstrukturen ist wichtig, wie sie erzwingt, einen Vorgang behandelt werden, der etwas ändert dass, als ob erstellt eine neue Version des ab. Dies ermöglicht z. B. auf Gleichheit und Vergleichbarkeit in Ihren Programmen konsistent sein.

## <a name="next-steps"></a>Nächste Schritte

Im nächste Abschnitt behandelt gründlich Funktionen, untersuchen verschiedene Möglichkeiten, die Sie sie bei der funktionalen Programmierung verwenden können.

[Funktionen](first-class-functions.md) tief, untersucht Funktionen zeigt, wie Sie diese in verschiedenen Kontexten verwenden können.

## <a name="further-reading"></a>Weiterführende Themen

Die [funktional denken](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) -Reihe ist eine weitere hervorragende Ressource funktionale Programmierung mit Informationen F#. Hierin sind die Grundlagen der funktionalen Programmierung pragmatischen und leicht lesbaren Weise mit F# Features zum Veranschaulichen der Konzepte.