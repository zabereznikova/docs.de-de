---
title: /=-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: b4855e8270a329f9345339060a323b5ca9cd9792
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592173"
---
# <a name="-operator-visual-basic"></a>/=-Operator (Visual Basic)
Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Gleit Komma Ergebnis der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des `/=`-Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
 Der `/=`-Operator dividiert zuerst den Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators) durch den Wert des Ausdrucks (auf der rechten Seite des Operators). Der-Operator weist dann das Gleit Komma Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.  
  
 Diese Anweisung weist der Variablen oder der Eigenschaft auf der linken Seite einen `Double`-Wert zu. Wenn `Option Strict` `On` ist, muss `variableorproperty` ein `Double` sein. Wenn `Option Strict` `Off` ist, führt Visual Basic eine implizite Konvertierung durch und weist den resultierenden Wert `variableorproperty` mit einem möglichen Fehler zur Laufzeit zu. Weitere Informationen finden Sie unter [erweiternde und einschränkende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Überladen  
 Der [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des `/`-Operators wirkt sich auf das Verhalten des `/=`-Operators aus. Wenn Ihr Code `/=` für eine Klasse oder Struktur verwendet, die `/` überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `/=`-Operator verwendet, um eine `Integer`-Variable durch eine Sekunde zu teilen und den Quotienten der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Siehe auch

- [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [\\ =-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
