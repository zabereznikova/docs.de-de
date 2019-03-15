---
title: Lazy-Ausdrücke
description: Erfahren Sie, wie F# lazy Ausdrücken können die Leistung Ihrer apps und Bibliotheken verbessern.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57853324"
---
# <a name="lazy-expressions"></a><span data-ttu-id="23dd2-103">Lazy-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="23dd2-103">Lazy Expressions</span></span>

<span data-ttu-id="23dd2-104">*Verzögerte Ausdrücke* sind Ausdrücke, die nicht sofort ausgewertet, aber stattdessen ausgewertet, wenn das Ergebnis benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="23dd2-104">*Lazy expressions* are expressions that are not evaluated immediately, but are instead evaluated when the result is needed.</span></span> <span data-ttu-id="23dd2-105">Dies kann helfen, um die Leistung Ihres Codes zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="23dd2-105">This can help to improve the performance of your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="23dd2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="23dd2-106">Syntax</span></span>

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a><span data-ttu-id="23dd2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23dd2-107">Remarks</span></span>

<span data-ttu-id="23dd2-108">In der vorherigen Syntax *Ausdruck* ist Code, der ausgewertet wird, nur, wenn das Ergebnis erforderlich ist, und *Bezeichner* ist ein Wert, der das Ergebnis speichert.</span><span class="sxs-lookup"><span data-stu-id="23dd2-108">In the previous syntax, *expression* is code that is evaluated only when a result is required, and *identifier* is a value that stores the result.</span></span> <span data-ttu-id="23dd2-109">Der Wert ist vom Typ [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), in dem Typ, der tatsächlich dient zur `'T` wird aus dem Ergebnis des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="23dd2-109">The value is of type [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), where the actual type that is used for `'T` is determined from the result of the expression.</span></span>

<span data-ttu-id="23dd2-110">Verzögerte Ausdrücken können Sie zur Verbesserung der Leistung durch Einschränken der Ausführung von einem Ausdrücke, die nur den Situationen, in dem ein Ergebnis benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="23dd2-110">Lazy expressions enable you to improve performance by restricting the execution of an expressions to only those situations in which a result is needed.</span></span>

<span data-ttu-id="23dd2-111">Um die Ausdrücke, die ausgeführt werden zu erzwingen, rufen Sie die Methode `Force`.</span><span class="sxs-lookup"><span data-stu-id="23dd2-111">To force the expressions to be performed, you call the method `Force`.</span></span> <span data-ttu-id="23dd2-112">`Force` bewirkt, dass die Ausführung nur einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23dd2-112">`Force` causes the execution to be performed only one time.</span></span> <span data-ttu-id="23dd2-113">Nachfolgende Aufrufe von `Force` zurückgegeben werden, dieselben dazu führen, jedoch keinen Code nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23dd2-113">Subsequent calls to `Force` return the same result, but do not execute any code.</span></span>

<span data-ttu-id="23dd2-114">Der folgende Code veranschaulicht die Verwendung von verzögerten Ausdrücken und die Verwendung von `Force`.</span><span class="sxs-lookup"><span data-stu-id="23dd2-114">The following code illustrates the use of lazy expressions and the use of `Force`.</span></span> <span data-ttu-id="23dd2-115">In diesem Code wird der Typ des `result` ist `Lazy<int>`, und die `Force` Methode gibt ein `int`.</span><span class="sxs-lookup"><span data-stu-id="23dd2-115">In this code, the type of `result` is `Lazy<int>`, and the `Force` method returns an `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

<span data-ttu-id="23dd2-116">Verzögerte Auswertung, aber nicht die `Lazy` eingeben, wird auch für Sequenzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="23dd2-116">Lazy evaluation, but not the `Lazy` type, is also used for sequences.</span></span> <span data-ttu-id="23dd2-117">Weitere Informationen finden Sie unter [Sequenzen](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="23dd2-117">For more information, see [Sequences](sequences.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="23dd2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23dd2-118">See also</span></span>

- [<span data-ttu-id="23dd2-119">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="23dd2-119">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="23dd2-120">LazyExtensions-Modul</span><span class="sxs-lookup"><span data-stu-id="23dd2-120">LazyExtensions module</span></span>](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
