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
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)
Wenn Sie zwei Variablen, die auf Objekte verweisen haben, können Sie entweder die `Is` oder `IsNot` Operator oder beides, um zu bestimmen, ob sie auf der gleichen Instanz verweisen.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>So testen Sie, ob zwei Objekte gleich sind  
  
-   Verwenden der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Sie möchten eine bestimmte Aktion ausgeführt abhängig davon, ob zwei Objekte auf dieselbe Instanz verweisen. Das obige Beispiel vergleicht Steuerelement `c` für das aktive Steuerelement im Formular `f`. Wenn Steuerelement nicht aktives ist, oder es ein ist nicht der gleiche Steuerelementinstanz als `c`, und klicken Sie dann die `If` -Anweisung fehl, und die Prozedur gibt zurück, ohne weitere Verarbeitung.  
  
 Verwenden Sie, ob `Is` oder `IsNot` persönliche Annehmlichkeit für Sie ist. Eine möglicherweise einfacher, als das andere in einem bestimmten Ausdruck zu lesen.  
  
## <a name="see-also"></a>Siehe auch  
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
