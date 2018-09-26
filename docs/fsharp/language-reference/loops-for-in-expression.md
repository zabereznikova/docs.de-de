---
title: 'Schleifen: for...in-Ausdruck (F#)'
description: Finden Sie unter wie der F#-for... in Ausdruck Schleifenkonstrukt zum Durchlaufen der Übereinstimmungen eines Musters in einer aufzählbaren Auflistung verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: c4fba1f1dea3993cafa2e37ad0f32d9fb2eed85a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087183"
---
# <a name="loops-forin-expression"></a>Schleifen: for...in-Ausdruck

Diese Schleifenkonstrukt wird zum Durchlaufen der Übereinstimmungen eines Musters in einer aufzählbaren Auflistung wie z. B. einen Bereichsausdruck, Sequenz, Liste, Array oder anderes Konstrukt, das Enumerationen unterstützt.

## <a name="syntax"></a>Syntax

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Hinweise

Die `for...in` Ausdruck verglichen werden kann, um die `for each` Anweisung in anderen .NET-Sprachen da er in einer Schleife auf die Werte in einer aufzählbaren Auflistung verwendet wird. Allerdings `for...in` unterstützt auch Musterabgleich, die über die Sammlung nicht nur die Iteration über die gesamte Auflistung.

Der enumerable-Ausdruck kann angegeben werden, als aufzählbare Auflistung oder mithilfe der `..` -Operator, wie ein Bereich auf einen ganzzahligen Typ. Aufzählbare Sammlungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen und So weiter. Jeder Typ, der implementiert `System.Collections.IEnumerable` kann verwendet werden.

Wenn Sie einen Bereich mithilfe von Ausdrücken die `..` -Operator, können Sie die folgende Syntax verwenden.

*Starten Sie* ... *Fertig stellen*

Können Sie auch eine Version, ein Inkrement wird aufgerufen, beinhaltet, die *überspringen*, wie im folgenden Code.

*Starten Sie* ... *Überspringen Sie* ... *Fertig stellen*

Wenn Sie ganzzahlige Bereiche und eine einfache Counter-Variable als Muster verwenden, in der Regel werden die Zählervariable um 1 bei jeder Iteration zu erhöhen, aber wenn der Bereich einen Skip-Wert enthält, wird erhöht, durch den Skip-Wert stattdessen.

Werte, die im Muster übereinstimmen, können auch im Body-Ausdruck verwendet werden.

Die folgenden Codebeispiele veranschaulichen die Verwendung der `for...in` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

Die Ausgabe lautet wie folgt.

```
1
5
100
450
788
```

Das folgende Beispiel zeigt, wie in einer Sequenz eine Schleife durchlaufen, und wie Sie ein Tupelmuster anstelle einer einfachen Variable verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

Die Ausgabe lautet wie folgt.

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

Das folgende Beispiel zeigt, wie Sie eine Schleife über einen einfachen ganzzahligen Bereich durchlaufen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

Die Ausgabe von function1 lautet wie folgt aus.

```
1 2 3 4 5 6 7 8 9 10
```

Das folgende Beispiel zeigt, wie in einer Schleife über einen Bereich mit einem Skip 2, die jedes andere Element des Bereichs enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

Die Ausgabe des `function2` lautet wie folgt.

```
1 3 5 7 9
```

Das folgende Beispiel zeigt, wie Sie mit einem Bereich von Zeichen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

Die Ausgabe des `function3` lautet wie folgt.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Das folgende Beispiel zeigt, wie Sie einen negativen Skip-Wert für eine umgekehrte Iteration zu verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

Die Ausgabe des `function4` lautet wie folgt.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

Der Anfang und das Ende des Bereichs können auch Ausdrücke, wie z. B. Funktionen, wie im folgenden Code sein.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

Die Ausgabe des `function5` mit dieser Eingabe lautet wie folgt.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

Das nächste Beispiel zeigt die Verwendung eines Platzhalterzeichens (\_) Wenn das Element nicht in der Schleife erforderlich ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

Die Ausgabe lautet wie folgt.

```
Number of elements in list1: 5
```

`Note` Können Sie `for...in` in Sequenzausdrücken und anderen Berechnungsausdrücken in diesem Fall, dass eine angepasste Version von der `for...in` Ausdruck wird verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)
- [Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)
