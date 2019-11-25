---
title: Sequenzen
description: Erfahren Sie, wie F# Sie Sequenzen verwenden, wenn Sie über eine große, geordnete Sammlung von Daten verfügen, aber nicht unbedingt alle Elemente verwenden.
ms.date: 11/04/2019
ms.openlocfilehash: 34e03f1cead0a9f678f637afcb6c8397ef7572bc
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971448"
---
# <a name="sequences"></a>Sequenzen

> [!NOTE]
> Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Eine *Sequenz* ist eine logische Reihe von Elementen, die alle einen Typ haben. Sequenzen sind besonders nützlich, wenn Sie über eine große, geordnete Auflistung von Daten verfügen, aber nicht unbedingt alle Elemente erwarten. Einzelne Sequenz Elemente werden nur bei Bedarf berechnet, sodass eine Sequenz eine bessere Leistung als eine Liste bieten kann, wenn nicht alle Elemente verwendet werden. Sequenzen werden durch den `seq<'T>`-Typ dargestellt, bei dem es sich um einen Alias für <xref:System.Collections.Generic.IEnumerable%601>handelt. Daher kann jeder .NET-Typ, der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, als Sequenz verwendet werden. Das- [Modul "SQ](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) " bietet Unterstützung für Manipulationen bei Sequenzen.

## <a name="sequence-expressions"></a>Sequenz Ausdrücke

Ein *Sequenz Ausdruck* ist ein Ausdruck, der zu einer Sequenz ausgewertet wird. Sequenz Ausdrücke können eine Reihe von Formularen annehmen. In der einfachsten Form wird ein Bereich angegeben. Beispielsweise erstellt `seq { 1 .. 5 }` eine Sequenz, die fünf Elemente enthält, einschließlich der Endpunkte 1 und 5. Sie können auch ein Inkrement (oder Dekrement) zwischen zwei doppelten Perioden angeben. Der folgende Code erstellt z. b. die Sequenz von Vielfachen von 10.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Sequence-Ausdrücke bestehen aus einer F#-Ausdrücke, die Werte der Sequenz zu erzeugen. Sie können Werte auch Programm gesteuert generieren:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

Im vorherigen Beispiel wird der `->`-Operator verwendet, der es Ihnen ermöglicht, einen Ausdruck anzugeben, dessen Wert zu einem Teil der Sequenz wird. Sie können nur `->` verwenden, wenn jeder Teil des nachfolgenden Codes einen Wert zurückgibt.

Alternativ können Sie das `do`-Schlüsselwort mit einem optionalen `yield` angeben, das folgt:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Der folgende Code generiert eine Liste von Koordinatenpaaren sowie einen Index in einem Array, das das Raster darstellt. Beachten Sie, dass für den ersten `for` Ausdruck eine `do` angegeben werden muss.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Ein `if` Ausdruck, der in einer Sequenz verwendet wird, ist ein Filter. Wenn Sie z. b. eine Sequenz von nur Primzahlen generieren möchten, vorausgesetzt, dass Sie über eine Funktions `isprime` vom Typ `int -> bool`verfügen, erstellen Sie die Sequenz wie folgt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Wie bereits erwähnt, ist hier `do` erforderlich, da keine `else` Verzweigung vorhanden ist, die in die `if`übergeht. Wenn Sie versuchen, `->`zu verwenden, erhalten Sie eine Fehlermeldung, die besagt, dass nicht alle Verzweigungen einen Wert zurückgeben.

## <a name="the-yield-keyword"></a>Das `yield!`-Schlüsselwort

Manchmal möchten Sie möglicherweise eine Sequenz von Elementen in eine andere Sequenz einschließen. Wenn Sie eine Sequenz in eine andere Sequenz einschließen möchten, müssen Sie das `yield!`-Schlüsselwort verwenden:

```fsharp
// Repeats '1 2 3 4 5' ten times
seq {
    for _ in 1..10 do
        yield! seq { 1; 2; 3; 4; 5}
}
```

Eine andere Möglichkeit der Betrachtung von `yield!` ist, dass Sie eine innere Sequenz vereinfacht und diese dann in die enthaltende Sequenz einbezieht.

Wenn `yield!` in einem Ausdruck verwendet wird, müssen alle anderen einzelnen Werte das `yield`-Schlüsselwort verwenden:

```fsharp
// Combine repeated values with their values
seq {
    for x in 1..10 do
        yield x
        yield! seq { for i in 1..x -> i}
}
```

Wenn Sie nur `x` im vorherigen Beispiel angeben, führt dies dazu, dass die Sequenz keine Werte erzeugt.

## <a name="examples"></a>Beispiele

Im ersten Beispiel wird ein Sequenz Ausdruck verwendet, der eine Iterations-, Filter-und Yield-Sequenz enthält, um ein Array zu generieren. Mit diesem Code wird eine Sequenz von Primzahlen zwischen 1 und 100 in der Konsole ausgegeben.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Im folgenden Beispiel wird eine Multiplikationstabelle erstellt, die aus Tupeln mit drei Elementen besteht, die aus zwei Faktoren und dem Produkt bestehen:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

Das folgende Beispiel veranschaulicht die Verwendung von `yield!`, um einzelne Sequenzen in einer einzigen abschließenden Sequenz zu kombinieren. In diesem Fall werden die Sequenzen für jede Teilstruktur in einer binären Struktur in einer rekursiven Funktion verkettet, um die endgültige Sequenz zu erhalten.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Verwenden von Sequenzen

Sequenzen unterstützen viele der gleichen Funktionen wie [Listen](lists.md). Sequenzen unterstützen auch Vorgänge wie z. b. das Gruppieren und zählen mithilfe von Funktionen zum Erstellen von Schlüsseln. Sequenzen unterstützen außerdem vielfältigere Funktionen zum Extrahieren von unter Sequenzen.

Viele Datentypen, z. b. Listen, Arrays, Mengen und Zuordnungen, sind implizit Sequenzen, da es sich um Aufzähl Bare Auflistungen handelt. Eine Funktion, die eine Sequenz als Argument annimmt, funktioniert mit einem der Common F# Data Types, zusätzlich zu einem beliebigen .NET-Datentyp, der `System.Collections.Generic.IEnumerable<'T>`implementiert. Vergleichen Sie dies mit einer Funktion, die eine Liste als Argument annimmt, das nur Listen annehmen kann. Der Typ `seq<'T>` ist eine typabkürzung für `IEnumerable<'T>`. Dies bedeutet, dass jeder Typ, der die generische `System.Collections.Generic.IEnumerable<'T>`implementiert, einschließlich Arrays, Listen, Sätze und Zuordnungen F#in sowie der meisten .net-Auflistungs Typen, mit dem `seq`-Typ kompatibel ist und überall dort verwendet werden kann, wo eine Sequenz erwartet wird.

## <a name="module-functions"></a>Modulfunktionen

Das- [Modul "SQ](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) " im [Microsoft. FSharp. Collections-Namespace](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) enthält Funktionen zum Arbeiten mit Sequenzen. Diese Funktionen können auch mit Listen, Arrays, Zuordnungen und Sätzen verwendet werden, da alle diese Typen Enumerable sind und daher als Sequenzen behandelt werden können.

## <a name="creating-sequences"></a>Erstellen von Sequenzen

Sequenzen können mithilfe von Sequenz Ausdrücken erstellt werden, wie zuvor beschrieben, oder mithilfe bestimmter Funktionen.

Sie können eine leere Sequenz mithilfe von "* [. Empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59)" erstellen, oder Sie können mithilfe von "* [. Singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7)" eine Sequenz von nur einem angegebenen Element erstellen.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet9.fs)]

