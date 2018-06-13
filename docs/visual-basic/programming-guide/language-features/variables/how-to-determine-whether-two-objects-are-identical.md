---
title: 'Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650097"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)
In Visual Basic werden Verweise auf zwei Variablen als identisch angesehen, wenn ihre Zeiger gleich, d. h. sind Wenn beide Variablen auf die gleiche Klasseninstanz im Arbeitsspeicher verweisen. Beispielsweise sollten Sie in einer Windows Forms-Anwendung, stellen einen Vergleich aus, um zu bestimmen, ob die aktuelle Instanz (`Me`) ist identisch mit einer bestimmten Instanz, wie z. B. `Form2`.  
  
 Visual Basic bietet zwei Operatoren zum Vergleich von Zeigern. Die [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` , wenn die Objekte identisch sind und die [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` sind.  
  
## <a name="determining-if-two-objects-are-identical"></a>Bestimmen, ob zwei Objekte identisch sind.  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Um festzustellen, ob zwei Objekte identisch sind.  
  
1.  Einrichten einer `Boolean` Ausdruck, der die beiden Objekte getestet.  
  
2.  Testausdruck, verwenden die `Is` Operator mit den beiden Objekten als Operanden.  
  
     `Is` Gibt `True` , wenn die Objekte auf die gleiche Klasseninstanz zeigen.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Bestimmen, ob zwei Objekte nicht identisch sind.  
 Gelegentlich möchten Sie eine Aktion ausführen, wenn die beiden Objekte nicht überein stimmen, und es kann zu kombinierende hinderlich erweisen `Not` und `Is`, z. B. `If Not obj1 Is obj2`. In diesem Fall können Sie die `IsNot` Operator.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Um festzustellen, ob zwei Objekte nicht identisch sind.  
  
1.  Einrichten einer `Boolean` Ausdruck, der die beiden Objekte getestet.  
  
2.  Testausdruck, verwenden die `IsNot` Operator mit den beiden Objekten als Operanden.  
  
     `IsNot` Gibt `True` , wenn die Objekte nicht auf die gleiche Klasseninstanz zeigen.  
  
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
