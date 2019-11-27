---
title: '&amp;=-Operator'
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
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350266"
---
# <a name="amp-operator-visual-basic"></a>&amp;=-Operator (Visual Basic)
Verkettet einen `String` Ausdruck zu einer `String` Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>-Komponenten  
 `variableorproperty`  
 Erforderlich Beliebige `String` Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich Beliebiger `String` -Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des `&=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md) Der `&=`-Operator verkettet den `String` Ausdruck auf der rechten Seite mit der `String` Variable oder Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.  
  
## <a name="overloading"></a>Überladen  
 Der [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des `&` Operators wirkt sich auf das Verhalten des `&=` Operators aus. Wenn Ihr Code `&=` in einer Klasse oder Struktur verwendet, die `&`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `&=`-Operator verwendet, um zwei `String` Variablen zu verketten und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- [&-Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
