---
title: 'Gewusst wie: Bestimmen der Gleichheit zweier Objekte'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348598"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)
In Visual Basic werden zwei Variablen Verweise als identisch betrachtet, wenn die Zeiger identisch sind, d. h., wenn beide Variablen auf dieselbe Klasseninstanz im Arbeitsspeicher verweisen. Beispielsweise können Sie in einer Windows Forms Anwendung einen Vergleich durchführen, um zu bestimmen, ob die aktuelle Instanz (`Me`) mit einer bestimmten Instanz identisch ist, z. b. `Form2`.  
  
 Visual Basic stellt zwei Operatoren zum Vergleichen von Zeigern bereit. Der [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` zurück, wenn die Objekte identisch sind, und der [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` zurück, wenn dies nicht der Fall ist.  
  
## <a name="determining-if-two-objects-are-identical"></a>Ermitteln, ob zwei Objekte identisch sind  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>So bestimmen Sie, ob zwei Objekte identisch sind  
  
1. Richten Sie einen `Boolean` Ausdruck ein, um die beiden Objekte zu testen.  
  
2. Verwenden Sie im Test Ausdruck den `Is`-Operator mit den beiden-Objekten als Operanden.  
  
     `Is` gibt `True` zurück, wenn die Objekte auf dieselbe Klasseninstanz verweisen.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Ermitteln, ob zwei Objekte nicht identisch sind  
 Manchmal möchten Sie eine Aktion ausführen, wenn die beiden Objekte nicht identisch sind, und es kann umständlich sein, `Not` und `Is`zu kombinieren, z. b. `If Not obj1 Is obj2`. In einem solchen Fall können Sie den `IsNot`-Operator verwenden.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>So bestimmen Sie, ob zwei Objekte nicht identisch sind  
  
1. Richten Sie einen `Boolean` Ausdruck ein, um die beiden Objekte zu testen.  
  
2. Verwenden Sie im Test Ausdruck den `IsNot`-Operator mit den beiden-Objekten als Operanden.  
  
     `IsNot` gibt `True` zurück, wenn die Objekte nicht auf dieselbe Klasseninstanz verweisen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Paare von `Object` Variablen getestet, um festzustellen, ob Sie auf dieselbe Klasseninstanz verweisen.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 Im vorangehenden Beispiel wird die folgende Ausgabe angezeigt.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Siehe auch

- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
