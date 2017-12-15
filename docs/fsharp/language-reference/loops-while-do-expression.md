---
title: 'Schleifen: while...do-Ausdruck (F#)'
description: "Finden Sie unter wie die while... führen Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung \"true\" ist."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 5f10fda84a5e748856eb7b2c63ad46cc1fba44bb
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2017
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="abd74-104">Schleifen: while...do-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="abd74-104">Loops: while...do Expression</span></span>

<span data-ttu-id="abd74-105">Die `while...do` Ausdruck wird verwendet, um den iterativen Ausführung (Schleife) ausführen, wenn eine angegebene testbedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="abd74-105">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>


## <a name="syntax"></a><span data-ttu-id="abd74-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="abd74-106">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="abd74-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abd74-107">Remarks</span></span>
<span data-ttu-id="abd74-108">Die *Testausdruck* ausgewertet wird, ist er `true`, *Text-Ausdruck* ausgeführt wird und der Testausdruck erneut ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="abd74-108">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="abd74-109">Die *Text-Ausdruck* muss einen Typ aufweisen `unit`.</span><span class="sxs-lookup"><span data-stu-id="abd74-109">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="abd74-110">Wenn der Testausdruck ist `false`, die Iteration beendet.</span><span class="sxs-lookup"><span data-stu-id="abd74-110">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="abd74-111">Das folgende Beispiel veranschaulicht die Verwendung der `while...do` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="abd74-111">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="abd74-112">Die Ausgabe des vorherigen Codes ist einen Stream von Zufallszahlen zwischen 1 und 20, der letzten, von denen 10 verwendet.</span><span class="sxs-lookup"><span data-stu-id="abd74-112">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
<span data-ttu-id="abd74-113">Können Sie `while...do` in Sequenzausdrücken und andere Berechnungsausdrücke in diesem Fall, dass eine angepasste Version von den `while...do` Ausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="abd74-113">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="abd74-114">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Berechnungsausdrücke](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="abd74-114">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="abd74-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abd74-115">See Also</span></span>
[<span data-ttu-id="abd74-116">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="abd74-116">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="abd74-117">Schleifen: `for...in`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="abd74-117">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)

[<span data-ttu-id="abd74-118">Schleifen: `for...to`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="abd74-118">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
