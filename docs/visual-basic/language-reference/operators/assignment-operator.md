---
title: =-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: ad74e3ebc947af4f36022be838b69df6ce24997a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840288"
---
# <a name="-operator-visual-basic"></a>=-Operator (Visual Basic)
Eine Variable oder Eigenschaft ein Wert zugewiesen.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Jeder schreibbare Variable oder eine Eigenschaft.  
  
 `value`  
 Jeder Literal, eine Konstante oder ein Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Die `=` Operator weist den Wert auf der rechten Seite auf die Variable oder Eigenschaft auf der linken Seite.  
  
> [!NOTE]
>  Die `=` -Operator wird auch als Vergleichsoperator verwendet. Weitere Informationen finden Sie unter [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Überladen  
 Die `=` Operator kann nur als relationale Vergleichsoperator und nicht als ein Zuweisungsoperator überladen werden. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, den Zuweisungsoperator. Der Wert auf der rechten Seite wird die Variable auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Operator-=-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [/ =-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
