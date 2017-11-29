---
title: 'Schleifen: for...in-Ausdruck (F#)'
description: "Finden Sie unter wie die f#-for... in Ausdruck Schleifenkonstrukt wird verwendet, um die Übereinstimmungen eines Musters in einer aufzählbaren Auflistung zu durchlaufen."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f54e3228-4aec-4d0a-ae37-bc3376508284
ms.openlocfilehash: d86aeb3bdd975261e59004d636354a740bd95c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forin-expression"></a><span data-ttu-id="96c6e-104">Schleifen: for...in-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="96c6e-104">Loops: for...in Expression</span></span>

<span data-ttu-id="96c6e-105">Diese Schleifenkonstrukt wird verwendet, durchlaufen die Übereinstimmungen eines Musters in einer aufzählbaren Auflistung z. B. einer Range-Ausdruck, Sequenz, Liste, Array oder andere Konstrukt, das Enumeration unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-105">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="96c6e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="96c6e-106">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="96c6e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96c6e-107">Remarks</span></span>
<span data-ttu-id="96c6e-108">Die `for...in` Ausdruck verglichen werden kann, um die `for each` Anweisung in anderen .NET-Sprachen da er über die Werte in einer aufzählbaren Auflistung in einer Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96c6e-108">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="96c6e-109">Allerdings `for...in` unterstützt auch Mustervergleich über der Auflistung statt nur die Iteration der gesamten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="96c6e-109">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="96c6e-110">Der enumerable-Ausdruck kann angegeben werden, als aufzählbare Auflistung oder mithilfe der `..` -Operator, als Bereich für einen ganzzahligen Typ.</span><span class="sxs-lookup"><span data-stu-id="96c6e-110">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="96c6e-111">Aufzählbare Auflistungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen usw. an.</span><span class="sxs-lookup"><span data-stu-id="96c6e-111">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="96c6e-112">Jeder Typ, der implementiert `System.Collections.IEnumerable` kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96c6e-112">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="96c6e-113">Wenn Sie einen Bereich mithilfe von Ausdrücken die `..` -Operator, können Sie die folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="96c6e-113">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="96c6e-114">*Starten Sie* ...</span><span class="sxs-lookup"><span data-stu-id="96c6e-114">*start* ..</span></span> <span data-ttu-id="96c6e-115">*Fertig stellen*</span><span class="sxs-lookup"><span data-stu-id="96c6e-115">*finish*</span></span>

<span data-ttu-id="96c6e-116">Sie können auch eine Version, die ein Inkrement aufgerufen der *überspringen*, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="96c6e-116">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="96c6e-117">*Starten Sie* ...</span><span class="sxs-lookup"><span data-stu-id="96c6e-117">*start* ..</span></span> <span data-ttu-id="96c6e-118">*Überspringen Sie* ...</span><span class="sxs-lookup"><span data-stu-id="96c6e-118">*skip* ..</span></span> <span data-ttu-id="96c6e-119">*Fertig stellen*</span><span class="sxs-lookup"><span data-stu-id="96c6e-119">*finish*</span></span>

<span data-ttu-id="96c6e-120">Wenn Sie ganzzahlige Bereiche und eine einfache Zählervariable als Muster verwenden, ist das normale Verhalten sich die Zählervariable erhöhen, indem bei jeder Iteration 1, aber wenn der Bereich einen Skip-Wert enthält, wird erhöht, durch den Skip-Wert stattdessen.</span><span class="sxs-lookup"><span data-stu-id="96c6e-120">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="96c6e-121">Das Muster übereinstimmende Werte können auch im Body-Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96c6e-121">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="96c6e-122">Die folgenden Codebeispiele veranschaulichen die Verwendung der `for...in` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="96c6e-122">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="96c6e-123">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-123">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="96c6e-124">Im folgende Beispiel wird gezeigt, wie in einer Schleife auf eine Sequenz und wie Sie ein Tupelmuster statt einer einfachen Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="96c6e-124">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="96c6e-125">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-125">The output is as follows.</span></span>

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

<span data-ttu-id="96c6e-126">Das folgende Beispiel zeigt, wie über eine einfache Integer-Bereich in einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="96c6e-126">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="96c6e-127">Die Ausgabe von function1 lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-127">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="96c6e-128">Das folgende Beispiel zeigt, wie in einer Schleife über einen Bereich mit einem Überspringen von 2, die jedes andere Element des Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="96c6e-128">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="96c6e-129">Die Ausgabe des `function2` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-129">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="96c6e-130">Im folgende Beispiel wird gezeigt, wie einen Zeichenbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96c6e-130">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="96c6e-131">Die Ausgabe des `function3` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-131">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="96c6e-132">Im folgende Beispiel wird gezeigt, wie einen negative Skip-Wert für eine umgekehrte Iteration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96c6e-132">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="96c6e-133">Die Ausgabe des `function4` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-133">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="96c6e-134">Der Anfang und das Ende des Bereichs können auch Ausdrücke, z. B. Funktionen, wie im folgenden Code sein.</span><span class="sxs-lookup"><span data-stu-id="96c6e-134">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="96c6e-135">Die Ausgabe des `function5` mit dieser Eingabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-135">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="96c6e-136">Das nächste Beispiel zeigt die Verwendung von Platzhalterzeichen (_), wenn das Element nicht in der Schleife erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="96c6e-136">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="96c6e-137">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96c6e-137">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="96c6e-138">`Note`Können Sie `for...in` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `for...in` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96c6e-138">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="96c6e-139">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="96c6e-139">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="96c6e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96c6e-140">See Also</span></span>
[<span data-ttu-id="96c6e-141">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="96c6e-141">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="96c6e-142">Schleifen: `for...to`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="96c6e-142">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="96c6e-143">Schleifen: `while...do`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="96c6e-143">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
