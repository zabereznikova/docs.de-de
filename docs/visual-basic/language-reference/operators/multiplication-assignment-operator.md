---
title: '*=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 3863e6c7416057507e8ae569804ed4a1be6a5b50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604158"
---
# <a name="-operator-visual-basic"></a>*=-Operator (Visual Basic)
Multipliziert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder eine Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `*=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `*=` Operator multipliziert zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators), durch den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators). Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft.  
  
## <a name="overloading"></a>Überladen  
 Die [*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Überladen der `*` Operator wirkt sich auf das Verhalten der `*=` Operator. Wenn im Code verwendet `*=` auf eine Klasse oder Struktur, die Überladungen `*`, achten Sie verstehen, dass ihr neu definierten Verhalten. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `*=` Operator, um eine Multiplizieren `Integer` Variable, indem das zweite und das Ergebnis die erste Variable zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
