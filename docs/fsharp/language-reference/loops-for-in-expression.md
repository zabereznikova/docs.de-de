---
title: 'Schleifen: for...in-Ausdruck'
description: Siehe How F# for... im Ausdrucks Schleifen Konstrukt wird verwendet, um die Übereinstimmungen eines Musters in einer Aufzähl baren Auflistung zu durchlaufen.
ms.date: 05/16/2016
ms.openlocfilehash: 640b0f91f6c641f3b49a99dc67abe7e4c31911ea
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630714"
---
# <a name="loops-forin-expression"></a><span data-ttu-id="c365c-103">Schleifen: for...in-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="c365c-103">Loops: for...in Expression</span></span>

<span data-ttu-id="c365c-104">Dieses Schleifen Konstrukt wird zum Durchlaufen der Übereinstimmungen eines Musters in einer Aufzähl baren Auflistung verwendet, wie z. b. ein Bereichs Ausdruck, eine Sequenz, eine Liste, ein Array oder ein anderes Konstrukt, das die Enumeration unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c365c-104">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>

## <a name="syntax"></a><span data-ttu-id="c365c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c365c-105">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="c365c-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c365c-106">Remarks</span></span>

<span data-ttu-id="c365c-107">Der `for...in` Ausdruck kann mit der `for each` -Anweisung in anderen .NET-Sprachen verglichen werden, da er verwendet wird, um die Werte in einer Aufzähl baren Auflistung zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="c365c-107">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="c365c-108">Unterstützt jedoch auch Muster Übereinstimmungen über die Auflistung anstelle von Iterationen über die gesamte Auflistung. `for...in`</span><span class="sxs-lookup"><span data-stu-id="c365c-108">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="c365c-109">Der Aufzähl Bare-Ausdruck kann als eine Aufzähl Bare Auflistung oder, mithilfe des `..` -Operators, als Bereich für einen ganzzahligen Typ angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c365c-109">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="c365c-110">Aufzähl Bare Auflistungen enthalten Listen, Sequenzen, Arrays, Sätze, Zuordnungen usw.</span><span class="sxs-lookup"><span data-stu-id="c365c-110">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="c365c-111">Jeder Typ, der `System.Collections.IEnumerable` implementiert, kann verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c365c-111">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="c365c-112">Wenn Sie einen Bereich mithilfe des `..` -Operators Ausdrücken, können Sie die folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="c365c-112">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="c365c-113">*starten* .</span><span class="sxs-lookup"><span data-stu-id="c365c-113">*start* ..</span></span> <span data-ttu-id="c365c-114">*ins*</span><span class="sxs-lookup"><span data-stu-id="c365c-114">*finish*</span></span>

<span data-ttu-id="c365c-115">Sie können auch eine Version verwenden, die ein Inkrement namens *Skip*enthält, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c365c-115">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="c365c-116">*starten* .</span><span class="sxs-lookup"><span data-stu-id="c365c-116">*start* ..</span></span> <span data-ttu-id="c365c-117">über *springen* ..</span><span class="sxs-lookup"><span data-stu-id="c365c-117">*skip* ..</span></span> <span data-ttu-id="c365c-118">*ins*</span><span class="sxs-lookup"><span data-stu-id="c365c-118">*finish*</span></span>

<span data-ttu-id="c365c-119">Wenn Sie ganzzahlige Bereiche und eine einfache Counter-Variable als Muster verwenden, besteht das typische Verhalten darin, die Counter-Variable bei jeder Iterationen um 1 zu erhöhen. wenn der Bereich jedoch einen Skip-Wert enthält, wird der Leistungswert stattdessen durch den Skip-Wert erhöht.</span><span class="sxs-lookup"><span data-stu-id="c365c-119">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="c365c-120">Werte, die mit dem Muster übereinstimmen, können auch im Text Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c365c-120">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="c365c-121">Die folgenden Codebeispiele veranschaulichen die Verwendung des `for...in` -Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="c365c-121">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="c365c-122">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-122">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="c365c-123">Im folgenden Beispiel wird gezeigt, wie eine Schleife über eine Sequenz ausgeführt wird und wie ein tupelmuster anstelle einer einfachen Variablen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c365c-123">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="c365c-124">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-124">The output is as follows.</span></span>

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

<span data-ttu-id="c365c-125">Im folgenden Beispiel wird gezeigt, wie ein einfacher ganzzahliger Bereich durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="c365c-125">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="c365c-126">Die Ausgabe von Funktion1 lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-126">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="c365c-127">Im folgenden Beispiel wird gezeigt, wie ein Bereich mit einem Skip von 2 durchlaufen wird, der jedes andere Element des Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="c365c-127">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="c365c-128">Die Ausgabe von `function2` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-128">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="c365c-129">Im folgenden Beispiel wird gezeigt, wie ein Zeichenbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c365c-129">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="c365c-130">Die Ausgabe von `function3` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-130">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="c365c-131">Im folgenden Beispiel wird gezeigt, wie ein negativer Skip-Wert für eine umgekehrte Iterationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c365c-131">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="c365c-132">Die Ausgabe von `function4` lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-132">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="c365c-133">Der Anfang und das Ende des Bereichs können auch Ausdrücke sein, z. b. Funktionen, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="c365c-133">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="c365c-134">Die Ausgabe von `function5` mit dieser Eingabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-134">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="c365c-135">Das nächste Beispiel zeigt die Verwendung eines Platzhalter Zeichens (\_), wenn das Element in der Schleife nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c365c-135">The next example shows the use of a wildcard character (\_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="c365c-136">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c365c-136">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="c365c-137">`Note`Sie können in `for...in` Sequenz Ausdrücken und anderen Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `for...in` des Ausdrucks verwendet.</span><span class="sxs-lookup"><span data-stu-id="c365c-137">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="c365c-138">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Berechnungs Ausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c365c-138">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c365c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c365c-139">See also</span></span>

- [<span data-ttu-id="c365c-140">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c365c-140">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c365c-141">Loops `for...to`Begriff</span><span class="sxs-lookup"><span data-stu-id="c365c-141">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
- [<span data-ttu-id="c365c-142">Loops `while...do`Begriff</span><span class="sxs-lookup"><span data-stu-id="c365c-142">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
