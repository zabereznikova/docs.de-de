---
title: 'Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02083a93e63fe799f529776f777ca877d2d138b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)
In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], Verweise auf zwei Variablen werden als identisch, wenn ihre Zeiger gleich, d. h. sind, wenn beide Variablen auf die gleiche Klasseninstanz im Arbeitsspeicher verweisen. Beispielsweise sollten Sie in einer Windows Forms-Anwendung, stellen einen Vergleich aus, um zu bestimmen, ob die aktuelle Instanz (`Me`) ist identisch mit einer bestimmten Instanz, wie z. B. `Form2`.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]stellt zwei Operatoren zum Vergleich von Zeigern. Die [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` , wenn die Objekte identisch sind und die [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` sind.  
  
## <a name="determining-if-two-objects-are-identical"></a>Bestimmen, ob zwei Objekte identisch sind.  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Um festzustellen, ob zwei Objekte identisch sind.  
  
1.  Einrichten einer `Boolean` Ausdruck, der die beiden Objekte getestet.  
  
2.  Testausdruck, verwenden die `Is` Operator mit den beiden Objekten als Operanden.  
  
     `Is`Gibt `True` , wenn die Objekte auf die gleiche Klasseninstanz zeigen.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Bestimmen, ob zwei Objekte nicht identisch sind.  
 Gelegentlich möchten Sie eine Aktion ausführen, wenn die beiden Objekte nicht überein stimmen, und es kann zu kombinierende hinderlich erweisen `Not` und `Is`, z. B. `If Not obj1 Is obj2`. In diesem Fall können Sie die `IsNot` Operator.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Um festzustellen, ob zwei Objekte nicht identisch sind.  
  
1.  Einrichten einer `Boolean` Ausdruck, der die beiden Objekte getestet.  
  
2.  Testausdruck, verwenden die `IsNot` Operator mit den beiden Objekten als Operanden.  
  
     `IsNot`Gibt `True` , wenn die Objekte nicht auf die gleiche Klasseninstanz zeigen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel testet Paare von `Object` Variablen, um festzustellen, ob sie auf der gleichen Instanz verweisen.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 Das obige Beispiel zeigt die folgende Ausgabe.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Siehe auch  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
