---
title: <<-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: e11dbc453934f1aac4a8092cdc6539ec11f0cc21
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663184"
---
# <a name="-operator-visual-basic"></a>\<\< -Operator (Visual Basic)
Führt eine arithmetische linksverschiebung in einem Bitmuster aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ganzzahliger numerischer Wert. Das Ergebnis der Verschiebung des Bitmusters. Der Datentyp ist identisch mit der `pattern`.  
  
 `pattern`  
 Erforderlich. Ein ganzzahliger numerischer Ausdruck. Das Bitmuster verschoben werden sollen. Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck. Die Anzahl der Bits, um das Bitmuster verschoben werden soll. Der Datentyp muss `Integer` oder zu verbreitern `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden. In eine arithmetische Verschiebung nach links die Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite werden auf 0 (null) festgelegt.  
  
 Um zu verhindern, dass eine Verschiebung um mehr Bits, die als Ergebnis werden kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die den Datentyp der entspricht `pattern`. Das binäre AND der folgenden Werte wird für den Betrag der Verschiebung verwendet. Die Größenmasken lauten wie folgt aus:  
  
|Datentyp `pattern`|Size-Maske (dezimal)|Size-Maske (hexadezimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Wenn `amount` NULL ist, den Wert der `result` ist identisch mit dem Wert des `pattern`. Wenn `amount` ist negativ, dabei handelt es sich als ein Wert ohne Vorzeichen mit der entsprechenden Größe maskiert.  
  
 Arithmetische Schichten generieren keine Stapelüberlauf-Ausnahmen.  
  
> [!NOTE]
>  Die `<<` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `<<` Operator, um die Durchführung von Berechnungen nach links verschiebt für ganzzahlige Werte. Das Ergebnis hat immer den gleichen Datentyp wie der Ausdruck, der verschoben werden.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:  
  
- `result1` ist Sie 192 (0000 0000 1100 0000).  
  
- `result2` 3072 (1100-0000-0000 0000) ist.  
  
- `result3` ist-32768 (1000-0000-0000-0000).  
  
- `result4` ist 384 (0000 0001 1000 0000).  
  
- `result5` ist 0 (15 Stellen links verschoben).  
  
 Der Betrag der Verschiebung für `result4` wird berechnet als 17 und 15, die gleich 1 ist.  
  
## <a name="see-also"></a>Siehe auch

- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<<=-Operator](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
