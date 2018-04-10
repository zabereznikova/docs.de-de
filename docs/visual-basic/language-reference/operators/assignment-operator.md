---
title: =-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 230005640b2b494e5413b14ba13a7cb82ee9f22b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>=-Operator (Visual Basic)
Weist einen Wert an eine Variable oder eine Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Jede schreibbare Variable oder eine Eigenschaft.  
  
 `value`  
 Ein Literal, eine Konstante oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Die `=` -Operator weist den Wert auf der rechten Seite der Variablen oder Eigenschaft auf der linken Seite.  
  
> [!NOTE]
>  Die `=` Operator wird auch als Vergleichsoperator verwendet. Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Überladen  
 Die `=` Operator kann nur als relationalen Vergleichsoperator und nicht als Zuweisungsoperator überladen werden. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, den Zuweisungsoperator. Der Wert auf der rechten Seite ist die Variable auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [Operator-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
