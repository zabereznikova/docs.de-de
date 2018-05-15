---
title: 'Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 005c91e6f4ec556a7e1bf255b47c8276a5d3d185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="a720b-102">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a720b-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="a720b-103">Wenn Sie zwei Variablen, die auf Objekte verweisen haben, können Sie entweder die `Is` oder `IsNot` Operator oder beides, um zu bestimmen, ob sie auf der gleichen Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="a720b-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="a720b-104">So testen Sie, ob zwei Objekte gleich sind</span><span class="sxs-lookup"><span data-stu-id="a720b-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="a720b-105">Verwenden der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.</span><span class="sxs-lookup"><span data-stu-id="a720b-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="a720b-106">Sie möchten eine bestimmte Aktion ausgeführt abhängig davon, ob zwei Objekte auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="a720b-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="a720b-107">Das obige Beispiel vergleicht Steuerelement `c` für das aktive Steuerelement im Formular `f`.</span><span class="sxs-lookup"><span data-stu-id="a720b-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="a720b-108">Wenn Steuerelement nicht aktives ist, oder es ein ist nicht der gleiche Steuerelementinstanz als `c`, und klicken Sie dann die `If` -Anweisung fehl, und die Prozedur gibt zurück, ohne weitere Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="a720b-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="a720b-109">Verwenden Sie, ob `Is` oder `IsNot` persönliche Annehmlichkeit für Sie ist.</span><span class="sxs-lookup"><span data-stu-id="a720b-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="a720b-110">Eine möglicherweise einfacher, als das andere in einem bestimmten Ausdruck zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a720b-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a720b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a720b-111">See Also</span></span>  
 [<span data-ttu-id="a720b-112">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a720b-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
