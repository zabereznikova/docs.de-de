---
title: Continue-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="fa921-102">Continue-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa921-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="fa921-103">Überträgt die Steuerung sofort an die nächste Iteration einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="fa921-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa921-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa921-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa921-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa921-105">Remarks</span></span>  
 <span data-ttu-id="fa921-106">Sie können aus übertragen innerhalb einer `Do`, `For`, oder `While` -Schleife zur nächsten Iteration der Schleife.</span><span class="sxs-lookup"><span data-stu-id="fa921-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="fa921-107">Wird sofort mit dem Test der Schleife-Bedingung, das Äquivalent zum Übertragen von in ist die Steuerung der `For` oder `While` -Anweisung oder der `Do` oder `Loop` -Anweisung, enthält die `Until` oder `While` Klausel.</span><span class="sxs-lookup"><span data-stu-id="fa921-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="fa921-108">Sie können `Continue` an einer beliebigen Stelle in der Schleife, die Übertragung zulässt.</span><span class="sxs-lookup"><span data-stu-id="fa921-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="fa921-109">Die Übertragung der Steuerung ermöglicht Regeln sind identisch mit der [GoTo-Anweisung](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fa921-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="fa921-110">Beispielsweise eine Schleife vollständig in Ihr enthalten ist eine `Try` Block, eine `Catch` Block oder ein `Finally` blockieren, können Sie `Continue` aus der Schleife zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="fa921-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="fa921-111">Wenn sich hingegen der `Try`... `End Try` Struktur innerhalb der Schleife enthalten ist, können keine `Continue` zum Übertragen der Steuerung aus der `Finally` Block, und Sie können es zum Übertragen von einer `Try` oder `Catch` blockiert werden, nur, wenn Sie vollständig übertragen der `Try`... `End Try` Struktur.</span><span class="sxs-lookup"><span data-stu-id="fa921-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="fa921-112">Wenn Sie geschachtelte Schleifen desselben Typs, z. B. verfügen eine `Do` Schleife innerhalb einer anderen `Do` Schleife, eine `Continue Do` Anweisung springt zur nächsten Iteration der innersten `Do` Schleife, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="fa921-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="fa921-113">Sie können keine `Continue` an die nächste Iteration einer Schleife enthaltenden desselben Typs zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="fa921-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="fa921-114">Wenn Sie z. B. geschachtelte Schleifen verschiedener Typen haben eine `Do` innerhalb einer Schleife eine `For` Schleife, können Sie an die nächste Iteration einer Schleife überspringen, indem Sie entweder `Continue Do` oder `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="fa921-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa921-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa921-115">Example</span></span>  
 <span data-ttu-id="fa921-116">Im folgenden Codebeispiel wird mit der `Continue While` Anweisung zur nächsten Spalte eines Arrays zu überspringen, wenn eine Division durch 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="fa921-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="fa921-117">Die `Continue While` befindet sich innerhalb einer `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="fa921-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="fa921-118">Er überträgt, um die `While col < lastcol` -Anweisung, die die nächste Iteration der innersten ist `While` -Schleife, enthält die `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="fa921-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fa921-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa921-119">See Also</span></span>  
 [<span data-ttu-id="fa921-120">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa921-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="fa921-121">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa921-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="fa921-122">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa921-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="fa921-123">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa921-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
