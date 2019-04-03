---
title: ^=-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5d7b3dcb55192167512e0934e09cff7dfddb6d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819650"
---
# <a name="-operator-visual-basic"></a>^=-Operator (Visual Basic)
Erhöht den Wert einer Variablen oder Eigenschaft, um die Leistung eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Alle numerischen Variablen oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `^=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `^=` löst der Operator zuerst den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators) mit dem Wert des Ausdrucks (auf der rechten Seite des Operators). Der Operator weist das Ergebnis des Vorgangs klicken Sie dann die Variable oder Eigenschaft an.  
  
 Visual Basic führt immer die Potenzierung der [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md). Die Operanden eines anderen Typs werden in konvertiert `Double`, und das Ergebnis ist immer `Double`.  
  
 Der Wert des `expression` möglich Bruch, negativ oder beides.  
  
## <a name="overloading"></a>Überladen  
 Die [^-Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Das Überladen der `^` Operator beeinflusst das Verhalten von der `^=` Operator. Wenn Ihr Code verwendet `^=` für eine Klasse oder Struktur, die Überladungen `^`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `^=` Operator, um den Wert eines auslösen `Integer` Variable mit einer zweiten Variablen, und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Siehe auch

- [^-Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
