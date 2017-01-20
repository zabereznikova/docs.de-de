---
title: "&amp;= Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.&="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operator &="
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "&= operator [Visual Basic]"
  - "compound assignment statements"
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &amp;= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Verkettet einen `String`\-Ausdruck mit einer `String`\-Variablen oder \-Eigenschaft und weist das Ergebnis der Variablen oder der Eigenschaft zu.  
  
## Syntax  
  
```  
  
variableorproperty &= expression  
```  
  
## Teile  
 `variableorproperty`  
 Erforderlich.  Beliebige `String`\-Variable oder \-Eigenschaft.  
  
 `expression`  
 Erforderlich.  Ein beliebiger `String`\-Ausdruck.  
  
## Hinweise  
 Das Element auf der linken Seite des Operators `&=` kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.  Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)sein.  Der Operator `&=` verkettet den `String` Ausdruck für das Recht zur `String`\-Variablen oder Eigenschaft auf der linken und weist das Ergebnis der Variablen oder Eigenschaft auf der linken Seite.  
  
## Überladen  
 Der [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Das Überladen des Operators `&` hat Auswirkungen auf das Verhalten des Operators `&=`.  Wenn im Code `&=` auf eine Klasse oder Struktur angewendet wird, die `&` überlädt, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `&=` verwendet, um zwei `String`\-Variablen zu verketten und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## Siehe auch  
 [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [\+\= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Concatenation Operators](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)