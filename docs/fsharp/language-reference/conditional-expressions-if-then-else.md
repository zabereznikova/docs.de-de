---
title: 'Bedingte Ausdrücke: if... then...else (F#)'
description: Erfahren Sie, wie bedingte Ausdrücke in f# zum Ausführen von anderen Verzweigungen von Code zu schreiben.
ms.date: 05/16/2016
ms.openlocfilehash: a3ca3c20a659ccf5dc432d0a747ff176ec889e9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563132"
---
# <a name="conditional-expressions-ifthenelse"></a>Bedingte Ausdrücke: `if...then...else`

Die `if...then...else` Ausdruck unterschiedliche Zweige der Code ausgeführt und wertet auch auf einen anderen Wert je nach den booleschen Ausdruck angegeben.


## <a name="syntax"></a>Syntax

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax *expression1* ausgeführt wird, wenn der boolesche Ausdruck ergibt `true`ist, andernfalls *expression2* ausgeführt wird.

Anders als in anderen Sprachen, die `if...then...else` Konstrukt ist ein Ausdruck, der keine Anweisung. Das bedeutet, dass es einen Wert erzeugt, der über den Wert des letzten Ausdrucks in der Verzweigung ist, die ausgeführt wird. Die Typen der Werte in jeder Verzweigung erzeugt müssen übereinstimmen. Wenn es keine explizite ist `else` Branch, dessen Typ ist `unit`. Aus diesem Grund Wenn der Typ des der `then` Verzweigung ist ein beliebiger Typ außer `unit`, muss vorhanden sein ein `else` Verzweigung mit den gleichen Rückgabetyp. Beim Verketten `if...then...else` Ausdrücke zusammen, verwenden Sie das Schlüsselwort `elif` anstelle von `else if`; sie gleichwertig sind.

## <a name="example"></a>Beispiel
Das folgende Beispiel zeigt, wie die `if...then...else` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

