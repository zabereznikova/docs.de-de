---
title: "How to: Determine Whether Two Objects Are Identical (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "testing, objects"
  - "objects [Visual Basic], comparing"
  - "object variables, determining identity"
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Determine Whether Two Objects Are Identical (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] gelten zwei Variablenverweise als identisch, wenn deren Zeiger gleich sind, d. h., wenn beide Variablen im Arbeitsspeicher auf die gleiche Klasseninstanz zeigen.  So können Sie in einer Windows Forms\-Anwendung einen Vergleich ausführen, um zu bestimmen, ob die aktuelle Instanz \(`Me`\) mit einer bestimmten Instanz identisch ist, beispielsweise `Form2`.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt zwei Operatoren zum Vergleich von Zeigern bereit.  Der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) gibt `True` zurück, wenn die Objekte identisch sind. Der [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) gibt `True` zurück, wenn sie nicht identisch sind.  
  
## Bestimmen der Gleicheit zweier Objekte  
  
#### So stellen Sie fest, ob zwei Objekte identisch sind  
  
1.  Richten Sie einen `Boolean`\-Ausdruck ein, um die beiden Objekte zu testen.  
  
2.  Verwenden Sie im Testausdruck den Operator `Is` mit den beiden Objekten als Operanden.  
  
     `Is` gibt `True` zurück, wenn die Objekte auf die gleiche Klasseninstanz zeigen.  
  
## Bestimmen der Ungleichheit zweier Objekte  
 Es kann vorkommen, dass Sie eine Aktion ausführen möchten, wenn die beiden Objekte nicht identisch sind. Dabei ist es eventuell umständlich, `Not` und `Is` zu kombinieren, wie z. B. bei `If Not obj1 Is obj2`.  In einem solchen Fall können Sie den Operator `IsNot` verwenden.  
  
#### So stellen Sie fest, ob zwei Objekte nicht identisch sind  
  
1.  Richten Sie einen `Boolean`\-Ausdruck ein, um die beiden Objekte zu testen.  
  
2.  Verwenden Sie im Testausdruck den Operator `IsNot` mit den beiden Objekten als Operanden.  
  
     `IsNot` gibt `True` zurück, wenn die Objekte nicht auf die gleiche Klasseninstanz zeigen.  
  
## Beispiel  
 Im folgenden Beispiel werden Paare von `Object`\-Variablen daraufhin getestet, ob sie auf die gleiche Klasseninstanz zeigen.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-tw_1.vb)]  
  
 Durch den Code im vorhergehenden Beispiel wird folgende Ausgabe angezeigt.  
  
 `objA different from objB?  True`  
  
 `objA identical to objC?  True`  
  
## Siehe auch  
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)