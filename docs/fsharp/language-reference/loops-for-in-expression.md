---
title: 'Schleifen: for...in-Ausdruck'
description: Siehe How F# for... im Ausdrucks Schleifen Konstrukt wird verwendet, um die Übereinstimmungen eines Musters in einer Aufzähl baren Auflistung zu durchlaufen.
ms.date: 05/16/2016
ms.openlocfilehash: 5a2ca59ca4199ece5d78010ff780e86ae2b25181
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216449"
---
# <a name="loops-forin-expression"></a>Schleifen: for...in-Ausdruck

Dieses Schleifen Konstrukt wird zum Durchlaufen der Übereinstimmungen eines Musters in einer Aufzähl baren Auflistung verwendet, wie z. b. ein Bereichs Ausdruck, eine Sequenz, eine Liste, ein Array oder ein anderes Konstrukt, das die Enumeration unterstützt.

## <a name="syntax"></a>Syntax

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Hinweise

Der `for...in` Ausdruck kann mit der `for each` -Anweisung in anderen .NET-Sprachen verglichen werden, da er verwendet wird, um die Werte in einer Aufzähl baren Auflistung zu durchlaufen. Unterstützt jedoch auch Muster Übereinstimmungen über die Auflistung anstelle von Iterationen über die gesamte Auflistung. `for...in`

Der Aufzähl Bare-Ausdruck kann als eine Aufzähl Bare Auflistung oder, mithilfe des `..` -Operators, als Bereich für einen ganzzahligen Typ angegeben werden. Aufzähl Bare Auflistungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen usw. Jeder Typ, der `System.Collections.IEnumerable` implementiert, kann verwendet werden.

Wenn Sie einen Bereich mithilfe des `..` -Operators Ausdrücken, können Sie die folgende Syntax verwenden.

*starten* . *ins*

Sie können auch eine Version verwenden, die ein Inkrement namens *Skip*enthält, wie im folgenden Code.

*starten* . über *springen* .. *ins*

Wenn Sie ganzzahlige Bereiche und eine einfache Counter-Variable als Muster verwenden, besteht das typische Verhalten darin, die Counter-Variable bei jeder Iterationen um 1 zu erhöhen. wenn der Bereich jedoch einen Skip-Wert enthält, wird der Leistungswert stattdessen durch den Skip-Wert erhöht.

Werte, die mit dem Muster übereinstimmen, können auch im Text Ausdruck verwendet werden.

Die folgenden Codebeispiele veranschaulichen die Verwendung des `for...in` -Ausdrucks.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

Die Ausgabe lautet wie folgt.

```console
1
5
100
450
788
```

Im folgenden Beispiel wird gezeigt, wie eine Schleife über eine Sequenz ausgeführt wird und wie ein tupelmuster anstelle einer einfachen Variablen verwendet wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

Die Ausgabe lautet wie folgt.

```console
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

Im folgenden Beispiel wird gezeigt, wie ein einfacher ganzzahliger Bereich durchlaufen wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

Die Ausgabe von Funktion1 lautet wie folgt.

```console
1 2 3 4 5 6 7 8 9 10
```

Im folgenden Beispiel wird gezeigt, wie ein Bereich mit einem Skip von 2 durchlaufen wird, der jedes andere Element des Bereichs enthält.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

Die Ausgabe von `function2` lautet wie folgt.

```console
1 3 5 7 9
```

Im folgenden Beispiel wird gezeigt, wie ein Zeichenbereich verwendet wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

Die Ausgabe von `function3` lautet wie folgt.

```console
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Im folgenden Beispiel wird gezeigt, wie ein negativer Skip-Wert für eine umgekehrte Iterationen verwendet wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

Die Ausgabe von `function4` lautet wie folgt.

```console
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

Der Anfang und das Ende des Bereichs können auch Ausdrücke sein, z. b. Funktionen, wie im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

Die Ausgabe von `function5` mit dieser Eingabe lautet wie folgt.

```console
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

Das nächste Beispiel zeigt die Verwendung eines Platzhalter Zeichens (\_), wenn das Element in der Schleife nicht benötigt wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

Die Ausgabe lautet wie folgt.

```console
Number of elements in list1: 5
```

`Note`Sie können in `for...in` Sequenz Ausdrücken und anderen Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `for...in` des Ausdrucks verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Berechnungs Ausdrücke](computation-expressions.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Loops `for...to`Begriff](loops-for-to-expression.md)
- [Loops `while...do`Begriff](loops-while-do-expression.md)