Mithilfe von " [sq. init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) " können Sie eine Sequenz erstellen, für die die Elemente mithilfe einer von Ihnen bereitgestellten Funktion erstellt werden. Außerdem geben Sie eine Größe für die Sequenz an. Diese Funktion ähnelt [List. init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), mit dem Unterschied, dass die Elemente erst erstellt werden, nachdem Sie die Sequenz durchlaufen haben. Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.init`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet10.fs)]

Ausgabe:

```console
0 10 20 30 40
```

Durch die Verwendung von "c [q. ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) " und " [setq. ofList&#60;'t&#62; Function](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d)" können Sie Sequenzen aus Arrays und Listen erstellen. Sie können jedoch auch Arrays und Listen in Sequenzen konvertieren, indem Sie einen Cast-Operator verwenden. Beide Verfahren werden im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet11.fs)]

Mithilfe von "* [. Cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334)" können Sie eine Sequenz aus einer schwach typisierten Auflistung erstellen, z. b. die in `System.Collections`definierten. Solch schwach typisierte Auflistungen haben den Elementtyp `System.Object` und werden mithilfe des nicht generischen `System.Collections.Generic.IEnumerable&#96;1` Typs aufgelistet. Der folgende Code veranschaulicht die Verwendung von `Seq.cast`, um eine `System.Collections.ArrayList` in eine Sequenz zu konvertieren.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet12.fs)]

