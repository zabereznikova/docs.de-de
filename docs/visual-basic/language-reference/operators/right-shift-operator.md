---
title: '>> -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: b40ed11747e057d620a9a45dd1361081f38acec8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260501"
---
# <a name="-operator-visual-basic"></a>>>-Operator (Visual Basic)
Führt eine arithmetische rechtsverschiebung in einem Bitmuster aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ganzzahliger numerischer Wert. Das Ergebnis der Verschiebung des Bitmusters. Der Datentyp ist identisch mit der `pattern`.  
  
 `pattern`  
 Erforderlich. Ein ganzzahliger numerischer Ausdruck. Das Bitmuster verschoben werden sollen. Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck. Die Anzahl der Bits, um das Bitmuster verschoben werden soll. Der Datentyp muss `Integer` oder zu verbreitern `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden. In eine arithmetische Verschiebung nach rechts die Bits, die hinter der äußere rechte Bit stellt Position verschoben werden verworfen und das Bit ganz links (Anmeldung) wird in der Bitpositionen, die auf der linken Seite weitergegeben. Dies bedeutet, dass bei `pattern` hat einen negativen Wert an, die frei werdenden Positionen auf 1 gesetzt werden; andernfalls werden sie auf 0 (null) festgelegt.  
  
 Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger`, und `ULong` ohne Vorzeichen sind, es gibt also keine Vorzeichenbit weitergegeben werden. Wenn `pattern` ist ein vorzeichenloser Typ, werden die frei werdenden Stellen immer 0 (null) festgelegt.  
  
 Um zu verhindern, verschieben, um mehr Bits, die als Ergebnis werden kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die in den Datentyp der entsprechenden `pattern`. Das binäre AND der folgenden Werte wird für den Betrag der Verschiebung verwendet. Die Größenmasken lauten wie folgt aus:  
  
|Datentyp `pattern`|Size-Maske (dezimal)|Size-Maske (hexadezimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Wenn `amount` NULL ist, den Wert der `result` ist identisch mit dem Wert des `pattern`. Wenn `amount` ist negativ, dabei handelt es sich als ein Wert ohne Vorzeichen mit der entsprechenden Größe maskiert.  
  
 Arithmetische Schichten generieren keine Stapelüberlauf-Ausnahmen.  
  
## <a name="overloading"></a>Überladen  
 Die `>>` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `>>` Operator zum Ausführen von arithmetischer rechtsverschiebungen für ganzzahlige Werte. Das Ergebnis hat immer den gleichen Datentyp wie der Ausdruck, der verschoben werden.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:  
  
-   `result1` 2560 (0000 1010-0000-0000) ist.  
  
-   `result2` ist 160 (0000 0000 1010 0000).  
  
-   `result3` ist 2 (0000-0000-0000-0010).  
  
-   `result4` ist 640 (0000 0010 1000 0000).  
  
-   `result5` ist 0 (15 Stellen nach rechts verschoben).  
  
 Der Betrag der Verschiebung für `result4` wird berechnet als 18 und 15, die gleich 2 ist.  
  
 Das folgende Beispiel zeigt die arithmetische Schichten auf einen negativen Wert.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:  
  
-   `negresult1` ist-512 (1111 1110 0000-0000).  
  
-   `negresult2` ist-1 (das signierte Bit wird weitergegeben).  
  
## <a name="see-also"></a>Siehe auch
- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [>>=-Operator](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
