---
title: Sequenzen (F#)
description: Erfahren Sie, wie Sie F#-Sequenzen zu verwenden, wenn Sie eine große Sammlung von Daten sortiert haben, aber nicht unbedingt erwartet, dass alle Elemente zu verwenden.
ms.date: 05/16/2016
ms.openlocfilehash: cfe8d1e350a8ac46b7700c12aa84d250f8b35855
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45527641"
---
# <a name="sequences"></a>Sequenzen

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Ein *Sequenz* ist eine logische Reihe von Elementen eines einzigen Typs. Sequenzen sind besonders nützlich, wenn Sie über eine große geordnete Auflistung von Daten, aber unbedingt erwarten nicht alle Elemente zu verwenden. Einzelne Sequenzelemente werden nur als Elemente berechnet werden erforderlich, damit eine bessere Leistung als eine Liste in Situationen eine Sequenz bereitstellen kann, wenn in dem möglicherweise nicht alle Elemente verwendet werden. Sequenzen werden dargestellt, durch die `seq<'T>` Typ, der einen Alias für `System.Collections.Generic.IEnumerable`. Aus diesem Grund alle .NET Framework-Typ, der implementiert `System.IEnumerable` kann als Sequenz verwendet werden. Die [Seq-Modul](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) bietet Unterstützung für Manipulationen mit Sequenzen.

## <a name="sequence-expressions"></a>Sequence-Ausdrücke

Ein *sequenzieren Ausdruck* ist ein Ausdruck, der eine Sequenz ergibt. Sequence-Ausdrücke können verschiedene Formen aufweisen. Die einfachste Form gibt einen Bereich an. Z. B. `seq { 1 .. 5 }` erstellt eine Sequenz, die fünf Elemente, einschließlich der Endpunkte, 1 und 5 enthält. Sie können auch ein Inkrement angeben (oder verringert) zwischen zwei doppelten Punkte. Der folgende Code erstellt z. B. die Abfolge der ein Vielfaches von 10.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Sequence-Ausdrücke bestehen aus einer f#-Ausdrücke, die Werte der Sequenz zu erzeugen. Sie können die `yield` Schlüsselwort, um die Werte erzeugen, werden Teil der Sequenz.

Es folgt ein Beispiel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

Können Sie die `->` Operator anstelle des `yield`, in diesem Fall können Sie weglassen der `do` -Schlüsselwort, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Der folgende Code generiert eine Liste der Koordinatenpaare zusammen mit einem Index in ein Array, das Raster darstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Ein `if` verwendete Ausdruck in einer Sequenz ist ein Filter. Beispielsweise, um eine Sequenz von nur Primzahlen, vorausgesetzt, Sie verfügen über eine Funktion generieren `isprime` des Typs `int -> bool`, erstellen Sie wie folgt die Sequenz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Bei Verwendung von `yield` oder `->` jeder Iteration muss in einer Iteration, um ein einzelnes Element der Sequenz zu generieren. Wenn jede Iteration eine Sequenz von Elementen erzeugt, verwenden Sie `yield!`. In diesem Fall werden die Elemente, die für jede Iteration generiert verkettet, um die endgültige Sequenz zu erzeugen.

Sie können mehrere Ausdrücke in einem Sequenzausdruck kombinieren. Die von jeder Ausdruck generierten Elemente werden miteinander verkettet. Ein Beispiel finden Sie im Abschnitt "Beispiele" in diesem Thema.

## <a name="examples"></a>Beispiele

Im ersten Beispiel wird einen Sequenzausdruck mit einer Iteration, einem Filter und eine "yield", um ein Array zu generieren. Dieser Code gibt eine Sequenz von Primzahlen zwischen 1 und 100 an die Konsole.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Der folgende code verwendet `yield` zum Erstellen einer Multiplikation-Tabelle, die aus Tupeln von drei Elementen, jede bestehend aus zwei Faktoren und das Produkt besteht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

Das folgende Beispiel zeigt die Verwendung von `yield!` einzelne Sequenzen zu einer einzigen endgültigen Sequenz zusammengefasst. In diesem Fall werden die Sequenzen für jede Teilstruktur in einer binären Struktur in eine rekursive Funktion zum Erzeugen der letzten Sequenz verkettet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]

