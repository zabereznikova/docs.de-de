---
title: 'Schleifen: while...do-Ausdruck'
description: Finden Sie unter wie beim... führen Ausdruck wird verwendet, um iterative Ausführung (Schleifen) auszuführen, während eine bestimmte testbedingung erfüllt ist.
ms.date: 05/16/2016
ms.openlocfilehash: d2a77e0bfefe3b6b026012e6b2938ba670326bcf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904019"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="141b2-103">Schleifen: while...do-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="141b2-103">Loops: while...do Expression</span></span>

<span data-ttu-id="141b2-104">Die `while...do` Ausdruck wird verwendet, um iterative Ausführung (Schleifen) auszuführen, während eine bestimmte testbedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="141b2-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="141b2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="141b2-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="141b2-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="141b2-106">Remarks</span></span>

<span data-ttu-id="141b2-107">Die *Testausdruck* ausgewertet wird, ist dies `true`, *Body-Ausdruck* ausgeführt wird und der Testausdruck erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="141b2-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="141b2-108">Die *Body-Ausdruck* muss einen Typ aufweisen `unit`.</span><span class="sxs-lookup"><span data-stu-id="141b2-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="141b2-109">Wenn der Testausdruck ist `false`, die Iteration beendet.</span><span class="sxs-lookup"><span data-stu-id="141b2-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="141b2-110">Das folgende Beispiel veranschaulicht die Verwendung der `while...do` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="141b2-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="141b2-111">Die Ausgabe des obigen Codes ist es sich um einen Stream von Zufallszahlen zwischen 1 und 20, die, der letzten der 10 ist.</span><span class="sxs-lookup"><span data-stu-id="141b2-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="141b2-112">Können Sie `while...do` in Sequenzausdrücken und anderen Berechnungsausdrücken in diesem Fall, dass eine angepasste Version von der `while...do` Ausdruck wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="141b2-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="141b2-113">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="141b2-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="141b2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="141b2-114">See also</span></span>

- [<span data-ttu-id="141b2-115">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="141b2-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="141b2-116">Schleifen: `for...in` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="141b2-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="141b2-117">Schleifen: `for...to` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="141b2-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)