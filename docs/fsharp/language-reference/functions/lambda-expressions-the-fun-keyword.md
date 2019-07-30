---
title: 'Lambda-Ausdrücke: Das fun-Schlüsselwort'
description: Erfahren Sie, wie Sie F# das Schlüsselwort "Fun" verwenden, um einen Lambda-Ausdruck zu definieren, der eine anonyme Funktion ist.
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630666"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Lambda-Ausdrücke: Das Fun-SchlüsselF#Wort ()

Das `fun` -Schlüsselwort wird verwendet, um einen Lambda-Ausdruck, d. h. eine anonyme Funktion, zu definieren.

## <a name="syntax"></a>Syntax

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Hinweise

Die *Parameter-List* besteht in der Regel aus Namen und optional Typen von Parametern. Im Allgemeinen kann die *Parameter-List* aus beliebigen F# Mustern bestehen. Eine vollständige Liste möglicher Muster finden Sie unter [Muster](../pattern-matching.md)Abgleich. In den folgenden Beispielen finden Sie Listen gültiger Parameter.

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

Der *Ausdruck* ist der Hauptteil der Funktion. der letzte Ausdruck von, der einen Rückgabewert generiert. Beispiele für gültige Lambda-Ausdrücke:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>Verwenden von Lambdaausdrücken

Lambda-Ausdrücke sind besonders nützlich, wenn Sie Vorgänge für eine Liste oder eine andere Auflistung ausführen möchten und die zusätzliche Arbeit beim Definieren einer Funktion vermeiden möchten. Viele F# Library-Funktionen nehmen die Werte von Funktionen als Argumente ein, und es kann sein, insbesondere dann hilfreich, einen Lambda-Ausdruck in diesen Fällen zu verwenden. Der folgende Code wendet einen Lambda-Ausdruck auf Elemente einer Liste an. In diesem Fall fügt die anonyme Funktion jedem Element einer Liste 1 hinzu.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
