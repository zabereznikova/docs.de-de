---
title: "-= Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.-="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-= operator [Visual Basic]"
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "operator -="
  - "compound assignment statements"
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# -= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Subtrahiert den Wert eines Ausdrucks vom Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft zu.  
  
## Syntax  
  
```  
  
variableorproperty -= expression  
```  
  
## Teile  
 `variableorproperty`  
 Erforderlich.  Beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Hinweise  
 Der Name auf der linken Seite des Operators `-=` kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.  Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)sein.  
  
 Der Operator `-=` subtrahiert zuerst den Wert des Ausdrucks auf der rechten Seite des Operators\) vom Wert der Variablen oder Eigenschaft auf der linken Seite des Operators\).  Der Operator weist dann das Ergebnis dieses Vorgangs zur Variablen oder Eigenschaft zu.  
  
## Überladen  
 Der Operator [\- Operator](../../../visual-basic/language-reference/operators/subtraction-operator.md) kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn der Operator `-` überladen wird, wirkt sich dies auf das Verhalten des Operators `-=` aus.  Wenn im Code `-=` auf eine Klasse oder Struktur angewendet wird, die `-` überlädt, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator **–\=** verwendet, um eine `Integer`\-Variable von einer anderen abzuziehen und das Ergebnis der zweiten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#11](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-assignment_1.vb)]  
  
## Siehe auch  
 [\- Operator](../../../visual-basic/language-reference/operators/subtraction-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)