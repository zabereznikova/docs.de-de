---
title: Nicht strikte Ausdrücke
description: Erfahren Sie F# , wie verzögerte Ausdrücke die Leistung Ihrer Apps und Bibliotheken verbessern können.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630747"
---
# <a name="lazy-expressions"></a><span data-ttu-id="d960e-103">Nicht strikte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d960e-103">Lazy Expressions</span></span>

<span data-ttu-id="d960e-104">Verzögerte *Ausdrücke* sind Ausdrücke, die nicht sofort ausgewertet werden, sondern stattdessen ausgewertet werden, wenn das Ergebnis benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="d960e-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="d960e-105">Dies kann helfen, die Leistung Ihres Codes zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d960e-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="d960e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d960e-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="d960e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d960e-107">Remarks</span></span>

<span data-ttu-id="d960e-108">In der vorherigen Syntax handelt es sich bei *Expression* um Code, der nur ausgewertet wird, wenn ein Ergebnis erforderlich ist, und der Bezeichner ist ein Wert, der das Ergebnis speichert.</span><span class="sxs-lookup"><span data-stu-id="d960e-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="d960e-109">Der Wert ist vom Typ [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), wobei der tatsächliche Typ, der für `'T` verwendet wird, vom Ergebnis des Ausdrucks bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="d960e-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="d960e-110">Mithilfe von Lazy Expressions können Sie die Leistung verbessern, indem Sie die Ausführung von Ausdrücken auf die Situationen beschränken, in denen ein Ergebnis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d960e-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="d960e-111">Um die Ausführung der Ausdrücke zu erzwingen, wird die-Methode `Force`aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d960e-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="d960e-112">`Force`bewirkt, dass die Ausführung nur einmal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d960e-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="d960e-113">Nachfolgende Aufrufe `Force` von geben das gleiche Ergebnis zurück, führen jedoch keinen Code aus.</span><span class="sxs-lookup"><span data-stu-id="d960e-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="d960e-114">Der folgende Code veranschaulicht die Verwendung von Lazy Expressions und die Verwendung von `Force`.</span><span class="sxs-lookup"><span data-stu-id="d960e-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="d960e-115">`result` In diesem Code ist `Lazy<int>`der Typ von, und die `Force` -Methode gibt einen `int`zurück.</span><span class="sxs-lookup"><span data-stu-id="d960e-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="d960e-116">Die verzögerte Auswertung, aber nicht `Lazy` der-Typ, wird auch für Sequenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d960e-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="d960e-117">Weitere Informationen finden Sie unter [Sequenzen](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="d960e-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d960e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d960e-118">See also</span></span>

- [<span data-ttu-id="d960e-119">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d960e-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d960e-120">LazyExtensions-Modul</span><span class="sxs-lookup"><span data-stu-id="d960e-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