## <a name="using-sequences"></a>Verwendung von Sequenzen

Sequenzen unterstützen viele derselben Funktionen wie [listet](lists.md). Sequenzen unterstützen auch Vorgänge wie das Gruppieren und mit der Generierung von Funktionen zählen. Sequenzen unterstützen auch vielfältiger Funktionen zum Extrahieren von Untersequenzen.

Viele Datentypen, z. B. Listen, Arrays, Gruppen und Zuordnungen sind Sequenzen implizit, da sie aufzählbare Sammlungen sind. Eine Funktion, die eine Sequenz akzeptiert, da ein Argument mit einem allgemeinen f#-Datentypen, darüber hinaus in einen .NET Framework-Datentyp verwendet werden kann, die implementiert `System.Collections.Generic.IEnumerable<'T>`. Vergleichen Sie dies auf eine Funktion, die eine Liste als Argument akzeptiert, der nur Listen dauern kann. Der Typ `seq<'T>` ist eine typabkürzung für `IEnumerable<'T>`. Dies bedeutet, dass jeder Typ, die generische implementiert `System.Collections.Generic.IEnumerable<'T>`festlegt einschließlich Arrays, Listen und Zuordnungen in f# und auch die meisten .NET Framework-Auflistungstypen, ist kompatibel mit der `seq` geben und kann verwendet werden, wo eine Sequenz erwartet wird.

## <a name="module-functions"></a>Modulfunktionen

Die [Seq-Modul](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) in die [Microsoft.FSharp.Collections-Namespace](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) enthält Funktionen zum Arbeiten mit Sequenzen. Diese Funktionen arbeiten mit Listen, Arrays, Zuordnungen und Sätze auch auf, da alle diese Typen enumerable sind und daher als Sequenzen behandelt werden kann.

## <a name="creating-sequences"></a>Erstellen von Sequenzen

Sie können Tasksequenzen mithilfe von Sequenzausdrücken, wie zuvor beschrieben oder mithilfe von bestimmten Funktionen erstellen.

