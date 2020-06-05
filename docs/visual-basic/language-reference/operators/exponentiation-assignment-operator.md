---
title: Operator ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: e631cc9a484b56ee059449ca1fbd9fc69405333d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371400"
---
# <a name="-operator-visual-basic"></a>^=-Operator (Visual Basic)
Löst den Wert einer Variablen oder Eigenschaft für die Potenz eines Ausdrucks aus und weist das Ergebnis wieder der Variablen oder der Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Bestandteile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Das Element auf der linken Seite des `^=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `^=` Operator löst zuerst den Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators) bis zur Potenz des Werts des Ausdrucks (auf der rechten Seite des Operators) aus. Der Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zurück.  
  
 Visual Basic führt immer eine exponentiell im [Double-Datentyp](../data-types/double-data-type.md)aus. Operanden eines beliebigen Typs werden in konvertiert `Double` , und das Ergebnis ist immer `Double` .  
  
 Der Wert von `expression` kann eine Bruch Zahl, eine negative oder beides sein.  
  
## <a name="overloading"></a>Überladen  
 Der [^-Operator](exponentiation-operator.md) kann *überladen*werden, was bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `^` Operators wirkt sich auf das Verhalten des- `^=` Operators aus. Wenn Ihr Code `^=` für eine Klasse oder Struktur verwendet, die überlastet `^` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `^=` -Operator verwendet, um den Wert einer `Integer` Variablen auf die Potenz einer zweiten Variablen zu erhöhen und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Weitere Informationen

- [^-Operator](exponentiation-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Arithmetische Operatoren](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
