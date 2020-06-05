---
title: 'Vorgehensweise: Überprüfen, ob zwei Objekte identisch sind'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403420"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="1b05a-102">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b05a-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="1b05a-103">Wenn Sie über zwei Variablen verfügen, die auf-Objekte verweisen, können Sie entweder den-oder den- `Is` `IsNot` Operator oder beides verwenden, um zu bestimmen, ob Sie auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="1b05a-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="1b05a-104">So testen Sie, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="1b05a-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="1b05a-105">Verwenden Sie den [is-Operator](../../../language-reference/operators/is-operator.md) oder den [IsNot-Operator](../../../language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.</span><span class="sxs-lookup"><span data-stu-id="1b05a-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="1b05a-106">Möglicherweise möchten Sie abhängig davon, ob zwei-Objekte auf dieselbe Instanz verweisen, eine bestimmte Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="1b05a-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="1b05a-107">Im vorangehenden Beispiel wird das Steuerelement `c` mit dem aktiven Steuerelement auf dem Formular verglichen `f` .</span><span class="sxs-lookup"><span data-stu-id="1b05a-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="1b05a-108">Wenn kein aktives Steuerelement vorhanden ist, oder wenn es ein Steuerelement ist, aber nicht die gleiche Steuerelement Instanz wie `c` , `If` schlägt die Anweisung fehl, und die Prozedur gibt ohne weitere Verarbeitung zurück.</span><span class="sxs-lookup"><span data-stu-id="1b05a-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="1b05a-109">`Is`Unabhängig davon, ob Sie oder verwenden `IsNot` , sind Sie für Sie persönlich.</span><span class="sxs-lookup"><span data-stu-id="1b05a-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="1b05a-110">Eine ist möglicherweise einfacher zu lesen als die andere in einem gegebenen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1b05a-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b05a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b05a-111">See also</span></span>

- [<span data-ttu-id="1b05a-112">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b05a-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
