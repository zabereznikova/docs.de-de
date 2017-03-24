---
title: 'Gewusst wie: bestimmen, ob zwei Objekte identisch (Visual Basic) sind | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3a853d9f958829eeb0fb42ecbcdae7ba912c89ed
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Gewusst wie: Bestimmen der Gleichheit zweier Objekte (Visual Basic)
In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Verweise auf zwei Variablen gelten als identisch, wenn deren Zeiger übereinstimmen, d. h., wenn beide Variablen auf die gleiche Klasseninstanz im Arbeitsspeicher verweisen. Z. B. in einer Windows Forms-Anwendung möglicherweise soll einen Vergleich aus, um zu bestimmen, ob die aktuelle Instanz (`Me`) ist identisch mit einer bestimmten Instanz, wie z. B. `Form2`.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet zwei Operatoren zum Vergleich von Zeigern. Die [Is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` , wenn die Objekte identisch sind und die [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` sind.  
  
## <a name="determining-if-two-objects-are-identical"></a>Bestimmen, ob zwei Objekte identisch sind  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Bestimmt, ob zwei Objekte identisch sind  
  
1.  Einrichten einer `Boolean` Ausdruck, der die beiden Objekte zu testen.  
  
2.  Verwenden Sie im Testausdruck den `Is` Operator mit den beiden Objekten als Operanden.  
  
     `Is`Gibt `True` , wenn die Objekte auf die gleiche Klasseninstanz zeigen.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Bestimmen, ob zwei Objekte identisch sind  
 Manchmal möchten Sie eine Aktion durchführen, wenn die beiden Objekte nicht identisch sind, und es kann schwierig zu kombinieren `Not` und `Is`, z. B. `If Not obj1 Is obj2`. In diesem Fall können Sie die `IsNot` Operator.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Bestimmt, ob zwei Objekte identisch sind  
  
1.  Einrichten einer `Boolean` Ausdruck, der die beiden Objekte zu testen.  
  
2.  Verwenden Sie im Testausdruck den `IsNot` Operator mit den beiden Objekten als Operanden.  
  
     `IsNot`Gibt `True` , wenn die Objekte nicht auf die gleiche Klasseninstanz zeigen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel testet Paare von `Object` Variablen, um festzustellen, ob sie auf die gleiche Klasseninstanz zeigen.  
  
 [!code-vb[VbVbalrKeywords&14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 Im vorhergehenden Beispiel wird die folgende Ausgabe.  
  
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
