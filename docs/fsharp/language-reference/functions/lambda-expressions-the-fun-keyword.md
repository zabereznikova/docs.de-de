---
title: 'Lambda-Ausdrücke: Das Fun-Schlüsselwort'
description: Erfahren Sie, wie Sie mit der F# "Fun"-Schlüsselwort, um ein Lambda-Ausdruck definieren, die eine anonyme Funktion ist.
ms.date: 05/16/2016
ms.openlocfilehash: 6ad15173bb8643bff330e3ca3823cba5d43ad445
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941023"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Lambda-Ausdrücke: Das Fun-Schlüsselwort (F#)

Die `fun` -Schlüsselwort wird verwendet, um einen Lambdaausdruck, d. h. eine anonyme Funktion zu definieren.

## <a name="syntax"></a>Syntax

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Hinweise

Die *Parameterliste* mit Namen und optional die Typen der Parameter in der Regel besteht. Allgemeiner ausgedrückt, die *Parameterliste* bestehen alle F# Muster. Eine vollständige Liste der möglichen Muster finden Sie unter [Musterabgleich](../pattern-matching.md). Liste der gültigen Parameter enthalten die folgenden Beispielen.

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

Lambda-Ausdrücke sind besonders nützlich, wenn Sie die Vorgänge auf eine Liste oder einer anderen Sammlung aus, und Definieren einer Funktion den zusätzlichen Aufwand vermeiden möchten, verwenden möchten. Viele F# Library-Funktionen nehmen die Werte von Funktionen als Argumente ein, und es kann sein, insbesondere dann hilfreich, einen Lambda-Ausdruck in diesen Fällen zu verwenden. Der folgende Code gilt einen Lambda-Ausdruck, für die Elemente einer Liste. In diesem Fall wird die anonyme Funktion 1 auf jedes Element einer Liste hinzugefügt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)