Mithilfe der Funktion " [setq. initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) " können Sie unendliche Sequenzen definieren. Für eine solche Sequenz geben Sie eine Funktion an, die jedes Element aus dem Index des Elements generiert. Aufgrund der verzögerten Auswertung sind unendliche Sequenzen möglich. Elemente werden nach Bedarf erstellt, indem die von Ihnen angegebene Funktion aufgerufen wird. Im folgenden Codebeispiel wird eine unendliche Sequenz von Gleit Komma Zahlen erzeugt, in diesem Fall die abwechselnde Reihe von aufeinander folgenden Ganzzahlen.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet13.fs)]

Mit "" wird eine Sequenz aus einer Berechnungs [Funktion generiert,](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) die einen-Zustand annimmt und Sie transformiert, um jedes nachfolgende Element in der Sequenz zu erzeugen. Der Status ist nur ein Wert, der zum Berechnen der einzelnen Elemente verwendet wird, und kann sich ändern, wenn jedes Element berechnet wird. Das zweite Argument für `Seq.unfold` ist der Anfangswert, der verwendet wird, um die Sequenz zu starten. `Seq.unfold` verwendet einen Optionstyp für den-Zustand, mit dem Sie die Sequenz beenden können, indem Sie den `None`-Wert zurückgeben. Der folgende Code zeigt zwei Beispiele für Sequenzen, `seq1` und `fib`, die von einem `unfold` Vorgang generiert werden. Der erste, `seq1`, ist nur eine einfache Sequenz mit Zahlen von bis zu 20. Der zweite `fib`verwendet `unfold`, um die "fbonacci"-Sequenz zu berechnen. Da jedes Element in der "atbonacci"-Sequenz die Summe der vorherigen beiden "fbonacci"-Zahlen ist, ist der Zustandswert ein Tupel, das aus den vorherigen zwei Zahlen in der Sequenz besteht. Der Anfangswert ist `(1,1)`, die ersten beiden Zahlen in der Sequenz.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet14.fs)]

Die Ausgabe lautet wie folgt:

```console
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Der folgende Code ist ein Beispiel, das viele der hier beschriebenen Sequenz Modulfunktionen verwendet, um die Werte von unendlichen Sequenzen zu generieren und zu berechnen. Die Ausführung des Codes kann einige Minuten dauern.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>Suchen und suchen von Elementen

Funktionen zur Unterstützung von Sequenzen mit Listen: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq.exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47) und [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Die Versionen dieser Funktionen, die für Sequenzen verfügbar sind, Werten die Sequenz nur bis zu dem Element aus, nach dem gesucht wird. Beispiele finden Sie unter [Listen](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).

## <a name="obtaining-subsequences"></a>Abrufen von unter Sequenzen

" [Set](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) " und "Set" sind wie die entsprechenden Funktionen, die für Listen verfügbar sind, mit [dem Unterschied](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) , dass das Filtern und auswählen erst erfolgt, wenn die Sequenz Elemente ausgewertet werden.

Mit " [sq. TRUNCATE](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) " wird eine Sequenz aus einer anderen Sequenz erstellt, die Sequenz wird jedoch auf eine angegebene Anzahl von Elementen beschränkt. "* [. Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) " erstellt eine neue Sequenz, die nur eine angegebene Anzahl von Elementen ab dem Anfang einer Sequenz enthält. Wenn in der Sequenz weniger Elemente vorhanden sind, als Sie angeben, wird von `Seq.take` eine `System.InvalidOperationException`ausgelöst. Der Unterschied zwischen `Seq.take` und `Seq.truncate` besteht darin, dass `Seq.truncate` keinen Fehler erzeugt, wenn die Anzahl der Elemente kleiner ist als die Anzahl, die Sie angeben.

Der folgende Code zeigt das Verhalten und Unterschiede zwischen `Seq.truncate` und `Seq.take`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet16.fs)]

Die Ausgabe vor dem Auftreten des Fehlers lautet wie folgt.

```console
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
1 4 9 16 25
1 4 9 16 25 36 49 64 81 100
```

Mithilfe von "* [. TakeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92)" können Sie eine Prädikat Funktion angeben (eine boolesche Funktion) und eine Sequenz aus einer anderen Sequenz erstellen, die aus den Elementen der ursprünglichen Sequenz besteht, für die das Prädikat `true`ist, aber vor dem ersten Element für die, die das Prädikat `false`zurückgibt. " [Sq. Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) " gibt eine Sequenz zurück, die eine angegebene Anzahl von ersten Elementen einer anderen Sequenz überspringt und die restlichen Elemente zurückgibt. "* [. SkipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) " gibt eine Sequenz zurück, die die ersten Elemente einer anderen Sequenz überspringt, solange das Prädikat `true`zurückgibt, und dann die restlichen Elemente zurückgibt, beginnend mit dem ersten Element, für das das Prädikat `false`zurückgibt.

Das folgende Codebeispiel veranschaulicht das Verhalten von und unterschieden zwischen `Seq.takeWhile`, `Seq.skip`und `Seq.skipWhile`.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet17.fs)]

Die Ausgabe lautet wie folgt.

```console
1 4 9
36 49 64 81 100
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Transformieren von Sequenzen

