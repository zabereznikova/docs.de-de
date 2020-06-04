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
ms.openlocfilehash: a546d8b0c9b3852386970f80d3da96794da2351c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370946"
---
# <a name="-operator"></a>\\=-Operator
Dividiert den Wert einer Variablen oder Eigenschaft durch den Wert eines Ausdrucks und weist das ganzzahlige Ergebnis der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Bestandteile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Das Element auf der linken Seite des `\=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)  
  
 Der `\=` Operator dividiert den Wert einer Variablen oder Eigenschaft auf der linken Seite durch den Wert auf der rechten Seite und weist das ganzzahlige Ergebnis der Variablen oder der Eigenschaft auf der linken Seite zu.  
  
 Weitere Informationen zur ganzzahligen Division finden Sie unter [\-Operator (Visual Basic)](integer-division-operator.md).  
  
## <a name="overloading"></a>Überladen  
 Der `\` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des- `\` Operators wirkt sich auf das Verhalten des- `\=` Operators aus. Wenn Ihr Code `\=` für eine Klasse oder Struktur verwendet, die überlastet `\` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `\=` -Operator verwendet, um eine `Integer` Variable durch eine Sekunde zu teilen und das ganzzahlige Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Weitere Informationen

- [\-Operator (Visual Basic)](integer-division-operator.md)
- [Operator/= (Visual Basic)](floating-point-division-assignment-operator.md)
- [Zuweisungsoperatoren](assignment-operators.md)
- [Arithmetische Operatoren](arithmetic-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
