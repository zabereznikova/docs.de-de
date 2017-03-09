---
title: "/= Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb./="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "/= operator [Visual Basic]"
  - "operator /="
  - "compound assignment statements"
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# /= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist die sich daraus ergebende Gleitkommazahl der Variablen oder Eigenschaft zu.  
  
## Syntax  
  
```  
  
variableorproperty /= expression  
```  
  
## Teile  
 `variableorproperty`  
 Erforderlich.  Beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Hinweise  
 Das Element auf der linken Seite des Operators `/=` kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.  Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)sein.  
  
 Der `/=` zuerst Operator teilt der Wert der Variablen oder Eigenschaft auf der linken Seite des Operators\) durch den Wert des Ausdrucks auf der rechten Seite des Operators\).  Der Operator weist dann das Ergebnis dieses Vorgangs float der Variablen oder Eigenschaft zu.  
  
 Diese Anweisung weist einen `Double` Wert der Variablen oder Eigenschaft auf der linken Seite.  Wenn `Option Strict` den Wert `On` hat, muss `variableorproperty` ein `Double`\-Wert sein.  Wenn `Option Strict` den Wert `Off` hat, führt Visual Basic eine implizite Konvertierung durch und weist den resultierenden Wert `variableorproperty` zu, wobei zur Laufzeit ein Fehler auftreten kann.  Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## Überladen  
 Der [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Das Überladen des Operators `/` hat Auswirkungen auf das Verhalten des Operators `/=`.  Wenn im Code `/=` auf eine Klasse oder Struktur angewendet wird, die `/` überlädt, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Operator `/=` verwendet, um eine `Integer`\-Variable durch eine andere zu dividieren und den Quotienten der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/floating-point-division-_0_1.vb)]  
  
## Siehe auch  
 [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [\\\= Operator](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)