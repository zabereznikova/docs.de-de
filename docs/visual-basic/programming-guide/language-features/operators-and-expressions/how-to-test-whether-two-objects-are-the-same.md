---
title: 'Vorgehensweise: Überprüfen Sie, ob zwei Objekte der gleichen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: d13671f284863fa7bf56964c2b9b963c25e8ea52
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977447"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="d4258-102">Vorgehensweise: Überprüfen Sie, ob zwei Objekte der gleichen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4258-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="d4258-103">Wenn Sie zwei Variablen, die auf Objekte verweisen verfügen, verwenden Sie entweder die `Is` oder `IsNot` Operator oder beides, um zu bestimmen, ob sie an dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="d4258-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="d4258-104">Zum Überprüfen, ob zwei Objekte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="d4258-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="d4258-105">Verwenden der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.</span><span class="sxs-lookup"><span data-stu-id="d4258-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="d4258-106">Sie möchten eine bestimmte Aktion ausgeführt abhängig davon, ob zwei Objekte auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="d4258-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="d4258-107">Im vorherige Beispiel vergleicht Steuerelement `c` für das aktive Steuerelement im Formular `f`.</span><span class="sxs-lookup"><span data-stu-id="d4258-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="d4258-108">Wenn keine aktiven Steuerelement vorhanden ist, oder ist es ein, aber es ist nicht der gleichen Instanz des Steuerelements als `c`, und klicken Sie dann die `If` Anweisung fehl, und die Prozedur zurückgegeben werden, ohne weitere Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="d4258-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="d4258-109">Gibt an, ob Sie verwenden `Is` oder `IsNot` persönliche aus Gründen der Bequemlichkeit für Sie ist.</span><span class="sxs-lookup"><span data-stu-id="d4258-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="d4258-110">Eine möglicherweise einfacher, als das andere in einem bestimmten Ausdruck zu lesen.</span><span class="sxs-lookup"><span data-stu-id="d4258-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4258-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4258-111">See also</span></span>
- [<span data-ttu-id="d4258-112">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4258-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
