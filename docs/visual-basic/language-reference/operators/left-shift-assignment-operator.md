---
title: << =-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: da2b5ca0b7538d77c3c8d8bc7d45712d656ce63a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768315"
---
# <a name="-operator-visual-basic"></a>\<\<=-Operator (Visual Basic)
Führt eine arithmetische Verschiebung nach links auf dem Wert einer Variable oder eine Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Variable oder eine Eigenschaft, ein ganzzahliger Typ (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck eines Datentyps, die erweitert werden kann, `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `<<=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `<<=` -Operator führt eine arithmetische Verschiebung nach links zuerst auf dem Wert der Variablen oder Eigenschaft. Der Operator weist das Ergebnis des Vorgangs klicken Sie dann diese Variable oder eine Eigenschaft an.  
  
 Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden. In eine arithmetische Verschiebung nach links die Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite werden auf 0 (null) festgelegt.  
  
## <a name="overloading"></a>Überladen  
 Die [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Das Überladen der `<<` Operator beeinflusst das Verhalten von der `<<=` Operator. Wenn Ihr Code verwendet `<<=` für eine Klasse oder Struktur, die Überladungen `<<`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `<<=` Operator, um das Bitmuster verschoben ein `Integer` Variable links von den angegebenen Betrag und Zuweisen des Ergebnisses der Variablen.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Siehe auch

- [<<-Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