Sie können eine leere Sequenz erstellen, mit [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), oder erstellen Sie eine Sequenz von nur einem angegebenen Element, mit [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

Sie können [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) zum Erstellen einer Sequenz, für die die Elemente erstellt werden, mithilfe einer Funktion, die Sie bereitstellen. Sie bieten auch eine Größe für die Sequenz. Diese Funktion ist ebenso wie [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), außer dass die Elemente nicht erstellt werden, bis Sie durch die Reihenfolge durchlaufen. Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.init`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

Ausgabe:

```
0 10 20 30 40
```

Mithilfe von [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) und [Seq.ofList&#60;t&#62; Funktion](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), können Sie Sequenzen von Arrays und Listen erstellen. Allerdings können Sie auch Arrays und Listen, Sequenzen konvertieren, indem mit einem Umwandlungsoperator. Beide Verfahren werden im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

Mithilfe von [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), erstellen Sie eine Sequenz aus einer schwach typisierte Sammlung, z. B. die in definierten `System.Collections`. Solche schwach typisierten Auflistungen haben den Typ des Elements `System.Object` und werden aufgelistet, die nicht generische mit `System.Collections.Generic.IEnumerable&#96;1` Typ. Der folgende Code veranschaulicht die Verwendung von `Seq.cast` konvertieren eine `System.Collections.ArrayList` in eine Sequenz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

Sie können eine unendliche Sequenzen definieren, mit der [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) Funktion. Für die eine Sequenz Geben Sie eine Funktion, die jedes Element aus dem Index des Elements generiert. Unendliche Sequenzen sind aufgrund der verzögerten Auswertung möglich. Elemente werden erstellt, je nach Bedarf durch Aufrufen der Funktion, die Sie angeben. Das folgende Codebeispiel erstellt eine infinite Sequenz von Gleitkommazahlen, in diesem Fall die abwechselnde Reihe der Umkehrwerte Quadraten von aufeinander folgenden ganzen Zahlen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) generiert eine Sequenz von einer Berechnungsfunktion, die von einem Zustand transformiert, um die nachfolgenden Elemente in der Sequenz zu erzeugen. Der Zustand ist nur ein Wert, der verwendet, um jedes Element berechnen und kann ändern, wenn jedes Element berechnet wird. Das zweite Argument für `Seq.unfold` ist der anfängliche Wert, der zum Starten der Sequenz verwendet wird. `Seq.unfold` verwendet einen Optionstyp für den Zustand, dadurch können Sie die Sequenz durch Rückgabe beendet die `None` Wert. Der folgende Code zeigt zwei Beispiele für Sequenzen `seq1` und `fib`, von erzeugte eine `unfold` Vorgang. Die erste `seq1`, nur eine einfache Sequenz mit Zahlen bis zu 100 ist. Der zweite `fib`, verwendet `unfold` der Fibonacci-Folge berechnet. Da jedes Element in der Fibonacci-Folge die Summe der beiden vorherigen Fibonacci-Zahlen ist, wird der Status-Wert ein Tupel, die aus den beiden vorherigen Zahlen in der Sequenz besteht. Der Anfangswert ist `(1,1)`, die ersten beiden Zahlen in der Sequenz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

Die Ausgabe lautet wie folgt:

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Der folgende Code ist ein Beispiel, das viele der hier beschriebenen zum Generieren und Berechnen der Werte von unendlichen Sequenzen Sequenz Modulfunktionen verwendet. Der Code kann einige Minuten dauern.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]

## <a name="searching-and-finding-elements"></a>Suchen und Suchen von Elementen

Sequenzen unterstützen Funktionen zur Verfügung, mit Listen: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq. exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), und [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Die Versionen dieser Funktionen, die für Sequenzen verfügbar sind, bewerten die Sequenz nur bis zu das Element, das nach der gesucht werden. Beispiele finden Sie in [listet](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).

## <a name="obtaining-subsequences"></a>Abrufen von Untersequenzen

[Seq.Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) und [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) sind den entsprechenden Funktionen, die für Listen, verfügbar sind, mit dem Unterschied, dass die Filterung und die Auswahl erfolgt erst, wenn die Sequenzelemente ausgewertet werden.

[Seq.Truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) wird eine Sequenz aus einer anderen Sequenz erstellt, jedoch wird die Sequenz mit einer angegebenen Anzahl von Elementen beschränkt. [Seq.Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) erstellt eine neue Sequenz, die nur eine angegebene Anzahl von Elementen ab dem Anfang einer Sequenz enthält. Wenn es weniger Elemente in der Sequenz als Sie angeben, dass in Anspruch nehmen, `Seq.take` löst eine `System.InvalidOperationException`. Der Unterschied zwischen `Seq.take` und `Seq.truncate` ist, die `Seq.truncate` ergibt keinen Fehler aus, wenn die Anzahl der Elemente ist weniger als die Zahl geben Sie an.

Der folgende Code zeigt das Verhalten und die Unterschiede zwischen `Seq.truncate` und `Seq.take`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

Die Ausgabe, lautet bevor der Fehler auftritt, wie folgt.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

Mithilfe von [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), Sie können eine Prädikatfunktion (eine boolesche Funktion) angeben und erstellen Sie eine Sequenz aus einer anderen Sequenz, die die Elemente der ursprünglichen Sequenz für die das Prädikat besteht `true`, aber beendet. vor dem ersten Element, das für die das Prädikat zurückgibt `false`. [Seq.Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) gibt eine Sequenz, die überspringt eine angegebene Anzahl der ersten Elemente einer anderen Sequenz und gibt die übrigen Elemente zurück. [Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) gibt eine Sequenz, die die ersten Elemente einer anderen Sequenz überspringt, solange das Prädikat zurückgibt `true`, und gibt dann die übrigen Elemente, beginnend mit dem ersten Element, das für die das Prädikat zurückgibt`false`.

Das folgende Codebeispiel veranschaulicht das Verhalten von und die Unterschiede zwischen `Seq.takeWhile`, `Seq.skip`, und `Seq.skipWhile`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

Die Ausgabe lautet wie folgt.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Transformieren von Sequenzen

[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) erstellt eine neue Sequenz, in dem aufeinander folgende Elemente der Eingabesequenz in Tupel gruppiert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) ähnelt `Seq.pairwise`, außer dass statt einer Sequenz von Tupeln, eine Sequenz von Arrays erzeugt wird, die Kopien der benachbarte Elemente enthalten (eine *Fenster*) aus der Sequenz. Sie geben die Anzahl der benachbarte Elemente, die Sie möchten in jedem Array.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.windowed`. In diesem Fall ist die Anzahl der Elemente im Fenster 3. Im Beispiel wird `printSeq`, die im vorherigen Codebeispiel definiert ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet180.fs)]

Die Ausgabe lautet wie folgt.

Ursprüngliche Sequenz:

```
1.0 1.5 2.0 1.5 1.0 1.5 

