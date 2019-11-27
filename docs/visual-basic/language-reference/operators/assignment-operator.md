---
title: Operator =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 75f303219b9bf32613989f65f90a9096ef70e02e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350206"
---
# <a name="-operator-visual-basic"></a>=-Operator (Visual Basic)
Weist einer Variablen oder Eigenschaft einen Wert zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>-Komponenten  
 `variableorproperty`  
 Eine beliebige beschreibbare Variable oder eine beliebige Eigenschaft.  
  
 `value`  
 Beliebiges Literalzeichen, Konstante oder Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des Gleichheitszeichens (`=`) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md) Der `=`-Operator weist der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite zu.  
  
> [!NOTE]
> Der `=`-Operator wird auch als Vergleichs Operator verwendet. Weitere Informationen finden Sie unter [Vergleichs Operatoren](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Überladen  
 Der `=`-Operator kann nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der Zuweisungs Operator veranschaulicht. Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [+=-Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Operator-= (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Operator/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
