---
title: 'Schleifen: while...do-Ausdruck'
description: Sehen Sie sich an, wie der while-... "Do Expression" wird verwendet, um iterative Ausführung (Schleifen) auszuführen, während eine angegebene Test Bedingung "true" ist.
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216632"
---
# <a name="loops-whiledo-expression"></a>Schleifen: while...do-Ausdruck

Der `while...do` Ausdruck wird verwendet, um iterative Ausführung (Schleifen) auszuführen, während eine angegebene Test Bedingung "true" ist.

## <a name="syntax"></a>Syntax

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Hinweise

Der *Test Ausdruck* wird ausgewertet. Wenn dies der `true`Fall ist, wird der *Text Ausdruck* ausgeführt, und der Test Ausdruck wird erneut ausgewertet. Der *Text Ausdruck* muss den Typ `unit`aufweisen. Wenn der Test Ausdruck ist `false`, wird die Iterationen beendet.

Das folgende Beispiel veranschaulicht die Verwendung des `while...do` -Ausdrucks.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

Die Ausgabe des vorherigen Codes ist ein Stream von Zufallszahlen zwischen 1 und 20, der letzte Wert ist 10.

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> Sie können in `while...do` Sequenz Ausdrücken und anderen Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `while...do` des Ausdrucks verwendet. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Berechnungs Ausdrücke](computation-expressions.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Loops `for...in`Begriff](loops-for-in-expression.md)
- [Loops `for...to`Begriff](loops-for-to-expression.md)
