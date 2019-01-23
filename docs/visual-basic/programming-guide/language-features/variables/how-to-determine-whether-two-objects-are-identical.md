---
title: 'Vorgehensweise: Zu bestimmen, ob zwei Objekte identisch (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 62d73b6c3d706d9990be7783f0f3461fc0783d9f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512969"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Vorgehensweise: Zu bestimmen, ob zwei Objekte identisch (Visual Basic)
In Visual Basic sind Verweise auf zwei Variablen als identisch, wenn deren Zeiger identisch, d. h. sind Wenn beide Variablen auf die gleiche Klasseninstanz im Arbeitsspeicher verweisen. Z. B. in einer Windows Forms-Anwendung, Sie möchten stellen einen Vergleich aus, um zu bestimmen, ob die aktuelle Instanz (`Me`) ist identisch mit einer bestimmten Instanz, wie z. B. `Form2`.  
  
 Visual Basic bietet zwei Operatoren zum Vergleichen von Zeigern. Die [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` , wenn die Objekte identisch sind und die [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` Wenn dies nicht der Fall.  
  
## <a name="determining-if-two-objects-are-identical"></a>Bestimmen, ob zwei Objekte identisch sind.  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Um festzustellen, ob zwei Objekte identisch sind.  
  
1.  Richten Sie eine `Boolean` Ausdruck, der die beiden Objekte zu testen.  
  
2.  Testausdruck, verwenden Sie die `Is` Operator mit den beiden Objekten als Operanden.  
  
     `Is` Gibt `True` Wenn die Objekte auf die gleiche Instanz der Klasse zeigen.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Bestimmen, ob zwei Objekte nicht identisch sind.  
 Manchmal möchten Sie eine Aktion ausführen, wenn die beiden Objekte nicht identisch sind, und es kann schwierig zu kombinieren `Not` und `Is`, z. B. `If Not obj1 Is obj2`. In diesem Fall können Sie die `IsNot` Operator.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Um festzustellen, ob zwei Objekte nicht identisch sind.  
  
1.  Richten Sie eine `Boolean` Ausdruck, der die beiden Objekte zu testen.  
  
2.  Testausdruck, verwenden Sie die `IsNot` Operator mit den beiden Objekten als Operanden.  
  
     `IsNot` Gibt `True` Wenn die Objekte nicht auf die gleiche Instanz der Klasse zeigen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel testet die Paare von `Object` Variablen, um festzustellen, ob sie auf die gleiche Instanz der Klasse verweisen.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 Im vorherige Beispiel wird die folgende Ausgabe angezeigt.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Siehe auch
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Vorgehensweise: Bestimmen Sie, ob zwei Objekte verknüpft sind](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
