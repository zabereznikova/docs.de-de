---
title: ^=-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9d87d2f090a8c18aaab742e73878c7b80f55c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>^=-Operator (Visual Basic)
Löst den Wert einer Variablen oder Eigenschaft, um die Leistungsfähigkeit eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder eine Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `^=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `^=` löst der Operator zuerst den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) mit der der Wert des Ausdrucks (auf der rechten Seite des Operators). Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft an.  
  
 Visual Basic führt immer Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md). Die Operanden eines anderen Typs konvertiert werden `Double`, und das Ergebnis ist immer `Double`.  
  
 Der Wert des `expression` kann Bruch, negativ oder beides.  
  
## <a name="overloading"></a>Überladen  
 Die [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Überladen der `^` Operator wirkt sich auf das Verhalten der `^=` Operator. Wenn im Code verwendet `^=` auf eine Klasse oder Struktur, die Überladungen `^`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `^=` Operator zum Auslösen des Wertes eines `Integer` Variable mit einer zweiten Variable und das Ergebnis die erste Variable zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [^-Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
