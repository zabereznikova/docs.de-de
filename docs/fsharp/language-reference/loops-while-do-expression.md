---
title: 'Schleifen: while...do-Ausdruck'
description: Sehen Sie sich an, wie der while-... "Do Expression" wird verwendet, um iterative Ausführung (Schleifen) auszuführen, während eine angegebene Test Bedingung "true" ist.
ms.date: 05/16/2016
ms.openlocfilehash: 73526279358db101f8d07721a200920f1e87f119
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216632"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="e8b24-103">Schleifen: while...do-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="e8b24-103">Loops: while...do Expression</span></span>

<span data-ttu-id="e8b24-104">Der `while...do` Ausdruck wird verwendet, um iterative Ausführung (Schleifen) auszuführen, während eine angegebene Test Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="e8b24-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8b24-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8b24-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="e8b24-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8b24-106">Remarks</span></span>

<span data-ttu-id="e8b24-107">Der *Test Ausdruck* wird ausgewertet. Wenn dies der `true`Fall ist, wird der *Text Ausdruck* ausgeführt, und der Test Ausdruck wird erneut ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e8b24-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="e8b24-108">Der *Text Ausdruck* muss den Typ `unit`aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e8b24-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="e8b24-109">Wenn der Test Ausdruck ist `false`, wird die Iterationen beendet.</span><span class="sxs-lookup"><span data-stu-id="e8b24-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="e8b24-110">Das folgende Beispiel veranschaulicht die Verwendung des `while...do` -Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="e8b24-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="e8b24-111">Die Ausgabe des vorherigen Codes ist ein Stream von Zufallszahlen zwischen 1 und 20, der letzte Wert ist 10.</span><span class="sxs-lookup"><span data-stu-id="e8b24-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```console
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="e8b24-112">Sie können in `while...do` Sequenz Ausdrücken und anderen Berechnungs Ausdrücken verwenden. in diesem Fall wird eine angepasste Version `while...do` des Ausdrucks verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8b24-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="e8b24-113">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Berechnungs Ausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e8b24-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8b24-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8b24-114">See also</span></span>

- [<span data-ttu-id="e8b24-115">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="e8b24-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e8b24-116">Loops `for...in`Begriff</span><span class="sxs-lookup"><span data-stu-id="e8b24-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="e8b24-117">Loops `for...to`Begriff</span><span class="sxs-lookup"><span data-stu-id="e8b24-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
