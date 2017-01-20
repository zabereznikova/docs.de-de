---
title: "IsNot Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.isnot"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsNot operator"
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# IsNot Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Vergleicht zwei Objektverweisvariablen.  
  
## Syntax  
  
```  
  
result = object1 IsNot object2  
```  
  
## Teile  
 `result`  
 Erforderlich.  Ein `Boolean`\-Wert.  
  
 `object1`  
 Erforderlich.  Beliebige `Object`\-Variable oder beliebiger Ausdruck.  
  
 `object2`  
 Erforderlich.  Beliebige `Object`\-Variable oder beliebiger Ausdruck.  
  
## Hinweise  
 Der Operator `IsNot` stellt fest, ob zwei Objektverweise auf unterschiedliche Objekte verweisen.  Jedoch werden keine Wertvergleiche ausgeführt.  Wenn sowohl `object1` als auch `object2` auf dieselbe Objektinstanz verweisen, dann ist `result` gleich `False`; verweisen sie nicht auf dieselbe Objektinstanz, dann ist `result` gleich `True`.  
  
 `IsNot` ist das Gegenteil des Operators `Is`.  Der Vorteil von `IsNot` besteht darin, dass Sie eine umständliche und eventuell schwer lesbare Syntax mit `Not` und `Is` vermeiden können.  
  
 Mit dem Operator `Is` und dem Operator `IsNot` können Sie sowohl früh gebundene als auch spät gebundene Objekte testen.  
  
> [!NOTE]
>  Der `IsNot`\-Operator kann nicht dazu verwendet werden, vom `TypeOf`\-Operator zurückgegebene Ausdrücke zu vergleichen.  Stattdessen müssen Sie den `Not`\-Operator und den `Is`\-Operator verwenden.  
  
## Beispiel  
 Im folgenden Codebeispiel werden für denselben Vergleich sowohl der Operator `Is` als auch der Operator `IsNot` verwendet.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## Siehe auch  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [How to: Test Whether Two Objects Are the Same](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)