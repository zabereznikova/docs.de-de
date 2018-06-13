---
title: '&gt;&gt; Operator (Visual Basic)'
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
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605406"
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt; Operator (Visual Basic)
Führt eine arithmetische rechtsverschiebung in einem Bitmuster aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ganzzahlige numerische Wert ist. Das Ergebnis der Verschiebung des Bitmusters. Der Datentyp ist dieselbe wie `pattern`.  
  
 `pattern`  
 Erforderlich. Ganzzahlige numerische Ausdruck. Das Bitmuster verschoben werden sollen. Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck. Die Anzahl der zu verschiebenden Bitmusters Bits. Der Datentyp muss `Integer` oder erweitert werden, um `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden. Klicken Sie in eine arithmetische Verschiebung nach rechts die Bits hinter Bit ganz rechts verschoben werden verworfen, und das am weitesten links stehende (Vorzeichenbit) wird in die auf der linken Seite frei gewordene Bitpositionen übertragen. Dies bedeutet, dass bei `pattern` hat einen negativen Wert werden die frei werdenden Positionen auf einen festgelegt; andernfalls sind sie auf 0 (null) festgelegt.  
  
 Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger`, und `ULong` sind, es gibt also keine Vorzeichenbit weitergegeben. Wenn `pattern` weist eine nicht signierte Typ, die frei werdenden Positionen immer auf 0 (null) festgelegt werden.  
  
 Um zu verhindern, Verschieben von mehr Bits, als das Ergebnis aufnehmen kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die in den Datentyp der entsprechenden `pattern`. Das binäre AND dieser Werte wird für den Betrag der Verschiebung verwendet. Die Größenmasken lauten wie folgt:  
  
|Datentyp `pattern`|Größenmaske (dezimal)|Größenmaske (hexadezimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Wenn `amount` gleich NULL ist, werden den Wert der `result` ist identisch mit dem Wert des `pattern`. Wenn `amount` ist negativ ist, es als Wert ohne Vorzeichen und wird mit der entsprechenden Größe maskiert.  
  
 Arithmetische Schichten generieren nie Stapelüberlauf-Ausnahmen.  
  
## <a name="overloading"></a>Überladen  
 Die `>>` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `>>` Operator arithmetische rechtsverschiebungen für ganzzahlige Werte ausführen. Das Ergebnis hat immer den gleichen Datentyp wie der zu verschiebende Ausdruck.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 Die Ergebnisse des obigen Beispiels sind wie folgt aus:  
  
-   `result1` 2560 (0000 1010 0000 0000) ist.  
  
-   `result2` ist 160 (0000 0000 1010 0000).  
  
-   `result3` ist 2 (0000-0000-0000-0010).  
  
-   `result4` ist 640 (0000 0010 1000 0000).  
  
-   `result5` ist 0 (15 Stellen rechts verschoben).  
  
 Der Betrag der Verschiebung für `result4` wird berechnet als 18 und 15, die gleich 2 ist.  
  
 Das folgende Beispiel zeigt die arithmetische Schichten auf einen negativen Wert.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 Die Ergebnisse des obigen Beispiels sind wie folgt aus:  
  
-   `negresult1` ist-512 (1111 1110 0000 0000).  
  
-   `negresult2` ist-1 (das Vorzeichenbit wird weitergegeben).  
  
## <a name="see-also"></a>Siehe auch  
 [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [>>=-Operator](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
