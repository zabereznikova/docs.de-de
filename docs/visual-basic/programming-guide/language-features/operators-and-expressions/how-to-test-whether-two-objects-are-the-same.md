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
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)
Wenn Sie zwei Variablen, die auf Objekte verweisen haben, können Sie entweder die `Is` oder `IsNot` Operator oder beides, um zu bestimmen, ob sie auf der gleichen Instanz verweisen.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>So testen Sie, ob zwei Objekte gleich sind  
  
-   Verwenden der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Sie möchten eine bestimmte Aktion ausgeführt abhängig davon, ob zwei Objekte auf dieselbe Instanz verweisen. Das obige Beispiel vergleicht Steuerelement `c` für das aktive Steuerelement im Formular `f`. Wenn Steuerelement nicht aktives ist, oder es ein ist nicht der gleiche Steuerelementinstanz als `c`, und klicken Sie dann die `If` -Anweisung fehl, und die Prozedur gibt zurück, ohne weitere Verarbeitung.  
  
 Verwenden Sie, ob `Is` oder `IsNot` persönliche Annehmlichkeit für Sie ist. Eine möglicherweise einfacher, als das andere in einem bestimmten Ausdruck zu lesen.  
  
## <a name="see-also"></a>Siehe auch  
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
