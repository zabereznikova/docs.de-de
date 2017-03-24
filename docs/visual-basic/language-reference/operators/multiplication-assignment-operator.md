---
title: "*= Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.*="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operator *="
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "*= operator [Visual Basic]"
  - "compound assignment statements"
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# *= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Multipliziert den Wert einer Variablen oder Eigenschaft mit dem Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft zu.  
  
## Syntax  
  
```  
  
variableorproperty *= expression  
```  
  
## Teile  
 `variableorproperty`  
 Erforderlich.  Beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Hinweise  
 Der Name auf der linken Seite des Operators `*=` kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.  Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)sein.  
  
 Der Operator `*=` multipliziert zuerst den Wert des Ausdrucks auf der rechten Seite des Operators\) durch den Wert der Variablen oder Eigenschaft auf der linken Seite des Operators\).  Der Operator weist dann das Ergebnis dieses Vorgangs zur Variablen oder Eigenschaft zu.  
  
## Überladen  
 Der [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Das Überladen des Operators `*` hat Auswirkungen auf das Verhalten des Operators `*=`.  Wenn im Code `*=` auf eine Klasse oder Struktur angewendet wird, die `*` überlädt, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `*=` verwendet, um eine `Integer`\-Variable mit einer anderen zu multiplizieren und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## Siehe auch  
 [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)