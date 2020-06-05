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
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371985"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operator = (Visual Basic)
Verkettet einen `String` -Ausdruck mit einer `String` Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder der Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Bestandteile  
 `variableorproperty`  
 Erforderlich. Eine beliebige `String` Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Beliebiger `String` -Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Das Element auf der linken Seite des `&=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md) Der `&=` Operator verkettet den `String` Ausdruck auf der rechten Seite mit der `String` Variablen oder der Eigenschaft auf der linken Seite und weist das Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.  
  
## <a name="overloading"></a>Überladen  
 Der [&-Operator](concatenation-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `&` Operators wirkt sich auf das Verhalten des- `&=` Operators aus. Wenn Ihr Code `&=` für eine Klasse oder Struktur verwendet, die überlastet `&` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `&=` -Operator verwendet, um zwei Variablen zu verketten `String` und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [&-Operator](concatenation-operator.md)
- [Operator + =](addition-assignment-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Verkettungs Operatoren](concatenation-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
