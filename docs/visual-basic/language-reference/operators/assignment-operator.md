---
title: = Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
dev_langs:
- VB
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
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
ms.openlocfilehash: 47b69a908f12ec36daf2848da6ee4b04895fd3a4
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-visual-basic"></a>=-Operator (Visual Basic)
Weist einen Wert einer Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
variableorproperty = value  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Jede schreibbare Variable oder jede Eigenschaft.  
  
 `value`  
 Jeder Literal, eine Konstante oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder die Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Die `=` -Operator weist den Wert auf der rechten Seite der Variablen oder Eigenschaft auf der linken Seite.  
  
> [!NOTE]
>  Die `=` Operator wird auch als Vergleichsoperator verwendet. Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Überladen  
 Die `=` Operator kann nur als ein relationaler Vergleichsoperator und nicht als Zuweisungsoperator überladen werden. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Zuweisungsoperator. Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [& = (Operator)](../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [^ =-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)   
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

