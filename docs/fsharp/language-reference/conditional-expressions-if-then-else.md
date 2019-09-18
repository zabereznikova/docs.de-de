---
title: 'Bedingte Ausdrücke: If... dann... woanders'
description: Erfahren Sie, wie Sie bedingte Ausdrücke in F# zum Ausführen der unterschiedliche Codezweige geschrieben.
ms.date: 05/16/2016
ms.openlocfilehash: d9763f37cd9170c42e968282b54a3ce925e92591
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083030"
---
# <a name="conditional-expressions-ifthenelse"></a>Bedingte Ausdrücke:`if...then...else`

Der `if...then...else` Ausdruck führt verschiedene Code Verzweigungen aus und wird abhängig vom angegebenen booleschen Ausdruck auch zu einem anderen Wert ausgewertet.

## <a name="syntax"></a>Syntax

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird *expression1* ausgeführt, wenn der boolesche Ausdruck `true`ergibt; andernfalls wird *expression2* ausgeführt.

Anders als in anderen Sprachen ist `if...then...else` das Konstrukt ein Ausdruck, nicht eine-Anweisung. Dies bedeutet, dass ein Wert erzeugt wird, bei dem es sich um den Wert des letzten Ausdrucks in der Verzweigung handelt, die ausgeführt wird. Die Typen der in den einzelnen Verzweigungen erzeugten Werte müssen mit identisch sein. Wenn keine explizite `else` Verzweigung vorhanden ist, ist `unit`der Typ. Wenn der Typ der `then` Verzweigung ein anderer Typ als `unit`ist, muss daher eine `else` Verzweigung mit dem gleichen Rückgabetyp vorhanden sein. Wenn Sie `if...then...else` Ausdrücke verketten, können Sie das-Schlüssel `elif` Wort anstelle `else if`von verwenden. Sie sind gleichwertig.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie der `if...then...else` -Ausdruck verwendet wird.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```console
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