[Seq. paarweise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) erstellt eine neue Sequenz, in der aufeinander folgende Elemente der Eingabe Sequenz in Tupel gruppiert werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet18.fs)]

" [Seq. Windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) " ist wie `Seq.pairwise`, mit der Ausnahme, dass anstelle einer Sequenz von Tupeln eine Sequenz von Arrays erzeugt wird, die Kopien von angrenzenden Elementen (ein *Fenster*) aus der Sequenz enthalten. Sie geben die Anzahl der angrenzenden Elemente in jedem Array an.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.windowed`. In diesem Fall ist die Anzahl der Elemente im Fenster 3. Im Beispiel wird `printSeq`verwendet, das im vorherigen Codebeispiel definiert wurde.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet180.fs)]

Die Ausgabe lautet wie folgt.

Anfangssequenz:

```console
1.0 1.5 2.0 1.5 1.0 1.5

Windows of length 3:
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|]

Moving average:
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Vorgänge mit mehreren Sequenzen

[Seq. zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) und [Seq. zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) nehmen zwei oder drei Sequenzen an und erstellen eine Sequenz von Tupeln. Diese Funktionen sind wie die entsprechenden Funktionen, die für [Listen](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d)verfügbar sind. Es gibt keine entsprechende Funktionalität zum Trennen einer Sequenz in zwei oder mehr Sequenzen. Wenn Sie diese Funktionalität für eine Sequenz benötigen, konvertieren Sie die Sequenz in eine Liste, und verwenden Sie [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).

## <a name="sorting-comparing-and-grouping"></a>Sortieren, vergleichen und gruppieren

Die Sortierfunktionen, die für Listen unterstützt werden, funktionieren auch mit Sequenzen. Dies schließt "* [. Sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) " und "*. [SortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f)" ein. Diese Funktionen durchlaufen die gesamte Sequenz.

Sie vergleichen zwei Sequenzen [mithilfe der Funktion](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) "" von "". Die-Funktion vergleicht aufeinander folgende Elemente und beendet, wenn Sie auf das erste ungleiche paar trifft. Alle zusätzlichen Elemente tragen nicht zum Vergleich bei.

Im folgenden Code wird die Verwendung von `Seq.compareWith` veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet19.fs)]

Im vorherigen Code wird nur das erste Element berechnet und überprüft, und das Ergebnis ist-1.

"" Ist eine Funktion, die für jedes Element einen Wert [mit](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) dem Namen " *Key* " generiert. Ein Schlüssel wird für jedes Element generiert, indem diese Funktion für jedes Element aufgerufen wird. `Seq.countBy` gibt dann eine Sequenz zurück, die die Schlüsselwerte und die Anzahl der Elemente enthält, die jeden Wert des Schlüssels generiert haben.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet201.fs)]

Die Ausgabe lautet wie folgt.

```console
(1, 34) (2, 33) (0, 33)
```

Die vorherige Ausgabe zeigt, dass 34 Elemente der ursprünglichen Sequenz vorhanden waren, die den Schlüssel 1, 33-Werte, die den Schlüssel 2 erstellt haben, und 33-Werte, die den Schlüssel 0 erzeugt haben, erstellt haben.

