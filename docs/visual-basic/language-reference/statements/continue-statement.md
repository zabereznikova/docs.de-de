---
title: Continue-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005101"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="484fb-102">Continue-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="484fb-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="484fb-103">Überträgt die Steuerung sofort an die nächste Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="484fb-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="484fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="484fb-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="484fb-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="484fb-105">Remarks</span></span>  
 <span data-ttu-id="484fb-106">Sie können von innerhalb einer `Do`-, `For`-oder `While`-Schleife zur nächsten Iterationen dieser Schleife übertragen.</span><span class="sxs-lookup"><span data-stu-id="484fb-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="484fb-107">Das Steuerelement wird sofort an den Schleifen Bedingungs Test übergeben, der der Übertragung an die `For`-oder `While`-Anweisung oder an die `Do`-oder `Loop`-Anweisung entspricht, die die `Until`-oder `While`-Klausel enthält.</span><span class="sxs-lookup"><span data-stu-id="484fb-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="484fb-108">Sie können `Continue` an jeder beliebigen Stelle in der Schleife verwenden, die Übertragungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="484fb-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="484fb-109">Die Regeln, die die Übertragung der Steuerung zulassen, sind identisch mit der [goto-Anweisung](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="484fb-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="484fb-110">Wenn eine-Schleife z. b. vollständig in einem `Try`-Block, einem `Catch`-Block oder einem `Finally`-Block enthalten ist, können Sie `Continue` zum Übertragen der Schleife verwenden.</span><span class="sxs-lookup"><span data-stu-id="484fb-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="484fb-111">Wenn andererseits die Struktur `Try`... `End Try` in der Schleife enthalten ist, können Sie `Continue` nicht verwenden, um die Steuerung aus dem `Finally`-Block zu übertragen, und Sie können Sie verwenden, um aus einem `Try`-oder `Catch`-Block nur zu übertragen, wenn Sie vollständig aus dem @no_ _T-6... `End Try`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="484fb-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="484fb-112">Wenn Sie über geschachtelte Schleifen desselben Typs verfügen, z. b. eine `Do`-Schleife innerhalb einer anderen `Do`-Schleife, überspringt eine `Continue Do`-Anweisung die nächste Iterations Schleife der innersten `Do`-Schleife, in der Sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="484fb-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="484fb-113">@No__t-0 kann nicht verwendet werden, um zur nächsten Iterations Schleife einer enthaltenden Schleife desselben Typs zu springen.</span><span class="sxs-lookup"><span data-stu-id="484fb-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="484fb-114">Wenn Sie geschachtelte Schleifen verschiedener Typen haben, z. b. eine `Do`-Schleife innerhalb einer `For`-Schleife, können Sie mit `Continue Do` oder `Continue For` mit der nächsten Iterationen der beiden Schleifen springen.</span><span class="sxs-lookup"><span data-stu-id="484fb-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="484fb-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="484fb-115">Example</span></span>  
 <span data-ttu-id="484fb-116">Im folgenden Codebeispiel wird die `Continue While`-Anweisung verwendet, um zur nächsten Spalte eines Arrays zu springen, wenn ein Divisor gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="484fb-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="484fb-117">Der `Continue While` befindet sich innerhalb einer `For`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="484fb-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="484fb-118">Es wird auf die `While col < lastcol`-Anweisung übertragen, bei der es sich um die nächste Iterationen der innersten `While`-Schleife handelt, die die `For`-Schleife enthält.</span><span class="sxs-lookup"><span data-stu-id="484fb-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="484fb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="484fb-119">See also</span></span>

- [<span data-ttu-id="484fb-120">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="484fb-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="484fb-121">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="484fb-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="484fb-122">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="484fb-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="484fb-123">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="484fb-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
