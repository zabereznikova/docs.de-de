---
title: Continue-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835382"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="8fa35-102">Continue-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fa35-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="8fa35-103">Überträgt die Steuerung sofort an die nächste Iteration einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="8fa35-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fa35-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="8fa35-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fa35-105">Remarks</span></span>  
 <span data-ttu-id="8fa35-106">Sie können über übertragen innerhalb einer `Do`, `For`, oder `While` Schleife, um der nächsten Iteration der Schleife.</span><span class="sxs-lookup"><span data-stu-id="8fa35-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="8fa35-107">Wird sofort in der Schleife Bedingung Tests, die entspricht, für die Übertragung an die Steuerung der `For` oder `While` -Anweisung oder der `Do` oder `Loop` -Anweisung, enthält die `Until` oder `While` Klausel.</span><span class="sxs-lookup"><span data-stu-id="8fa35-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="8fa35-108">Sie können `Continue` an einer beliebigen Position in der Schleife, die Übertragung zulässt.</span><span class="sxs-lookup"><span data-stu-id="8fa35-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="8fa35-109">Die Übertragung der Steuerung ermöglichen Regeln sind identisch mit der [GoTo-Anweisung](../../../visual-basic/language-reference/statements/goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8fa35-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="8fa35-110">Z. B. wenn eine Schleife vollständig enthalten ist eine `Try` Block, eine `Catch` Block oder ein `Finally` blockieren, können Sie `Continue` aus der Schleife zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="8fa35-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="8fa35-111">Wenn sich dagegen die `Try`... `End Try` Struktur innerhalb der Schleife enthalten ist, können keine `Continue` zum Übergeben der Steuerung aus der `Finally` Block, und verwenden sie zum Übertragen von eine `Try` oder `Catch` blockiert werden, nur, wenn Sie vollständig aus übertragen der `Try`... `End Try` Struktur.</span><span class="sxs-lookup"><span data-stu-id="8fa35-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="8fa35-112">Bei geschachtelten Schleifen desselben Typs, z. B. eine `Do` Schleife innerhalb einer anderen `Do` Schleife, einer `Continue Do` überspringt die Anweisung an die nächste Iteration der innersten `Do` Schleife, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="8fa35-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="8fa35-113">Sie können keine `Continue` an die nächste Iteration einer Schleife mit desselben Typs zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="8fa35-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="8fa35-114">Wenn Sie z. B. geschachtelte Schleifen verschiedener Typen haben eine `Do` innerhalb einer Schleife eine `For` Schleife können Sie mit der nächsten Iteration der beiden Schleifen fortfahren, indem Sie entweder `Continue Do` oder `Continue For`.</span><span class="sxs-lookup"><span data-stu-id="8fa35-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fa35-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fa35-115">Example</span></span>  
 <span data-ttu-id="8fa35-116">Im folgenden Codebeispiel wird die `Continue While` Anweisung, um auf die nächste Spalte mit einem Array zu überspringen, wenn eine Division durch 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="8fa35-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="8fa35-117">Die `Continue While` befindet sich innerhalb einer `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="8fa35-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="8fa35-118">Wird an die `While col < lastcol` -Anweisung, die die nächste Iteration der innersten ist `While` -Schleife, enthält die `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="8fa35-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="8fa35-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fa35-119">See also</span></span>

- [<span data-ttu-id="8fa35-120">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fa35-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="8fa35-121">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fa35-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="8fa35-122">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fa35-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="8fa35-123">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8fa35-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
