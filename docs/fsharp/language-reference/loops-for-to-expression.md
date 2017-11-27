---
title: 'Schleifen: for...to-Ausdruck (F#)'
description: Finden Sie unter wie die f#-for... in Ausdruck verwendet, um einen Wertebereich einer Schleifenvariablen in einer Schleife zu durchlaufen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e14c38d9-b1ef-4b7f-be9a-fb6ef6708e02
ms.openlocfilehash: 1a1d71d30b5e87e4691a78acd5032de9419399db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forto-expression"></a><span data-ttu-id="4c852-104">Schleifen: for...to-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4c852-104">Loops: for...to Expression</span></span>

<span data-ttu-id="4c852-105">Die `for...to` Ausdruck wird verwendet, um einen Wertebereich einer Schleifenvariablen in einer Schleife zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="4c852-105">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>


## <a name="syntax"></a><span data-ttu-id="4c852-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c852-106">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="4c852-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c852-107">Remarks</span></span>
<span data-ttu-id="4c852-108">Der Typ des Bezeichners wird abgeleitet, von dem Typ des der *starten* und *Fertig stellen* Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="4c852-108">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="4c852-109">Typen, die für diese Ausdrücke müssen 32-Bit-Ganzzahlen sein.</span><span class="sxs-lookup"><span data-stu-id="4c852-109">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="4c852-110">Obwohl technisch gesehen ist ein Ausdruck, `for...to` ist eher wie eine herkömmliche Anweisung in einem imperativen Programmiersprache ab.</span><span class="sxs-lookup"><span data-stu-id="4c852-110">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="4c852-111">Der Rückgabetyp für die *Text-Ausdruck* muss `unit`.</span><span class="sxs-lookup"><span data-stu-id="4c852-111">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="4c852-112">Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der der `for...to` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4c852-112">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="4c852-113">Der obige Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="4c852-113">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="4c852-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c852-114">See Also</span></span>
[<span data-ttu-id="4c852-115">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4c852-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4c852-116">Schleifen: `for...in`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4c852-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="4c852-117">Schleifen: `while...do`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="4c852-117">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
