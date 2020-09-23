---
title: 'Vorgehensweise: Bestimmen der Gleichheit zweier Objekte'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 1bbc8083fcfb6f5ff0f4328c32b83a2e7218ecd6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072274"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)

In Visual Basic werden zwei Variablen Verweise als identisch betrachtet, wenn die Zeiger identisch sind, d. h., wenn beide Variablen auf dieselbe Klasseninstanz im Arbeitsspeicher verweisen. Beispielsweise können Sie in einer Windows Forms Anwendung einen Vergleich durchführen, um zu bestimmen, ob die aktuelle Instanz ( `Me` ) mit einer bestimmten Instanz identisch ist, z. b `Form2` ..  
  
 Visual Basic stellt zwei Operatoren zum Vergleichen von Zeigern bereit. Der [is-Operator](../../../language-reference/operators/is-operator.md) gibt zurück `True` , wenn die Objekte identisch sind, und der [IsNot-Operator](../../../language-reference/operators/isnot-operator.md) gibt zurück, wenn dies nicht der Fall ist `True` .  
  
## <a name="determining-if-two-objects-are-identical"></a>Ermitteln, ob zwei Objekte identisch sind  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>So bestimmen Sie, ob zwei Objekte identisch sind  
  
1. Richten Sie einen- `Boolean` Ausdruck ein, um die beiden-Objekte zu testen.  
  
2. Verwenden Sie im Test Ausdruck den- `Is` Operator mit den beiden-Objekten als Operanden.  
  
     `Is` Gibt zurück `True` , wenn die Objekte auf dieselbe Klasseninstanz verweisen.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Ermitteln, ob zwei Objekte nicht identisch sind  

 Manchmal möchten Sie eine Aktion durchführen, wenn die beiden Objekte nicht identisch sind, und das kombinieren und beispielsweise umständlich sein kann `Not` `Is` `If Not obj1 Is obj2` . In einem solchen Fall können Sie den- `IsNot` Operator verwenden.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>So bestimmen Sie, ob zwei Objekte nicht identisch sind  
  
1. Richten Sie einen- `Boolean` Ausdruck ein, um die beiden-Objekte zu testen.  
  
2. Verwenden Sie im Test Ausdruck den- `IsNot` Operator mit den beiden-Objekten als Operanden.  
  
     `IsNot` Gibt zurück `True` , wenn die Objekte nicht auf dieselbe Klasseninstanz verweisen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel `Object` werden Variablen Paare getestet, um festzustellen, ob Sie auf dieselbe Klasseninstanz verweisen.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 Im vorangehenden Beispiel wird die folgende Ausgabe angezeigt.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Siehe auch

- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Objektvariablen](object-variables.md)
- [Werte von Objektvariablen](object-variable-values.md)
- [Is-Operator](../../../language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../language-reference/operators/isnot-operator.md)
- [Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten](how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase und MyClass](../../program-structure/me-my-mybase-and-myclass.md)
