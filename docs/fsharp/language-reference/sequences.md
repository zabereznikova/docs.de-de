---
title: Sequenzen (F#)
description: "Erfahren Sie, wie f# Sequenzen zu verwenden, wenn Sie einen großen geordnete Auflistung von Daten haben, aber nicht notwendigerweise erwarten, dass alle Elemente verwenden."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 23dc7d75-cd26-4df2-9be3-9d1aba5c4443
ms.openlocfilehash: b0562a6efbd2398cd8730bb835a1833955fee1c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="sequences"></a>Sequenzen

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Ein *Sequenz* ist eine logische Reihe von Elementen eines einzigen Typs. Sequenzen sind besonders nützlich, wenn Sie eine große geordnete Auflistung von Daten sich nicht unbedingt erwarten alle Elemente verwenden. Einzelne Sequenz, die Elemente, nur als berechnet werden erforderlich, damit eine Sequenz eine bessere Leistung als eine Liste in Situationen bereitstellen kann, in denen nicht alle Elemente verwendet werden. Sequenzen werden dargestellt, indem die `seq<'T>` Typ, der einen Alias für `System.Collections.Generic.IEnumerable`. Aus diesem Grund alle .NET Framework-Typ, der implementiert `System.IEnumerable` als Sequenz verwendet werden können. Die [Seq-Modul](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) bietet Unterstützung für Manipulationen mit Sequenzen.

## <a name="sequence-expressions"></a>Sequenzausdrücke
Ein *Sequenz Ausdruck* ist ein Ausdruck, der eine Sequenz ergibt. Sequenzausdrücke können verschiedene Formen aufweisen. Die einfachste Form gibt einen Bereich an. Beispielsweise `seq { 1 .. 5 }` erstellt eine Sequenz, die fünf Elemente enthält, einschließlich der Endpunkte, 1 und 5. Sie können auch ein Inkrement (oder Dekrement anzugeben) zwischen zwei doppelten Zeiträumen. Im folgenden Code wird z. B. die Sequenz der Vielfache von 10 erstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1502.fs)]

Sequenzausdrücke bestehen aus f#-Ausdrücke, die Werte der Sequenz zu erzeugen. Sie können die `yield` Schlüsselwort, um Werte zu produzieren, die Bestandteil der Sequenz.

Es folgt ein Beispiel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1503.fs)]

Können Sie die `->` Operator anstelle von `yield`, in diesem Fall können Sie weglassen der `do` -Schlüsselwort, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1504.fs)]

Der folgende Code generiert eine Liste der Koordinatenpaare zusammen mit einem Index in ein Array, das Raster darstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1505.fs)]

Ein `if` verwendete Ausdruck in einer Sequenz ist ein Filter. Beispielsweise generiert eine Sequenz von nur Primzahlen, vorausgesetzt, dass Sie eine Funktion haben `isprime` des Typs `int -> bool`, erstellen Sie die Sequenz wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1506.fs)]

Bei Verwendung von `yield` oder `->` in einer Iteration jeder Iteration wird erwartet, dass ein einzelnes Element der Sequenz zu generieren. Wenn jede Iteration eine Sequenz von Elementen erzeugt, verwenden Sie `yield!`. In diesem Fall werden die Elemente in jeder Iteration generierten verkettet, um die endgültige Sequenz zu erzeugen.

Sie können mehrere Ausdrücke zusammen in einem Sequenzausdruck kombinieren. Die von jedem Ausdruck generierten Elemente werden verkettet. Ein Beispiel finden Sie unter dem Abschnitt "Beispiele" dieses Themas.

## <a name="examples"></a>Beispiele
Im ersten Beispiel wird ein Sequenzausdruck, die einer Iteration, einem Filter und eine Yield generieren Sie ein Array enthält. Dieser Code wird eine Sequenz von Primzahlen zwischen 1 und 100 an die Konsole ausgegeben.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1507.fs)]

Der folgende code verwendet `yield` eine Multiplikationstabelle erstellen, die aus Tupeln von drei Elementen, jede bestehend aus zwei Faktoren und das Produkt besteht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1508.fs)]