Windows of length 3: 
[|1.0; 1.5; 2.0|] [|1.5; 2.0; 1.5|] [|2.0; 1.5; 1.0|] [|1.5; 1.0; 1.5|] 

Moving average: 
1.5 1.666666667 1.5 1.333333333
```

## <a name="operations-with-multiple-sequences"></a>Operationen mit mehreren Sequenzen

[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) und [Seq. zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) zwei oder drei Sequenzen und generieren eine Sequenz von Tupeln. Diese Funktionen sind den entsprechenden Funktionen zur [listet](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). Es gibt keine entsprechende Funktionalität, um eine Sequenz, die in mindestens zwei Sequenzen zu trennen. Wenn Sie diese Funktion für eine Sequenz benötigen, konvertieren Sie die Sequenz in eine Liste, und verwenden [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).

## <a name="sorting-comparing-and-grouping"></a>Sortieren, vergleichen und gruppieren

Sortierfunktionen für Listen unterstützt, funktionieren auch mit Sequenzen. Dies schließt [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) und [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Diese Funktionen durchlaufen die gesamte Sequenz ab.

Sie vergleichen zwei Sequenzen mithilfe der [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) Funktion. Die Funktion vergleicht aufeinander folgende Elemente wiederum und wird beendet, wenn er das erste ungleichen Paar trifft. Alle zusätzlichen Elemente tragen nicht auf den Vergleich.

Im folgenden Code wird die Verwendung von `Seq.compareWith` veranschaulicht:

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

Im vorherigen Code wird nur das erste Element wird berechnet und überprüft, und das Ergebnis ist 1.

[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) akzeptiert eine Funktion, die einen Wert generiert eine *Schlüssel* für jedes Element. Ein Schlüssel wird für jedes Element durch Aufrufen dieser Funktion auf jedes Element generiert. `Seq.countBy` Gibt zurück, klicken Sie dann eine Sequenz, die enthält die Schlüsselwerte und der Anzahl von Elementen, die jeder Wert des Schlüssels generiert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

Die Ausgabe lautet wie folgt.

```
(1, 34) (2, 33) (0, 33)
```

Die vorherige Ausgabe zeigt, dass 34 Elemente der ursprünglichen Sequenz, die erzeugt die Taste 1, 33-Werte, die den Schlüssel 2 erzeugt und 33 Werte, die den Schlüssel 0 erstellt wurden.

Sie können Elemente einer Sequenz von Aufrufen gruppieren [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy` nimmt eine Sequenz und eine Funktion, die einen Schlüssel aus einem Element generiert. Die Funktion wird für jedes Element der Sequenz ausgeführt werden. `Seq.groupBy` Gibt eine Sequenz von Tupeln, die, in dem das erste Element jedes Tupels ist der Schlüssel und das zweite ist eine Sequenz von Elementen, die diesen Schlüssel zu generieren.

