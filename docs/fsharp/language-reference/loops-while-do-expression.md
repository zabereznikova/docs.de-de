---
title: 'Schleifen: while...do-Ausdruck (F#)'
description: Finden Sie unter wie die while... führen Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung "true" ist.
ms.date: 05/16/2016
ms.openlocfilehash: e3198246e44bbb11b226f04da6795f3da22626e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562231"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="8527d-103">Schleifen: while...do-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8527d-103">Loops: while...do Expression</span></span>

<span data-ttu-id="8527d-104">Die `while...do` Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="8527d-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="8527d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8527d-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="8527d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8527d-106">Remarks</span></span>
<span data-ttu-id="8527d-107">Die *Testausdruck* ausgewertet wird, ist er `true`, *Text-Ausdruck* ausgeführt wird und der Testausdruck erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="8527d-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="8527d-108">Die *Text-Ausdruck* muss einen Typ aufweisen `unit`.</span><span class="sxs-lookup"><span data-stu-id="8527d-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="8527d-109">Wenn der Testausdruck ist `false`, die Iteration beendet.</span><span class="sxs-lookup"><span data-stu-id="8527d-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="8527d-110">Das folgende Beispiel veranschaulicht die Verwendung der `while...do` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8527d-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="8527d-111">Die Ausgabe des vorherigen Codes ist einen Stream von Zufallszahlen zwischen 1 und 20, der letzten, von denen 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="8527d-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="8527d-112">Können Sie `while...do` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `while...do` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8527d-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="8527d-113">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8527d-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8527d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8527d-114">See Also</span></span>
[<span data-ttu-id="8527d-115">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="8527d-115">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="8527d-116">Schleifen: `for...in`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8527d-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="8527d-117">Schleifen: `for...to`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="8527d-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
