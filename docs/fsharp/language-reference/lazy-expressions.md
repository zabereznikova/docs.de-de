---
title: Nicht strikte Ausdrücke
description: 'Erfahren Sie, wie Sie mit F # Lazy Expressions die Leistung Ihrer Apps und Bibliotheken verbessern können.'
ms.date: 08/15/2020
ms.openlocfilehash: 71c466ca3b74c9e92b81a3c268e07438ec944905
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558087"
---
# <a name="lazy-expressions"></a><span data-ttu-id="b84f9-103">Nicht strikte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="b84f9-103">Lazy Expressions</span></span>

<span data-ttu-id="b84f9-104">Verzögerte *Ausdrücke* sind Ausdrücke, die nicht sofort ausgewertet werden, sondern stattdessen ausgewertet werden, wenn das Ergebnis benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="b84f9-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="b84f9-105">Dies kann helfen, die Leistung Ihres Codes zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b84f9-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="b84f9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b84f9-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="b84f9-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b84f9-107">Remarks</span></span>

<span data-ttu-id="b84f9-108">In der vorherigen Syntax handelt es sich bei *Expression* um Code, der nur ausgewertet wird, wenn ein Ergebnis erforderlich ist, und der *Bezeichner* ist ein Wert, der das Ergebnis speichert.</span><span class="sxs-lookup"><span data-stu-id="b84f9-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="b84f9-109">Der Wert ist vom Typ [`Lazy<'T>`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazy-1-0.html) , wobei der tatsächliche Typ, der für verwendet wird, `'T` vom Ergebnis des Ausdrucks bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="b84f9-109">The value is of type [`Lazy<'T>`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazy-1-0.html), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="b84f9-110">Mithilfe von Lazy Expressions können Sie die Leistung verbessern, indem Sie die Ausführung von Ausdrücken auf die Situationen beschränken, in denen ein Ergebnis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b84f9-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="b84f9-111">Um die Ausführung der Ausdrücke zu erzwingen, wird die-Methode aufgerufen `Force` .</span><span class="sxs-lookup"><span data-stu-id="b84f9-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="b84f9-112">`Force` bewirkt, dass die Ausführung nur einmal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b84f9-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="b84f9-113">Nachfolgende Aufrufe von `Force` geben das gleiche Ergebnis zurück, führen jedoch keinen Code aus.</span><span class="sxs-lookup"><span data-stu-id="b84f9-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="b84f9-114">Der folgende Code veranschaulicht die Verwendung von Lazy Expressions und die Verwendung von `Force` .</span><span class="sxs-lookup"><span data-stu-id="b84f9-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="b84f9-115">In diesem Code ist der Typ von `result` `Lazy<int>` , und die- `Force` Methode gibt einen zurück `int` .</span><span class="sxs-lookup"><span data-stu-id="b84f9-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="b84f9-116">Die verzögerte Auswertung, aber nicht der- `Lazy` Typ, wird auch für Sequenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b84f9-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="b84f9-117">Weitere Informationen finden Sie unter [Sequenzen](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="b84f9-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b84f9-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b84f9-118">See also</span></span>

- [<span data-ttu-id="b84f9-119">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b84f9-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b84f9-120">LazyExtensions-Modul</span><span class="sxs-lookup"><span data-stu-id="b84f9-120">LazyExtensions module</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazyextensions.html)
