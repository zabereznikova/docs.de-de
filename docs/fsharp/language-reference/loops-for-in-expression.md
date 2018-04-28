---
title: 'Schleifen: for...in-Ausdruck (F#)'
description: Finden Sie unter wie die f#-for... in Ausdruck Schleifenkonstrukt wird verwendet, um die Übereinstimmungen eines Musters in einer aufzählbaren Auflistung zu durchlaufen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: eaf0f4fc6419d8e0bff46795120ee5e42c4efe1d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="loops-forin-expression"></a><span data-ttu-id="eccd8-103">Schleifen: for...in-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="eccd8-103">Loops: for...in Expression</span></span>

<span data-ttu-id="eccd8-104">Diese Schleifenkonstrukt wird verwendet, durchlaufen die Übereinstimmungen eines Musters in einer aufzählbaren Auflistung z. B. einer Range-Ausdruck, Sequenz, Liste, Array oder andere Konstrukt, das Enumeration unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="eccd8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eccd8-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="eccd8-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eccd8-106">Remarks</span></span>
<span data-ttu-id="eccd8-107">Die `for...in` Ausdruck verglichen werden kann, um die `for each` Anweisung in anderen .NET-Sprachen da er über die Werte in einer aufzählbaren Auflistung in einer Schleife verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eccd8-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="eccd8-108">Allerdings `for...in` unterstützt auch Mustervergleich über der Auflistung statt nur die Iteration der gesamten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="eccd8-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="eccd8-109">Der enumerable-Ausdruck kann angegeben werden, als aufzählbare Auflistung oder mithilfe der `..` -Operator, als Bereich für einen ganzzahligen Typ.</span><span class="sxs-lookup"><span data-stu-id="eccd8-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="eccd8-110">Aufzählbare Auflistungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen usw. an.</span><span class="sxs-lookup"><span data-stu-id="eccd8-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="eccd8-111">Jeder Typ, der implementiert `System.Collections.IEnumerable` kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eccd8-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="eccd8-112">Wenn Sie einen Bereich mithilfe von Ausdrücken die `..` -Operator, können Sie die folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="eccd8-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="eccd8-113">*Starten Sie* ...</span><span class="sxs-lookup"><span data-stu-id="eccd8-113">*start* ..</span></span> <span data-ttu-id="eccd8-114">*Fertig stellen*</span><span class="sxs-lookup"><span data-stu-id="eccd8-114">*finish*</span></span>

<span data-ttu-id="eccd8-115">Sie können auch eine Version, die ein Inkrement aufgerufen der *überspringen*, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="eccd8-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="eccd8-116">*Starten Sie* ...</span><span class="sxs-lookup"><span data-stu-id="eccd8-116">*start* ..</span></span> <span data-ttu-id="eccd8-117">*Überspringen Sie* ...</span><span class="sxs-lookup"><span data-stu-id="eccd8-117">*skip* ..</span></span> <span data-ttu-id="eccd8-118">*Fertig stellen*</span><span class="sxs-lookup"><span data-stu-id="eccd8-118">*finish*</span></span>

<span data-ttu-id="eccd8-119">Wenn Sie ganzzahlige Bereiche und eine einfache Zählervariable als Muster verwenden, ist das normale Verhalten sich die Zählervariable erhöhen, indem bei jeder Iteration 1, aber wenn der Bereich einen Skip-Wert enthält, wird erhöht, durch den Skip-Wert stattdessen.</span><span class="sxs-lookup"><span data-stu-id="eccd8-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="eccd8-120">Das Muster übereinstimmende Werte können auch im Body-Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eccd8-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="eccd8-121">Die folgenden Codebeispiele veranschaulichen die Verwendung der `for...in` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="eccd8-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="eccd8-122">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="eccd8-123">Im folgende Beispiel wird gezeigt, wie in einer Schleife auf eine Sequenz und wie Sie ein Tupelmuster statt einer einfachen Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eccd8-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="eccd8-124">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-124">The output is as follows.</span></span>

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

<span data-ttu-id="eccd8-125">Das folgende Beispiel zeigt, wie über eine einfache Integer-Bereich in einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="eccd8-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="eccd8-126">Die Ausgabe von function1 lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="eccd8-127">Das folgende Beispiel zeigt, wie in einer Schleife über einen Bereich mit einem Überspringen von 2, die jedes andere Element des Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="eccd8-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="eccd8-128">Die Ausgabe des `function2` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="eccd8-129">Im folgende Beispiel wird gezeigt, wie einen Zeichenbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eccd8-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="eccd8-130">Die Ausgabe des `function3` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="eccd8-131">Im folgende Beispiel wird gezeigt, wie einen negative Skip-Wert für eine umgekehrte Iteration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eccd8-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="eccd8-132">Die Ausgabe des `function4` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="eccd8-133">Der Anfang und das Ende des Bereichs können auch Ausdrücke, z. B. Funktionen, wie im folgenden Code sein.</span><span class="sxs-lookup"><span data-stu-id="eccd8-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="eccd8-134">Die Ausgabe des `function5` mit dieser Eingabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="eccd8-135">Das nächste Beispiel zeigt die Verwendung von Platzhalterzeichen (_), wenn das Element nicht in der Schleife erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="eccd8-135">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="eccd8-136">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="eccd8-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="eccd8-137">`Note` Können Sie `for...in` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `for...in` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eccd8-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="eccd8-138">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="eccd8-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="eccd8-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eccd8-139">See Also</span></span>
[<span data-ttu-id="eccd8-140">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="eccd8-140">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="eccd8-141">Schleifen: `for...to`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="eccd8-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="eccd8-142">Schleifen: `while...do`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="eccd8-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
