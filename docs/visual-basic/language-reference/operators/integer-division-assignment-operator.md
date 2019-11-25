---
title: '\=-Operator'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: 600acf9b41b63358da245fe602595fee4093b15b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330946"
---
# <a name="-operator"></a>\\= Operator
Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Any numeric variable or property.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array. The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left  
  
 For further information on integer division, see [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Überladen  
 The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure. Overloading the `\` operator affects the behavior of the `\=` operator. If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Siehe auch

- [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
