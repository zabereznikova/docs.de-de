---
title: 'Schleifen: for...in-Ausdruck (F#)'
description: Finden Sie unter wie die f#-for... in Ausdruck Schleifenkonstrukt wird verwendet, um die Übereinstimmungen eines Musters in einer aufzählbaren Auflistung zu durchlaufen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: eaf0f4fc6419d8e0bff46795120ee5e42c4efe1d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forin-expression"></a>Schleifen: for...in-Ausdruck

Diese Schleifenkonstrukt wird verwendet, durchlaufen die Übereinstimmungen eines Musters in einer aufzählbaren Auflistung z. B. einer Range-Ausdruck, Sequenz, Liste, Array oder andere Konstrukt, das Enumeration unterstützt.


## <a name="syntax"></a>Syntax

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Hinweise
Die `for...in` Ausdruck verglichen werden kann, um die `for each` Anweisung in anderen .NET-Sprachen da er über die Werte in einer aufzählbaren Auflistung in einer Schleife verwendet wird. Allerdings `for...in` unterstützt auch Mustervergleich über der Auflistung statt nur die Iteration der gesamten Auflistung.

Der enumerable-Ausdruck kann angegeben werden, als aufzählbare Auflistung oder mithilfe der `..` -Operator, als Bereich für einen ganzzahligen Typ. Aufzählbare Auflistungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen usw. an. Jeder Typ, der implementiert `System.Collections.IEnumerable` kann verwendet werden.

Wenn Sie einen Bereich mithilfe von Ausdrücken die `..` -Operator, können Sie die folgende Syntax verwenden.

*Starten Sie* ... *Fertig stellen*

Sie können auch eine Version, die ein Inkrement aufgerufen der *überspringen*, wie im folgenden Code.

*Starten Sie* ... *Überspringen Sie* ... *Fertig stellen*

Wenn Sie ganzzahlige Bereiche und eine einfache Zählervariable als Muster verwenden, ist das normale Verhalten sich die Zählervariable erhöhen, indem bei jeder Iteration 1, aber wenn der Bereich einen Skip-Wert enthält, wird erhöht, durch den Skip-Wert stattdessen.

Das Muster übereinstimmende Werte können auch im Body-Ausdruck verwendet werden.

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

Im folgende Beispiel wird gezeigt, wie in einer Schleife auf eine Sequenz und wie Sie ein Tupelmuster statt einer einfachen Variablen verwendet.

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

Das folgende Beispiel zeigt, wie über eine einfache Integer-Bereich in einer Schleife.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

Die Ausgabe von function1 lautet wie folgt.

```
1 2 3 4 5 6 7 8 9 10
```

Das folgende Beispiel zeigt, wie in einer Schleife über einen Bereich mit einem Überspringen von 2, die jedes andere Element des Bereichs enthält.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

Die Ausgabe des `function2` lautet wie folgt.

```
1 3 5 7 9
```

Im folgende Beispiel wird gezeigt, wie einen Zeichenbereich verwendet wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

Die Ausgabe des `function3` lautet wie folgt.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Im folgende Beispiel wird gezeigt, wie einen negative Skip-Wert für eine umgekehrte Iteration verwendet wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

Die Ausgabe des `function4` lautet wie folgt.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

Der Anfang und das Ende des Bereichs können auch Ausdrücke, z. B. Funktionen, wie im folgenden Code sein.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

Die Ausgabe des `function5` mit dieser Eingabe lautet wie folgt.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

Das nächste Beispiel zeigt die Verwendung von Platzhalterzeichen (_), wenn das Element nicht in der Schleife erforderlich ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

Die Ausgabe lautet wie folgt.

```
Number of elements in list1: 5
```

`Note` Können Sie `for...in` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `for...in` Ausdruck verwendet wird. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Schleifen: `for...to`-Ausdruck](loops-for-to-expression.md)

[Schleifen: `while...do`-Ausdruck](loops-while-do-expression.md)