Das folgende Beispiel veranschaulicht die Verwendung von `yield!` einzelne Sequenzen zu einer einzigen endgültigen Sequenz zusammengefasst. In diesem Fall werden die Sequenzen für jede Teilstruktur einer binären Struktur in eine rekursive Funktion, um die endgültige Sequenz zu erzeugen verkettet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1509.fs)]
    
## <a name="using-sequences"></a>Verwenden von Sequenzen
Sequenzen unterstützen viele derselben Funktionen wie [listet](lists.md). Sequenzen unterstützen auch Vorgänge wie das Gruppieren und zählen mithilfe von Funktionen Schlüssel generieren. Sequenzen unterstützen auch mehr verschiedene Funktionen für das Extrahieren von Untersequenzen.

Viele Datentypen, z. B. Listen, Arrays, Mengen und Zuordnungen sind Sequenzen implizit, da sie aufzählbarer Auflistungen sind. Eine Funktion, die eine Sequenz akzeptiert, wenn ein Argument mit einem allgemeinen f#-Datentypen, darüber hinaus in einen .NET Framework-Datentyp arbeitet, die implementiert `System.Collections.Generic.IEnumerable<'T>`. Vergleichen Sie dies auf eine Funktion, die eine Liste als Argument annimmt, die nur Listen übernehmen können. Der Typ `seq<'T>` ist eine typabkürzung für `IEnumerable<'T>`. Dies bedeutet, dass jeder Typ, der die generische implementiert `System.Collections.Generic.IEnumerable<'T>`festlegt einschließlich Arrays, Listen und Zuordnungen in F# erläutert werden und auch die meisten .NET Framework-Auflistungstypen, ist kompatibel mit den `seq` geben und kann verwendet werden, wo eine Sequenz erwartet wird.


## <a name="module-functions"></a>Modulfunktionen
Die [Seq-Modul](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684) in der [Microsoft.FSharp.Collections-Namespace](https://msdn.microsoft.com/library/24f64e5f-5030-47d0-9759-8d3e398ed13f) enthält Funktionen zum Arbeiten mit Sequenzen. Diese Funktionen funktionieren mit Listen, Arrays, Zuordnungen und Sätze auch daran, dass alle diese Typen aufzählbare und daher als Sequenzen behandelt werden kann.


## <a name="creating-sequences"></a>Erstellen von Sequenzen
Sie können die Sequenzen mithilfe von Sequenzausdrücken, wie zuvor beschrieben oder mithilfe von bestimmten Funktionen erstellen.

Sie können eine leere Sequenz erstellen, mit [Seq.empty](https://msdn.microsoft.com/library/3c7f1c69-6117-4782-b2da-0e04d6854f59), oder erstellen Sie eine Sequenz von nur einem angegebenen Element, mit [Seq.singleton](https://msdn.microsoft.com/library/9b8cc460-a282-4ec5-b29a-630ab17e9de7).

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet9.fs)]

