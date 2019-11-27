---
title: 'Gewusst wie: Überprüfen, ob zwei Objekte identisch sind'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343622"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="50f6a-102">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50f6a-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="50f6a-103">Wenn Sie über zwei Variablen verfügen, die auf-Objekte verweisen, können Sie entweder den `Is`-oder `IsNot`-Operator oder beides verwenden, um zu bestimmen, ob Sie auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="50f6a-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="50f6a-104">So testen Sie, ob zwei Objekte identisch sind</span><span class="sxs-lookup"><span data-stu-id="50f6a-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="50f6a-105">Verwenden Sie den [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder den [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.</span><span class="sxs-lookup"><span data-stu-id="50f6a-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="50f6a-106">Möglicherweise möchten Sie abhängig davon, ob zwei-Objekte auf dieselbe Instanz verweisen, eine bestimmte Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="50f6a-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="50f6a-107">Im vorangehenden Beispiel wird die Steuerelement `c` mit dem aktiven Steuerelement im Formular `f`verglichen.</span><span class="sxs-lookup"><span data-stu-id="50f6a-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="50f6a-108">Wenn kein aktives Steuerelement vorhanden ist, oder wenn es ein Steuerelement ist, aber nicht die gleiche Steuerelement Instanz wie `c`, dann schlägt die `If` Anweisung fehl, und die Prozedur wird ohne weitere Verarbeitung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50f6a-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="50f6a-109">Unabhängig davon, ob Sie `Is` oder `IsNot` verwenden, sind Sie für Sie persönlich.</span><span class="sxs-lookup"><span data-stu-id="50f6a-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="50f6a-110">Eine ist möglicherweise einfacher zu lesen als die andere in einem gegebenen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="50f6a-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f6a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50f6a-111">See also</span></span>

- [<span data-ttu-id="50f6a-112">Vergleichs Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50f6a-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