Sie können Elemente einer Sequenz gruppieren, indem Sie "* [. GroupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd)" aufrufen. `Seq.groupBy` nimmt eine Sequenz und eine Funktion an, die einen Schlüssel aus einem-Element generiert. Die-Funktion wird für jedes Element der Sequenz ausgeführt. `Seq.groupBy` gibt eine Sequenz von Tupeln zurück, wobei das erste Element jedes Tupels der Schlüssel und das zweite eine Sequenz von Elementen ist, die diesen Schlüssel erzeugt.

Im folgenden Codebeispiel wird die Verwendung von `Seq.groupBy` zum Partitionieren der Sequenz von Zahlen von 1 bis 100 in drei Gruppen mit den eindeutigen Schlüsselwerten 0, 1 und 2 veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet202.fs)]

Die Ausgabe lautet wie folgt.

```console
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Sie können eine Sequenz erstellen, die doppelte Elemente durch Aufrufen von "* [. verschieden](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401)" entfernt. Oder Sie können " [sq. distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75)" verwenden, das eine Schlüssel generierende Funktion verwendet, die für jedes Element aufgerufen wird. Die resultierende Sequenz enthält Elemente der ursprünglichen Sequenz mit eindeutigen Schlüsseln. spätere Elemente, die einen doppelten Schlüssel zu einem früheren Element liefern, werden verworfen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.distinct`. `Seq.distinct` wird veranschaulicht, indem Sequenzen erzeugt werden, die binäre Zahlen darstellen, und dann zeigt, dass die einzigen unterschiedlichen Elemente 0 und 1 sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet22.fs)]

Der folgende Code veranschaulicht die `Seq.distinctBy`, indem mit einer Sequenz begonnen wird, die negative und positive Zahlen enthält und die absolute value-Funktion als Schlüssel generierende Funktion verwendet. In der resultierenden Sequenz fehlen alle positiven Zahlen, die den negativen Zahlen in der Sequenz entsprechen, da die negativen Zahlen an früherer Stelle in der Sequenz angezeigt werden und daher anstelle der positiven Zahlen mit dem gleichen absoluten Wert ausgewählt werden. -Wert oder-Schlüssel.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Schreibgeschützte und zwischengespeicherte Sequenzen

Mit "*" wird eine schreibgeschützte Kopie einer [Sequenz erstellt.](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) `Seq.readonly` ist nützlich, wenn Sie über eine Auflistung mit Lese-/Schreibzugriff verfügen, z. b. ein Array, und Sie die ursprüngliche Auflistung nicht ändern möchten. Diese Funktion kann verwendet werden, um die Daten Kapselung beizubehalten. Im folgenden Codebeispiel wird ein Typ erstellt, der ein Array enthält. Eine Eigenschaft macht das Array verfügbar, aber anstelle eines Arrays gibt es eine Sequenz zurück, die aus dem Array mithilfe von `Seq.readonly`erstellt wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssequences/snippet24.fs)]

" [Sq. Cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) " erstellt eine gespeicherte Version einer Sequenz. Verwenden Sie `Seq.cache`, um eine erneute Auswertung einer Sequenz zu vermeiden, oder wenn Sie über mehrere Threads verfügen, die eine Sequenz verwenden, aber Sie müssen sicherstellen, dass jedes Element nur einmal bearbeitet wird. Wenn Sie eine Sequenz haben, die von mehreren Threads verwendet wird, können Sie einen Thread verwenden, der die Werte für die ursprüngliche Sequenz auflistet und berechnet, und die verbleibenden Threads können die zwischengespeicherte Sequenz verwenden.

## <a name="performing-computations-on-sequences"></a>Ausführen von Berechnungen für Sequenzen

Einfache arithmetische Operationen ähneln denen von Listen, wie z [. b. "*. Average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8)", "* [. Sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a)", "* [. averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8)", " [sq. sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)" usw.

" [Setq. Fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3)", " [setq. Reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9)" und " [setq. Scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) " ähneln den entsprechenden Funktionen, die für Listen verfügbar sind. Sequenzen unterstützen eine Teilmenge der vollständigen Variationen dieser Funktionen, die die-Unterstützung auflisten. Weitere Informationen und Beispiele finden Sie unter [Listen](lists.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
