---
title: "Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="fa51d-102">Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa51d-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="fa51d-103">Wenn Sie zwei Variablen, die auf Objekte verweisen haben, können Sie entweder die `Is` oder `IsNot` Operator oder beides, um zu bestimmen, ob sie auf der gleichen Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="fa51d-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="fa51d-104">So testen Sie, ob zwei Objekte gleich sind</span><span class="sxs-lookup"><span data-stu-id="fa51d-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="fa51d-105">Verwenden der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.</span><span class="sxs-lookup"><span data-stu-id="fa51d-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="fa51d-106">Sie möchten eine bestimmte Aktion ausgeführt abhängig davon, ob zwei Objekte auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="fa51d-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="fa51d-107">Das obige Beispiel vergleicht Steuerelement `c` für das aktive Steuerelement im Formular `f`.</span><span class="sxs-lookup"><span data-stu-id="fa51d-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="fa51d-108">Wenn Steuerelement nicht aktives ist, oder es ein ist nicht der gleiche Steuerelementinstanz als `c`, und klicken Sie dann die `If` -Anweisung fehl, und die Prozedur gibt zurück, ohne weitere Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="fa51d-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="fa51d-109">Verwenden Sie, ob `Is` oder `IsNot` persönliche Annehmlichkeit für Sie ist.</span><span class="sxs-lookup"><span data-stu-id="fa51d-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="fa51d-110">Eine möglicherweise einfacher, als das andere in einem bestimmten Ausdruck zu lesen.</span><span class="sxs-lookup"><span data-stu-id="fa51d-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa51d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa51d-111">See Also</span></span>  
 [<span data-ttu-id="fa51d-112">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa51d-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
