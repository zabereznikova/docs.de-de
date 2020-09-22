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
ms.openlocfilehash: eccea0b43564a4980778c9d1a5b8f9a8c2a9207d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874828"
---
# <a name="-operator-visual-basic"></a>=-Operator (Visual Basic)

Weist einer Variablen oder Eigenschaft einen Wert zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Bestandteile  

 `variableorproperty`  
 Eine beliebige beschreibbare Variable oder eine beliebige Eigenschaft.  
  
 `value`  
 Beliebiges Literalzeichen, Konstante oder Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  

 Das Element auf der linken Seite des Gleichheitszeichens ( `=` ) kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md) Der `=` Operator weist der Variablen oder der Eigenschaft auf der linken Seite den Wert auf der rechten Seite zu.  
  
> [!NOTE]
> Der- `=` Operator wird auch als Vergleichs Operator verwendet. Weitere Informationen finden Sie unter [Vergleichs Operatoren](comparison-operators.md).  
  
## <a name="overloading"></a>Überladen  

 Der `=` Operator kann nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der Zuweisungs Operator veranschaulicht. Der Wert auf der rechten Seite wird der Variablen auf der linken Seite zugewiesen.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Weitere Informationen

- [&=-Operator](and-assignment-operator.md)
- [Operator * =](multiplication-assignment-operator.md)
- [Operator + =](addition-assignment-operator.md)
- [Operator-= (Visual Basic)](subtraction-assignment-operator.md)
- [Operator/= (Visual Basic)](floating-point-division-assignment-operator.md)
- [\\=-Operator](integer-division-assignment-operator.md)
- [^ =-Operator](exponentiation-assignment-operator.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
- [Comparison Operators (Vergleichsoperatoren)](comparison-operators.md)
- [ReadOnly](../modifiers/readonly.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
