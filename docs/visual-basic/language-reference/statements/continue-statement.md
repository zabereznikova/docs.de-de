---
title: Continue-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: cf73ea1b3d402609c9966980dcab9ddd9bc096c2
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874961"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="6b6e8-102">Continue-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b6e8-102">Continue Statement (Visual Basic)</span></span>

<span data-ttu-id="6b6e8-103">Überträgt die Steuerung sofort an die nächste Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6e8-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="6b6e8-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6b6e8-105">Remarks</span></span>  

 <span data-ttu-id="6b6e8-106">Sie können von innerhalb einer- `Do` ,- `For` oder- `While` Schleife zur nächsten Iterationen dieser Schleife übertragen.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="6b6e8-107">Das Steuerelement wird sofort an den Schleifen Bedingungs Test übergeben, der der Übertragung an die- `For` oder- `While` Anweisung entspricht, oder an die-oder-Anweisung, die die-oder- `Do` `Loop` `Until` Klausel enthält `While` .</span><span class="sxs-lookup"><span data-stu-id="6b6e8-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="6b6e8-108">Sie können `Continue` an jeder beliebigen Stelle in der Schleife verwenden, die Übertragungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="6b6e8-109">Die Regeln, die die Übertragung der Steuerung zulassen, sind identisch mit der [goto-Anweisung](goto-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6b6e8-109">The rules allowing transfer of control are the same as with the [GoTo Statement](goto-statement.md).</span></span>  
  
 <span data-ttu-id="6b6e8-110">Wenn eine-Schleife z. b. vollständig in einem- `Try` Block, einem-Block oder einem-Block enthalten ist `Catch` `Finally` , können Sie verwenden, `Continue` um aus der Schleife zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="6b6e8-111">Wenn andererseits die `Try` ... `End Try` -Struktur in der-Schleife enthalten ist, können Sie nicht verwenden, `Continue` um die Steuerung aus dem-Block zu übertragen `Finally` , und Sie können Sie nur verwenden, um aus einem-oder-Block zu übertragen, `Try` `Catch` Wenn Sie vollständig aus der `Try` ...-Struktur übertragen `End Try` .</span><span class="sxs-lookup"><span data-stu-id="6b6e8-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="6b6e8-112">Wenn Sie über geschachtelte Schleifen desselben Typs verfügen, z. b `Do` . eine Schleife innerhalb einer anderen `Do` Schleife, springt eine- `Continue Do` Anweisung zur nächsten Iterationen der innersten Schleife, in der `Do` Sie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="6b6e8-113">Sie können nicht verwenden `Continue` , um zur nächsten Iterations Schleife einer enthaltenden Schleife desselben Typs zu springen.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="6b6e8-114">Wenn Sie geschachtelte Schleifen verschiedener Typen, z. b. eine- `Do` Schleife innerhalb einer-Schleife `For` , verwenden, können Sie mit oder mit der nächsten Iterations Schleife springen `Continue Do` `Continue For` .</span><span class="sxs-lookup"><span data-stu-id="6b6e8-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b6e8-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b6e8-115">Example</span></span>  

 <span data-ttu-id="6b6e8-116">Im folgenden Codebeispiel wird die- `Continue While` Anweisung verwendet, um zur nächsten Spalte eines Arrays zu springen, wenn ein Divisor gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="6b6e8-117">Der `Continue While` befindet sich innerhalb einer- `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="6b6e8-118">Es wird zur-Anweisung übertragen, bei der es sich um `While col < lastcol` die nächste Iterations Schleife der innersten Schleife handelt, die `While` die- `For` Schleife enthält.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="6b6e8-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b6e8-119">See also</span></span>

- [<span data-ttu-id="6b6e8-120">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b6e8-120">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="6b6e8-121">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b6e8-121">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="6b6e8-122">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b6e8-122">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="6b6e8-123">Try... Catch... Abschließend-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b6e8-123">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
