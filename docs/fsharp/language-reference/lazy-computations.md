---
title: "Verzögerte Berechnungen (F#)"
description: "Erfahren Sie, wie die Leistung Ihrer apps und Bibliotheken von f# verzögerte Berechnungen verbessert werden können."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a><span data-ttu-id="4e502-104">Verzögerte Berechnungen</span><span class="sxs-lookup"><span data-stu-id="4e502-104">Lazy Computations</span></span>

<span data-ttu-id="4e502-105">*Verzögerte Berechnungen* sind Berechnungen, die nicht sofort ausgewertet werden, sondern werden stattdessen ausgewertet, wenn das Ergebnis benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="4e502-105">*Lazy computations* are computations that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="4e502-106">Dadurch können um die Leistung des Codes zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4e502-106">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e502-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e502-107">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="4e502-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e502-108">Remarks</span></span>

<span data-ttu-id="4e502-109">In der vorherigen Syntax *Ausdruck* ist Code, der ausgewertet wird, nur, wenn ein Ergebnis erforderlich ist und *Bezeichner* ist ein Wert, der das Ergebnis speichert.</span><span class="sxs-lookup"><span data-stu-id="4e502-109">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="4e502-110">Der Wert ist vom Typ [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in dem die tatsächlichen eingeben, die verwendet wird, für `'T` wird über das Ergebnis des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="4e502-110">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="4e502-111">Verzögerte Berechnungen ermöglichen es Ihnen, Verbessern der Leistung durch Einschränken der Ausführung einer Berechnung auf nur die Fälle, in denen ein Ergebnis benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="4e502-111">Lazy computations enable you to improve performance by restricting the execution of a computation to only those situations in which a result is needed.</span></span>

<span data-ttu-id="4e502-112">Um die Berechnung ausgeführt werden zu erzwingen, rufen Sie die Methode `Force`.</span><span class="sxs-lookup"><span data-stu-id="4e502-112">To force the computation to be performed, you call the method `Force`.</span></span> <span data-ttu-id="4e502-113">`Force`bewirkt, dass die Ausführung nur einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e502-113">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="4e502-114">Nachfolgende Aufrufe `Force` zurückgeben identisch zu, wobei jedoch keinen Code nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e502-114">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="4e502-115">Der folgende Code veranschaulicht die Verwendung der verzögerten Berechnung und die Verwendung von `Force`.</span><span class="sxs-lookup"><span data-stu-id="4e502-115">The following code illustrates the use of lazy computation and the use of `Force`.</span></span> <span data-ttu-id="4e502-116">In diesem Code wird der Typ des `result` ist `Lazy<int>`, und die `Force` Methode gibt ein `int`.</span><span class="sxs-lookup"><span data-stu-id="4e502-116">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="4e502-117">Verzögerte Auswertung jedoch nicht die `Lazy` eingeben, wird auch für Sequenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e502-117">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="4e502-118">Weitere Informationen finden Sie unter [Sequenzen](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="4e502-118">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e502-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e502-119">See Also</span></span>

[<span data-ttu-id="4e502-120">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="4e502-120">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="4e502-121">LazyExtensions-Modul</span><span class="sxs-lookup"><span data-stu-id="4e502-121">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
