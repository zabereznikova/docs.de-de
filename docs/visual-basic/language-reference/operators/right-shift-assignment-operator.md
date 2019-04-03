---
title: '>>=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 1076ce62077391f2c88ebdd621d1dbd6fb40d647
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838962"
---
# <a name="-operator-visual-basic"></a>>> =-Operator (Visual Basic)
Führt eine arithmetische rechtsverschiebung den Wert einer Variable oder eine Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.  
  
## <a name="syntax"></a>Syntax  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Variable oder eine Eigenschaft, ein ganzzahliger Typ (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck eines Datentyps, die erweitert werden kann, `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite von der `>>=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Die `>>=` -Operator führt eine arithmetische rechtsverschiebung zuerst auf dem Wert der Variablen oder Eigenschaft. Der Operator weist das Ergebnis des Vorgangs klicken Sie dann die Variable oder Eigenschaft an.  
  
 Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden. In eine arithmetische Verschiebung nach rechts die Bits, die hinter der äußere rechte Bit stellt Position verschoben werden verworfen und das Bit ganz links in der Bitpositionen, die auf der linken Seite weitergegeben wird. Dies bedeutet, dass bei `variableorproperty` hat einen negativen Wert an, die frei werdenden Positionen auf 1 gesetzt werden. Wenn `variableorproperty` positiv ist, oder wenn der Datentyp ein Typ ohne Vorzeichen ist, werden die frei werdenden Stellen 0 (null) festgelegt.  
  
## <a name="overloading"></a>Überladen  
 Die [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Das Überladen der `>>` Operator beeinflusst das Verhalten von der `>>=` Operator. Wenn Ihr Code verwendet `>>=` für eine Klasse oder Struktur, die Überladungen `>>`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `>>=` Operator, um das Bitmuster verschoben ein `Integer` Variable, um den angegebenen Betrag und Zuweisen des Ergebnisses, auf die Variable nach rechts.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [>>-Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
