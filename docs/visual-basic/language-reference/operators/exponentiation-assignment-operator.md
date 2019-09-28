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
ms.openlocfilehash: 382e0b27c2dbf27e5acccf29f1b8d2b002cb6664
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592235"
---
# <a name="-operator-visual-basic"></a>^=-Operator (Visual Basic)
Löst den Wert einer Variablen oder Eigenschaft für die Potenz eines Ausdrucks aus und weist das Ergebnis wieder der Variablen oder der Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des `^=`-Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
 Der `^=`-Operator löst zuerst den Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators) bis zur Potenz des Werts des Ausdrucks (auf der rechten Seite des Operators) aus. Der Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zurück.  
  
 Visual Basic führt immer eine exponentiell im [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)aus. Operanden eines beliebigen Typs werden in `Double` konvertiert, und das Ergebnis ist immer `Double`.  
  
 Der Wert von `expression` kann eine Bruch Zahl, eine negative oder beides sein.  
  
## <a name="overloading"></a>Überladen  
 Der [^-Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) kann *überladen*werden, was bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des `^`-Operators wirkt sich auf das Verhalten des `^=`-Operators aus. Wenn Ihr Code `^=` für eine Klasse oder Struktur verwendet, die `^` überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `^=`-Operator verwendet, um den Wert einer `Integer`-Variablen auf die Potenz einer zweiten Variablen zu erhöhen und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Siehe auch

- [^-Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
