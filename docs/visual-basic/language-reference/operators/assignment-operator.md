---
title: "= Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.Assign"
  - "vb.="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "= operator [Visual Basic]"
  - "= assignment statements [Visual Basic]"
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# = Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Weist einer Variablen oder Eigenschaft einen Wert zu.  
  
## Syntax  
  
```  
  
variableorproperty = value  
```  
  
## Teile  
 `variableorproperty`  
 Jede schreibbare Variable oder jede Eigenschaft.  
  
 `value`  
 Beliebiges Literal, eine Konstante oder ein Ausdruck.  
  
## Hinweise  
 Das Element auf der linken Seite des Gleichheitszeichens \(`=`\) kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.  Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)sein.  Der Operator `=` weist den Wert auf seiner rechten Seite der Variablen oder Eigenschaft auf seiner linken Seite zu.  
  
> [!NOTE]
>  Der Operator `=` wird auch als Vergleichsoperator verwendet.  Ausführlichere Informationen finden Sie unter [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## Überladen  
 Der Operator `=` kann als nur relationaler Vergleichsoperator, nicht als Zuweisungsoperator, überladen werden.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel wird der Zuweisungsoperator näher erläutert.  Der Wert auf rechten Seite wird der Variablen auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## Siehe auch  
 [&\= Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [\*\= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [\+\= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [\-\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [\/\= Operator](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\\= Operator](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [^\= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)