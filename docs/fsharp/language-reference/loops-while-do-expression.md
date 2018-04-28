---
title: 'Schleifen: while...do-Ausdruck (F#)'
description: Finden Sie unter wie die while... führen Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung "true" ist.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 847f99faab42c8805bd788e42e3f24ad6369ba52
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="b57d5-103">Schleifen: while...do-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b57d5-103">Loops: while...do Expression</span></span>

<span data-ttu-id="b57d5-104">Die `while...do` Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="b57d5-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="b57d5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b57d5-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="b57d5-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b57d5-106">Remarks</span></span>
<span data-ttu-id="b57d5-107">Die *Testausdruck* ausgewertet wird, ist er `true`, *Text-Ausdruck* ausgeführt wird und der Testausdruck erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="b57d5-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="b57d5-108">Die *Text-Ausdruck* muss einen Typ aufweisen `unit`.</span><span class="sxs-lookup"><span data-stu-id="b57d5-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="b57d5-109">Wenn der Testausdruck ist `false`, die Iteration beendet.</span><span class="sxs-lookup"><span data-stu-id="b57d5-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="b57d5-110">Das folgende Beispiel veranschaulicht die Verwendung der `while...do` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b57d5-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="b57d5-111">Die Ausgabe des vorherigen Codes ist einen Stream von Zufallszahlen zwischen 1 und 20, der letzten, von denen 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="b57d5-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="b57d5-112">Können Sie `while...do` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `while...do` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b57d5-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="b57d5-113">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b57d5-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="b57d5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b57d5-114">See Also</span></span>
[<span data-ttu-id="b57d5-115">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b57d5-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b57d5-116">Schleifen: `for...in`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b57d5-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="b57d5-117">Schleifen: `for...to`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b57d5-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