Sie können [Seq.init](https://msdn.microsoft.com/library/059de69d-812c-4f8e-be86-88aa72101576) zum Erstellen einer Sequenz, für die die Elemente erstellt werden, mithilfe einer Funktion, die Sie bereitstellen. Sie geben Sie eine Größe für die Sequenz. Diese Funktion ist ebenso wie [List.init](https://msdn.microsoft.com/library/dd38c096-0ea8-4858-be6b-794b90418b83), außer dass die Elemente nicht erstellt werden, bis Sie mit der Sequenz durchlaufen. Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.init`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet10.fs)]

Ausgabe:

```
0 10 20 30 40
```

Mithilfe von [Seq.ofArray](https://msdn.microsoft.com/library/299cd4d9-be72-4511-aac8-089e1ddaac99) und [Seq.ofList &#60; " T &#62; Funktion](https://msdn.microsoft.com/visualfsharpdocs/conceptual/seq.oflist%5b%27t%5d-function-%5bfsharp%5d), können Sie Sequenzen aus Arrays und Listen erstellen. Allerdings können Sie auch Arrays und Listen in Sequenzen konvertieren mit einem Umwandlungsoperator. Beide Verfahren werden im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet11.fs)]

Mithilfe von [Seq.cast](https://msdn.microsoft.com/library/1d087db3-a8b2-41dd-8ddc-227544529334), erstellen Sie eine Sequenz aus einer schwach typisierten Auflistung, z. B. die in definierten `System.Collections`. Solche schwach typisierten Auflistungen haben den Elementtyp `System.Object` aufgelistet werden, mit dem nichtgenerischen `System.Collections.Generic.IEnumerable&#96;1` Typ. Der folgende Code veranschaulicht die Verwendung von `Seq.cast` Konvertieren einer `System.Collections.ArrayList` in einer Sequenz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet12.fs)]

Sie können unendliche Sequenzen definieren, mit der [Seq.initInfinite](https://msdn.microsoft.com/library/d1804e53-da92-48ec-8d6e-57eaf4c62bef) Funktion. Für die eine Sequenz Geben Sie eine Funktion, die jedes Element aus dem Index des Elements generiert. Unendliche Sequenzen sind aufgrund der verzögerten Auswertung möglich. Elemente werden erstellt, je nach Bedarf durch Aufrufen der Funktion, die Sie angeben. Das folgende Codebeispiel generiert eine unendliche Sequenz von Gleitkommazahlen, in diesem Fall die abwechselnde Reihe von Umkehrwerte Quadraten von aufeinander folgenden ganzen Zahlen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet13.fs)]

[Seq.unfold](https://msdn.microsoft.com/library/7d9232fc-742e-42bc-bdf7-6f130f0eff21) generiert eine Sequenz von einer Berechnungsfunktion, die von einem Zustand transformiert, um die nachfolgenden Elemente in der Sequenz zu erzeugen. Der Status ist nur ein Wert, der verwendet, um jedes Element berechnen, und ändern kann, wie die einzelnen Elemente berechnet wird. Das zweite Argument `Seq.unfold` ist der anfängliche Wert, der verwendet wird, um die Sequenz zu starten. `Seq.unfold`verwendet einen Optionstyp für die Sequenz wird durch zurückgeben beendet wird, können den Status der `None` Wert. Der folgende Code zeigt zwei Beispiele für Sequenzen `seq1` und `fib`, von erzeugte ein `unfold` Vorgang. Die erste `seq1`, ist nur eine einfache Sequenz mit Zahlen bis 100. Die zweite `fib`, verwendet `unfold` zum Berechnen der Fibonacci-Sequenz. Da jedes Element in der Fibonacci-Sequenz die Summe der vorherigen zwei Fibonacci-Zahlen ist, wird der Status-Wert ein Tupel, aus denen die beiden vorherigen Zahlen in der Sequenz besteht. Der Anfangswert ist `(1,1)`, die ersten beiden Zahlen in der Sequenz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet14.fs)]

Die Ausgabe lautet wie folgt:

```
The sequence seq1 contains numbers from 0 to 20.

0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20

The sequence fib contains Fibonacci numbers.

2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
```

Der folgende Code ist ein Beispiel, viele der Sequenz-Modul-Funktionen, die hier beschriebenen zum Generieren und berechnen die Werte der unendlichen Sequenzen verwendet. Der Code möglicherweise Ausführung einige Minuten dauern.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet15.fs)]
    
## <a name="searching-and-finding-elements"></a>Suchen und Suchen von Elementen
Sequenzen unterstützen Funktionen, die mit Listen verfügbar: [Seq.exists](https://msdn.microsoft.com/library/428c97bf-599d-4c39-a5b9-f8717c198ad1), [Seq. exists2](https://msdn.microsoft.com/library/efdf14a4-27f7-4dc1-9281-52639e66d565), [Seq.find](https://msdn.microsoft.com/library/02c21ecd-97e5-4e99-a4c1-b4d0b730b7d8), [Seq.findIndex](https://msdn.microsoft.com/library/96dfe86b-df15-4d92-8316-7cd6055e09f3), [ Seq.pick](https://msdn.microsoft.com/library/a87bc771-55f7-43f9-94f9-33d8f9bf325d), [Seq.tryFind](https://msdn.microsoft.com/library/ac43c6f5-4dc7-4e9a-a222-00b5736aee47), und [Seq.tryFindIndex](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a). Die Versionen dieser Funktionen, die für Sequenzen verfügbaren auswerten die Sequenz nur bis zu dem Element, das nach der gesucht werden. Beispiele finden Sie unter [listet](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d).


## <a name="obtaining-subsequences"></a>Abrufen von Untersequenzen
[Seq.Filter](https://msdn.microsoft.com/library/7f2e9850-a660-460c-9831-3bbff5613770) und [Seq.choose](https://msdn.microsoft.com/library/63b83b06-4b24-4239-bf69-a2c12d891395) sind wie die entsprechenden Funktionen, die für Listen, verfügbar sind, mit dem Unterschied, dass die Filterung und die Auswahl erfolgt erst, wenn die Sequenzelemente ausgewertet werden.

[Seq.Truncate](https://msdn.microsoft.com/library/1892dfeb-308e-45e2-857a-3c3405d02244) wird eine Sequenz aus einer anderen Sequenz erstellt, jedoch wird die Sequenz auf eine angegebene Anzahl von Elementen beschränkt. [Seq.Take](https://msdn.microsoft.com/library/6e75f701-640b-4c4a-9d63-4313fc090596) erstellt eine neue Sequenz, die nur eine bestimmte Anzahl von Elementen vom Anfang einer Sequenz enthält. Wenn es weniger Elemente in der Sequenz gibt als Sie angeben, dass in Anspruch nehmen, `Seq.take` löst eine `System.InvalidOperationException`. Der Unterschied zwischen `Seq.take` und `Seq.truncate` ist, `Seq.truncate` ist einen Fehler erzeugt, wenn die Anzahl der Elemente ist weniger als die Zahl angeben, die Sie.

Der folgende Code zeigt das Verhalten und die Unterschiede zwischen `Seq.truncate` und `Seq.take`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet16.fs)]

Die Ausgabe, lautet bevor der Fehler auftritt, wie folgt.

```
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100 
1 4 9 16 25 
1 4 9 16 25 36 49 64 81 100
```

Mithilfe von [Seq.takeWhile](https://msdn.microsoft.com/library/19eea4ce-66e0-4353-b015-72eb03421d92), können Sie eine Prädikatfunktion (eine boolesche Funktion) angeben und erstellen Sie eine Sequenz aus einer anderen Sequenz bestehend aus diesen Elementen der ursprünglichen Sequenz für die das Prädikat ist `true`, aber anhalten vor dem ersten Element für die das Prädikat wieder `false`. [Seq.Skip](https://msdn.microsoft.com/library/b4eb3f08-8594-4d17-8180-852c6c688bf1) gibt eine Sequenz, überspringt die angegebene Anzahl der ersten Elemente einer anderen Sequenz und gibt die übrigen Elemente zurück. [Seq.skipWhile](https://msdn.microsoft.com/library/fb729021-2a3c-430f-83c3-0b37526f1a16) gibt eine Sequenz, die die ersten Elemente einer anderen Sequenz überspringt, solange das Prädikat `true`, und gibt dann die übrigen Elemente, beginnend mit dem ersten Element für die das Prädikat wieder `false`.

Das folgende Codebeispiel veranschaulicht das Verhalten von und die Unterschiede zwischen `Seq.takeWhile`, `Seq.skip`, und `Seq.skipWhile`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet17.fs)]

Die Ausgabe lautet wie folgt.

```
1 4 9 
36 49 64 81 100 
16 25 36 49 64 81 100
```

## <a name="transforming-sequences"></a>Transformieren von Sequenzen
[Seq.pairwise](https://msdn.microsoft.com/library/210dcf26-4e24-4d83-af6d-a8288b2ae4b1) erstellt eine neue Sequenz, in dem aufeinander folgenden Elementen der Eingabesequenz in Tupel gruppiert werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet18.fs)]

[Seq.windowed](https://msdn.microsoft.com/library/8b565b8f-d645-4dba-be22-099075fe4744) entspricht `Seq.pairwise`, außer dass statt, erzeugt eine Sequenz von Tupeln, eine Sequenz von Arrays erzeugt wird, die Kopien der benachbarten Elemente enthalten (einen *Fenster*) aus der Sequenz. Sie geben die Anzahl der benachbarten Elemente, die in jedem Array.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.windowed`. In diesem Fall ist die Anzahl von Elementen im Fenster 3. Im Beispiel wird `printSeq`, die im vorherigen Codebeispiel definiert ist.

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
[Seq.zip](https://msdn.microsoft.com/library/0a5df8bf-0d48-44ce-bff4-e8ef1df5bca4) und [Seq. zip3](https://msdn.microsoft.com/library/ef13bebb-22ae-4eb9-873b-87dd29154d16) zwei oder drei Sequenzen und erzeugt eine Sequenz von Tupeln. Diese Funktionen verhalten sich wie die entsprechenden Funktionen zur [listet](https://msdn.microsoft.com/library/83102799-f251-42e1-93ef-64232e8c5b1d). Ist keine entsprechende Funktionalität, um eine Sequenz in zwei oder mehr Sequenzen zu trennen. Wenn Sie diese Funktionalität für eine Sequenz benötigen, konvertieren Sie die Sequenz in eine Liste, und verwenden [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).


## <a name="sorting-comparing-and-grouping"></a>Sortieren, vergleichen und gruppieren
Die Sortierfunktionen für Listen unterstützt, funktionieren auch mit Sequenzen. Dies schließt [Seq.sort](https://msdn.microsoft.com/library/327ea595-e77c-4529-b61e-8c6cbf5ec92e) und [Seq.sortBy](https://msdn.microsoft.com/library/4f8b4fb9-bf20-49d9-b4ee-dcc906c8208f). Diese Funktionen durchlaufen die gesamte Sequenz ab.

Vergleichen von zwei Sequenzen mit dem [Seq.compareWith](https://msdn.microsoft.com/library/5a740135-0b3a-4545-816f-8f91cc31290f) Funktion. Die Funktion aufeinander folgenden Elementen wiederum vergleicht und wird beendet, wenn das erste ungleiche Paar gefunden wird. Alle zusätzlichen Elemente tragen nicht auf den Vergleich.

Im folgenden Code wird die Verwendung von `Seq.compareWith` veranschaulicht:

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet19.fs)]

Im vorherigen Code wird nur das erste Element wird berechnet und überprüft, und das Ergebnis ist-1.

[Seq.countBy](https://msdn.microsoft.com/library/721702a5-150e-4fe8-81cd-ffbf8476cc1f) übernimmt eine Funktion, die einen Wert mit dem generiert eine *Schlüssel* für jedes Element. Ein Schlüssel wird für jedes Element durch das Aufrufen dieser Funktion auf jedes Element generiert. `Seq.countBy`Klicken Sie dann zurückgegeben eine Sequenz, die den Schlüsselwerten und die Anzahl von Elementen, die jeder Wert des Schlüssels generiert enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet201.fs)]

Die Ausgabe lautet wie folgt.

```
(1, 34) (2, 33) (0, 33)
```

Die vorherige Ausgabe zeigt, dass 34 Elemente der ursprünglichen Sequenz, die erzeugt die Taste 1, 33 Werte, die die Schlüssel 2 erzeugt und 33 Werte, die den Schlüssel 0 erstellt wurden.

Sie können Elemente einer Sequenz von Aufrufen gruppieren [Seq.groupBy](https://msdn.microsoft.com/library/d46a04df-1a42-40cc-a368-058c9c5806fd). `Seq.groupBy`nimmt eine Sequenz und eine Funktion, die einen Schlüssel aus einem Element generiert. Die Funktion wird auf jedes Element der Sequenz ausgeführt. `Seq.groupBy`Gibt eine Sequenz von Tupeln, wobei das erste Element jedes Tupels ist der Schlüssel und das zweite ist eine Sequenz von Elementen, die diesen Schlüssel zu erzeugen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.groupBy` , die Sequenz von Zahlen von 1 bis 100 in drei Gruppen zu partitionieren, die unterschiedliche Schlüsselwerte sind 0, 1 und 2 aufweisen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet202.fs)]

Die Ausgabe lautet wie folgt.

```
(1, seq [1; 4; 7; 10; ...]) (2, seq [2; 5; 8; 11; ...]) (0, seq [3; 6; 9; 12; ...])
```

Erstellen Sie können eine Sequenz, die doppelte Elemente durch Aufrufen von [Seq.distinct](https://msdn.microsoft.com/library/99d01014-7e0e-4e7b-9d0a-41a61d93f401). Oder Sie können [Seq.distinctBy](https://msdn.microsoft.com/library/9293293b-9420-49c8-848f-401a9cd49b75), was in Anspruch nimmt eine Funktion auf jedes Element aufgerufen werden. Die resultierende Sequenz enthält Elemente der ursprünglichen Sequenz, die einen eindeutigen Schlüssel aufweisen. nachfolgende Elemente, die einen doppelten Schlüssel zu einem früheren Element erzeugt werden verworfen.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Seq.distinct`. `Seq.distinct`wird durch Generieren von Sequenzen, die binäre Zahlen darstellen, und klicken Sie dann angezeigt, die nur unterschiedliche Elemente sind 0 und 1 veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet22.fs)]

Der folgende Code zeigt `Seq.distinctBy` von beginnen mit einer Sequenz, die negative und positive Zahlen enthält und die Absolutwertfunktion wie die Funktion Schlüssel generieren. Die resultierende Sequenz fehlt die positiven Zahlen, die den negativen Zahlen in der Sequenz entsprechen, da negativen Zahlen angezeigt, weiter oben in der Sequenz werden und daher ausgewählt sind, statt die positiven Zahlen, die den gleichen absoluten haben Wert oder Schlüssel.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet23.fs)]
    
## <a name="readonly-and-cached-sequences"></a>ReadOnly "und" zwischengespeicherte Sequenzen
[Seq.ReadOnly](https://msdn.microsoft.com/library/88059cb4-3bb0-4126-9448-fbcd48fe13a7) erstellt eine schreibgeschützte Kopie einer Sequenz. `Seq.readonly`ist nützlich, wenn Sie eine Auflistung mit Lese-/ Schreibzugriff, z. B. ein Array, und Sie nicht die ursprüngliche Auflistung ändern möchten. Diese Funktion kann verwendet werden, für die datenkapselung erhalten bleiben. Im folgenden Codebeispiel wird ein Typ, der ein Array erstellt. Eine Eigenschaft verfügbar macht, Arrays, anstatt ein Array gibt eine Sequenz, die aus dem Array erstellt wird jedoch `Seq.readonly`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssequences/snippet24.fs)]

[Seq.Cache](https://msdn.microsoft.com/library/d197f9cc-08bf-4986-9869-246e72ca73f0) erstellt eine gespeicherte Version einer Sequenz. Verwenden Sie `Seq.cache` erneute Bewertung einer Sequenz oder vermeiden, wenn stehen Ihnen mehrere Threads, die eine Sequenz zu verwenden, aber Sie müssen sicherstellen, dass jedes Element nur einmal verarbeitet wird. Bei einer Sequenz, die durch mehrere Threads verwendet wird, können Sie einen Thread, die zählt, und die Werte für die ursprüngliche Sequenz berechnet haben, und verbleibenden Threads können die zwischengespeicherte Sequenz verwendet.


## <a name="performing-computations-on-sequences"></a>Ausführen von Berechnungen für Sequenzen
Einfache arithmetische Operationen entsprechen denen von Listen, z. B. [Seq.average](https://msdn.microsoft.com/library/609d793b-c70f-4e36-9ab4-d928056d65b8), [Seq.sum](https://msdn.microsoft.com/library/01208515-4880-4358-91f5-af34f66dc77a), [Seq.averageBy](https://msdn.microsoft.com/library/47c855c1-2dbd-415a-885e-b909d9d3e4f8), [Seq.sumBy](https://msdn.microsoft.com/library/68cca78c-94ed-4a45-9b8d-34d2c5f2b1b1)und so weiter.

[Seq.fold](https://msdn.microsoft.com/library/30c4c95a-9563-4c96-bbe1-f7aacfd026e3), [Seq.reduce](https://msdn.microsoft.com/library/a2ad4f64-ac69-47d2-92f0-7173d9dfeae9), und [Seq.scan](https://msdn.microsoft.com/library/7e2d23e9-f153-4411-a884-b6d415ff627e) sind wie die entsprechenden Funktionen, die für Listen verfügbar sind. Sequenzen unterstützen eine Teilmenge der vollständigen Variationen dieser Funktionen, die Listen unterstützen. Weitere Informationen und Beispiele finden Sie unter [listet](lists.md).

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[F#-Typen](fsharp-types.md)
