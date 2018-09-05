---
title: 'Lambdaausdrücke: Das fun-Schlüsselwort (F#)'
description: Erfahren Sie, wie der F#-Schlüsselwort "Spaß" zu verwenden, um ein Lambda-Ausdruck definieren eine anonyme Funktion handelt.
ms.date: 05/16/2016
ms.openlocfilehash: a37757f6b7328cd348bbf13f058a6dbc881769cf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744287"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Lambdaausdrücke: Das fun-Schlüsselwort (F#)

Die `fun` -Schlüsselwort wird verwendet, um einen Lambdaausdruck, d. h. eine anonyme Funktion zu definieren.

## <a name="syntax"></a>Syntax

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Hinweise

Die *Parameterliste* mit Namen und optional die Typen der Parameter in der Regel besteht. Allgemeiner ausgedrückt, die *Parameterliste* bestehen keine F#-Muster. Eine vollständige Liste der möglichen Muster finden Sie unter [Musterabgleich](../pattern-matching.md). Liste der gültigen Parameter enthalten die folgenden Beispielen.

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

Die *Ausdruck* ist der Text der Funktion, von denen der letzte Ausdruck einen Wert zurückgegeben generiert. Die folgenden: Beispiele für gültige Lambda-Ausdrücke

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>Verwenden von Lambdaausdrücken

Lambda-Ausdrücke sind besonders nützlich, wenn Sie die Vorgänge auf eine Liste oder einer anderen Sammlung aus, und Definieren einer Funktion den zusätzlichen Aufwand vermeiden möchten, verwenden möchten. Viele f# Library-Funktionen nehmen die Werte von Funktionen als Argumente ein, und es kann sein, insbesondere dann hilfreich, einen Lambda-Ausdruck in diesen Fällen zu verwenden. Der folgende Code gilt einen Lambda-Ausdruck, für die Elemente einer Liste. In diesem Fall wird die anonyme Funktion 1 auf jedes Element einer Liste hinzugefügt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
