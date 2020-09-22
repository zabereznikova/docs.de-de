---
title: Operator -=
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 9149d9b350fc05c5e576f9f7800725aeb330e79d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873296"
---
# <a name="--operator-visual-basic"></a>-=-Operator (Visual Basic)

Subtrahiert den Wert eines Ausdrucks vom Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder der Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>Bestandteile  

 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  

 Das Element auf der linken Seite des `-=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `-=` Operator subtrahiert zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators) vom Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators). Der-Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.  
  
## <a name="overloading"></a>Überladen  

 Der [-Operator (Visual Basic)](subtraction-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `-` Operators wirkt sich auf das Verhalten des- `-=` Operators aus. Wenn Ihr Code `-=` für eine Klasse oder Struktur verwendet, die überlastet `-` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der `-=` -Operator verwendet, um eine Variable von einer anderen zu subtrahieren `Integer` und das Ergebnis der letzteren Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Weitere Informationen

- [--Operator (Visual Basic)](subtraction-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