Das folgende Codebeispiel zeigt die Verwendung von `Seq.groupBy` die Sequenz von Zahlen von 1 bis 100 in drei Gruppen partitionieren, die unterschiedliche Schlüsselwerte sind 0, 1 und 2 aufweisen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

Die Ausgabe lautet wie folgt.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Sie können eine Sequenz, die doppelte Elemente durch den Aufruf erstellen [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). Sie können auch [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), der akzeptiert eine Schlüsselgenerierungsfunktionalität auf jedes Element aufgerufen werden. Die resultierende Sequenz enthält Elemente der ursprünglichen Sequenz, die einen eindeutigen Schlüssel aufweisen. nachfolgende Elemente, die einen doppelten Schlüssel zu einem früheren Element zu erstellen, werden verworfen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.distinct`. `Seq.distinct` wird veranschaulicht, durch das Generieren von Sequenzen, die binäre Zahlen darstellen, und klicken Sie dann angezeigt, die nur unterschiedliche Elemente 0 und 1 sind.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

Der folgende Code veranschaulicht `Seq.distinctBy` indem beginnend mit der eine Sequenz, negative und positive Zahlen enthält, und die Absolutwertfunktion als die Funktion. Die resultierende Sequenz fehlen alle positiven Zahlen, die den negative Zahlen in der Sequenz entsprechen, da die negativen Zahlen weiter oben in der Sequenz werden und aus diesem Grund anstelle der positiven Zahlen, die den gleichen absoluten ausgewählt werden Wert oder Schlüssel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]

## <a name="readonly-and-cached-sequences"></a>Schreibgeschützte und zwischengespeicherte Sequenzen

[Seq.ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) erstellt eine schreibgeschützte Kopie einer Sequenz. `Seq.readonly` ist nützlich, wenn Sie eine Auflistung mit Lese-/ Schreibzugriff, z. B. ein Array, und Sie nicht die ursprüngliche Auflistung ändern möchten. Diese Funktion kann verwendet werden, um datenkapselung beizubehalten. Im folgenden Codebeispiel wird ein Typ, der ein Array erstellt. Anstelle der Rückgabe eines Arrays, gibt eine Sequenz, die aus dem Array erstellt wird, jedoch eine Eigenschaft verfügbar macht, das Array `Seq.readonly`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq.Cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) erstellt eine gespeicherte Version einer Sequenz. Verwenden Sie `Seq.cache` um eine erneute Auswertung einer Sequenz oder zu vermeiden, wenn Sie mehrere Threads, die eine Sequenz zu verwenden, aber Sie müssen sicherstellen, dass jedes Element nur einmal verarbeitet wird. Bei einer Sequenz, die von mehreren Threads verwendet wird, dass ein Thread, die zählt, und berechnet die Werte für der ursprünglichen Sequenz und verbleibenden Threads können die zwischengespeicherte Sequenz.

## <a name="performing-computations-on-sequences"></a>Ausführen von Berechnungen für Sequenzen

Einfache arithmetische Operationen sind vergleichbar mit denen der Listen, z. B. [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)und so weiter.

[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), und [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) sind den entsprechenden Funktionen, die für Listen verfügbar sind. Sequenzen unterstützen eine Teilmenge der vollständigen Varianten dieser Funktionen, die Unterstützung von Listen. Weitere Informationen und Beispiele finden Sie unter [listet](lists.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
