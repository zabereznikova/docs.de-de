---
title: '&amp;=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: dee30096f244adc34b83fdfdc6af0baabd372b4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672408"
---
# <a name="amp-operator-visual-basic"></a>&amp;=-Operator (Visual Basic)
Verkettet eine `String` Ausdruck, der eine `String` Variable oder eine Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Alle `String` Variable oder eine Eigenschaft.  
  
 `expression`  
 Erforderlich. Beliebiger `String` -Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `&=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Die `&=` Operator verkettet die `String` Ausdruck auf der rechten Seite, um die `String` Variable oder eine Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder die Eigenschaft auf der linken Seite.  
  
## <a name="overloading"></a>Überladen  
 Die [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Das Überladen der `&` Operator beeinflusst das Verhalten von der `&=` Operator. Wenn Ihr Code verwendet `&=` für eine Klasse oder Struktur, die Überladungen `&`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `&=` Operator zum Verketten von zwei `String` Variablen und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
