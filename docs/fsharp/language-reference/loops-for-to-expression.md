---
title: 'Schleifen: for...to-Ausdruck (F#)'
description: Finden Sie unter wie die f#-for... in Ausdruck verwendet, um einen Wertebereich einer Schleifenvariablen in einer Schleife zu durchlaufen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 95a8960d71c82c01118d2e71479fc0ec5298a02b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forto-expression"></a><span data-ttu-id="46a98-103">Schleifen: for...to-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="46a98-103">Loops: for...to Expression</span></span>

<span data-ttu-id="46a98-104">Die `for...to` Ausdruck wird verwendet, um einen Wertebereich einer Schleifenvariablen in einer Schleife zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="46a98-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="46a98-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="46a98-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="46a98-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46a98-106">Remarks</span></span>
<span data-ttu-id="46a98-107">Der Typ des Bezeichners wird abgeleitet, von dem Typ des der *starten* und *Fertig stellen* Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="46a98-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="46a98-108">Typen, die für diese Ausdrücke müssen 32-Bit-Ganzzahlen sein.</span><span class="sxs-lookup"><span data-stu-id="46a98-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="46a98-109">Obwohl technisch gesehen ist ein Ausdruck, `for...to` ist eher wie eine herkömmliche Anweisung in einem imperativen Programmiersprache ab.</span><span class="sxs-lookup"><span data-stu-id="46a98-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="46a98-110">Der Rückgabetyp für die *Text-Ausdruck* muss `unit`.</span><span class="sxs-lookup"><span data-stu-id="46a98-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="46a98-111">Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der der `for...to` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="46a98-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="46a98-112">Der obige Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="46a98-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="46a98-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46a98-113">See Also</span></span>
[<span data-ttu-id="46a98-114">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="46a98-114">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="46a98-115">Schleifen: `for...in`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="46a98-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="46a98-116">Schleifen: `while...do`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="46a98-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
