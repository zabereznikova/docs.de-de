---
title: Operator /=
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
ms.openlocfilehash: 48ae78630aa66ad804d539f88524c456cf805889
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371244"
---
# <a name="-operator-visual-basic"></a>/=-Operator (Visual Basic)
Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das Gleit Komma Ergebnis der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Bestandteile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Das Element auf der linken Seite des `/=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `/=` Operator dividiert zuerst den Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators) durch den Wert des Ausdrucks (auf der rechten Seite des Operators). Der-Operator weist dann das Gleit Komma Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.  
  
 Diese Anweisung weist `Double` der Variablen oder der Eigenschaft auf der linken Seite einen Wert zu. Wenn `Option Strict` ist `On` , `variableorproperty` muss ein-Wert sein `Double` . Wenn `Option Strict` ist `Off` , führt Visual Basic eine implizite Konvertierung durch und weist den resultierenden Wert `variableorproperty` mit einem möglichen Fehler zur Laufzeit zu. Weitere Informationen finden Sie unter [erweiternde und einschränkende Konvertierungen](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Option Strict-Anweisung](../statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Überladen  
 Der [Operator/(Visual Basic)](floating-point-division-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `/` Operators wirkt sich auf das Verhalten des- `/=` Operators aus. Wenn Ihr Code `/=` für eine Klasse oder Struktur verwendet, die überlastet `/` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `/=` -Operator verwendet, um eine `Integer` Variable durch eine Sekunde zu teilen und den Quotienten der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Operator/(Visual Basic)](floating-point-division-operator.md)
- [\\=-Operator](integer-division-assignment-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Arithmetische Operatoren](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
