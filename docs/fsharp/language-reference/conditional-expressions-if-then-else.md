---
title: 'Bedingte Ausdrücke: if... then...else (F#)'
description: Erfahren Sie, wie Sie bedingte Ausdrücke in f# zum Ausführen der unterschiedliche Codezweige geschrieben.
ms.date: 05/16/2016
ms.openlocfilehash: 10e4224bef772f00520cf5a0fff2f2920147c2fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890868"
---
# <a name="conditional-expressions-ifthenelse"></a>Bedingte Ausdrücke: `if...then...else`

Die `if...then...else` Ausdruck unterschiedliche Codezweige ausführt und auch auf einen anderen Wert je nach angegebenem booleschen Ausdruck ausgewertet wird.

## <a name="syntax"></a>Syntax

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *expression1* ausgeführt wird, wenn der boolesche Ausdruck ergibt `true`ist, andernfalls *expression2* ausgeführt wird.

Anders als in anderen Sprachen, die `if...then...else` Konstrukt ist ein Ausdruck, der keine Anweisung. Das bedeutet, dass sie einen Wert erzeugt, das den Wert des letzten Ausdrucks im Branch, der ausgeführt wird. Die Typen der Werte produziert, die in jeder Verzweigung müssen übereinstimmen. Wenn es keine explizite ist `else` Branch, der Typ ist `unit`. Aus diesem Grund, wenn der Typ des der `then` Branch ist ein beliebiger Typ außer `unit`, muss vorhanden sein ein `else` Branch mit den gleichen Rückgabetyp. Beim Verketten `if...then...else` Ausdrücke, können Sie das Schlüsselwort `elif` anstelle von `else if`; sie gleichwertig sind.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, wie Sie mit der `if...then...else` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
