---
title: "Lambdaausdrücke: Das fun-Schlüsselwort (F#)"
description: "Erfahren Sie, wie das 'Fun'-Schlüsselwort [F#] zu verwenden, um einen Lambda-Ausdruck zu definieren, der einer anonymen Funktion wird."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Lambdaausdrücke: Das fun-Schlüsselwort (F#)

Die `fun` Schlüsselwort wird verwendet, um einen Lambda-Ausdruck, d. h. einer anonymen Funktion definieren.


## <a name="syntax"></a>Syntax

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Hinweise
Die *Parameterliste* besteht normalerweise aus Namen und optional die Typen der Parameter. Allgemeiner gesagt ist der *Parameterliste* können bestehen keine f#-Muster. Eine vollständige Liste der möglichen Muster finden Sie unter [Mustervergleich](../pattern-matching.md). Listen gültige Parameter werden in den folgenden Beispielen.

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

Die *Ausdruck* ist der Text der Funktion, von denen der letzte Ausdruck einen Rückgabewert generiert. Die folgenden: Beispiele für gültige Lambda-Ausdrücke

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a>Verwenden von Lambdaausdrücken
Lambda-Ausdrücke sind besonders nützlich, wenn Sie möchten, um Vorgänge auf eine Liste oder einer anderen Sammlung auszuführen und eine Funktion definieren den zusätzlichen Aufwand vermeiden möchten. Viele f#-Bibliotheksfunktionen nehmen Funktionswerte als Argumente ein, und es kann besonders praktisch, einen Lambda-Ausdruck in diesen Fällen zu verwenden. Der folgende Code wendet einen Lambda-Ausdruck auf Elemente einer Liste. In diesem Fall fügt 1 mit die anonyme Funktion auf jedes Element einer Liste hinzu.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a>Siehe auch
[Funktionen](index.md)
