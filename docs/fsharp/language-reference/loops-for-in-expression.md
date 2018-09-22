---
title: 'Schleifen: for...in-Ausdruck (F#)'
description: Finden Sie unter wie der F#-for... in Ausdruck Schleifenkonstrukt zum Durchlaufen der Übereinstimmungen eines Musters in einer aufzählbaren Auflistung verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: c4fba1f1dea3993cafa2e37ad0f32d9fb2eed85a
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576810"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="75bf4-103">Schleifen: for...in-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="75bf4-103">Loops: for...in Expression</span></span>

<span data-ttu-id="75bf4-104">Diese Schleifenkonstrukt wird zum Durchlaufen der Übereinstimmungen eines Musters in einer aufzählbaren Auflistung wie z. B. einen Bereichsausdruck, Sequenz, Liste, Array oder anderes Konstrukt, das Enumerationen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="75bf4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="75bf4-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="75bf4-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75bf4-106">Remarks</span></span>

<span data-ttu-id="75bf4-107">Die `for...in` Ausdruck verglichen werden kann, um die `for each` Anweisung in anderen .NET-Sprachen da er in einer Schleife auf die Werte in einer aufzählbaren Auflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75bf4-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="75bf4-108">Allerdings `for...in` unterstützt auch Musterabgleich, die über die Sammlung nicht nur die Iteration über die gesamte Auflistung.</span><span class="sxs-lookup"><span data-stu-id="75bf4-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="75bf4-109">Der enumerable-Ausdruck kann angegeben werden, als aufzählbare Auflistung oder mithilfe der `..` -Operator, wie ein Bereich auf einen ganzzahligen Typ.</span><span class="sxs-lookup"><span data-stu-id="75bf4-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="75bf4-110">Aufzählbare Sammlungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen und So weiter.</span><span class="sxs-lookup"><span data-stu-id="75bf4-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="75bf4-111">Jeder Typ, der implementiert `System.Collections.IEnumerable` kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75bf4-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="75bf4-112">Wenn Sie einen Bereich mithilfe von Ausdrücken die `..` -Operator, können Sie die folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bf4-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="75bf4-113">*Starten Sie* ...</span><span class="sxs-lookup"><span data-stu-id="75bf4-113">*start* ..</span></span> <span data-ttu-id="75bf4-114">*Fertig stellen*</span><span class="sxs-lookup"><span data-stu-id="75bf4-114">*finish*</span></span>

<span data-ttu-id="75bf4-115">Können Sie auch eine Version, ein Inkrement wird aufgerufen, beinhaltet, die *überspringen*, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="75bf4-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="75bf4-116">*Starten Sie* ...</span><span class="sxs-lookup"><span data-stu-id="75bf4-116">*start* ..</span></span> <span data-ttu-id="75bf4-117">*Überspringen Sie* ...</span><span class="sxs-lookup"><span data-stu-id="75bf4-117">*skip* ..</span></span> <span data-ttu-id="75bf4-118">*Fertig stellen*</span><span class="sxs-lookup"><span data-stu-id="75bf4-118">*finish*</span></span>

<span data-ttu-id="75bf4-119">Wenn Sie ganzzahlige Bereiche und eine einfache Counter-Variable als Muster verwenden, in der Regel werden die Zählervariable um 1 bei jeder Iteration zu erhöhen, aber wenn der Bereich einen Skip-Wert enthält, wird erhöht, durch den Skip-Wert stattdessen.</span><span class="sxs-lookup"><span data-stu-id="75bf4-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="75bf4-120">Werte, die im Muster übereinstimmen, können auch im Body-Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75bf4-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="75bf4-121">Die folgenden Codebeispiele veranschaulichen die Verwendung der `for...in` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="75bf4-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="75bf4-122">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="75bf4-123">Das folgende Beispiel zeigt, wie in einer Sequenz eine Schleife durchlaufen, und wie Sie ein Tupelmuster anstelle einer einfachen Variable verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bf4-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="75bf4-124">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-124">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="75bf4-125">Das folgende Beispiel zeigt, wie Sie eine Schleife über einen einfachen ganzzahligen Bereich durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="75bf4-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="75bf4-126">Die Ausgabe von function1 lautet wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="75bf4-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="75bf4-127">Das folgende Beispiel zeigt, wie in einer Schleife über einen Bereich mit einem Skip 2, die jedes andere Element des Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="75bf4-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="75bf4-128">Die Ausgabe des `function2` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="75bf4-129">Das folgende Beispiel zeigt, wie Sie mit einem Bereich von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="75bf4-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="75bf4-130">Die Ausgabe des `function3` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="75bf4-131">Das folgende Beispiel zeigt, wie Sie einen negativen Skip-Wert für eine umgekehrte Iteration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="75bf4-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="75bf4-132">Die Ausgabe des `function4` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="75bf4-133">Der Anfang und das Ende des Bereichs können auch Ausdrücke, wie z. B. Funktionen, wie im folgenden Code sein.</span><span class="sxs-lookup"><span data-stu-id="75bf4-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="75bf4-134">Die Ausgabe des `function5` mit dieser Eingabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="75bf4-135">Das nächste Beispiel zeigt die Verwendung eines Platzhalterzeichens (\_) Wenn das Element nicht in der Schleife erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="75bf4-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="75bf4-136">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="75bf4-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="75bf4-137">`Note` Können Sie `for...in` in Sequenzausdrücken und anderen Berechnungsausdrücken in diesem Fall, dass eine angepasste Version von der `for...in` Ausdruck wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="75bf4-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="75bf4-138">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="75bf4-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75bf4-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75bf4-139">See also</span></span>

- [<span data-ttu-id="75bf4-140">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="75bf4-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="75bf4-141">Schleifen: `for...to`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="75bf4-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="75bf4-142">Schleifen: `while...do`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="75bf4-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
