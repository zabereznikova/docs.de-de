---
title: "&gt;&gt; Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.>>"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operator>>"
  - ">> operator [Visual Basic]"
  - "bit shift operators"
  - "operator >>"
  - "right shift operators"
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# &gt;&gt; Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Führt eine arithmetische Verschiebung nach rechts für ein Bitmuster aus.  
  
## Syntax  
  
```  
  
result = pattern >> amount  
```  
  
## Teile  
 `result`  
 Erforderlich.  Ganzzahliger numerischer Wert.  Das Ergebnis der Verschiebung des Bitmusters.  Der Datentyp entspricht dem von `pattern`.  
  
 `pattern`  
 Erforderlich.  Ein ganzzahliger numerischer Ausdruck.  Das zu verschiebende Bitmuster.  Der Datentyp muss ein ganzzahliger Typ \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` oder `ULong`\) sein.  
  
 `amount`  
 Erforderlich.  Ein numerischer Ausdruck.  Die Anzahl der Bits, um die das Bitmuster verschoben werden soll.  Der Datentyp muss `Integer` sein oder zu `Integer` erweitert werden.  
  
## Hinweise  
 Arithmetische Verschiebungen sind nicht zyklisch, d. h., die Bits, die an einem Ende des Ergebnisses durch die Verschiebung herausfallen, werden nicht am anderen Ende wieder eingefügt.  Bei einer arithmetischen Verschiebung nach rechts werden die Bits, die über die Bitposition ganz rechts hinaus verschoben werden, verworfen, und das Bit ganz links \(Vorzeichenbit\) wird in die Bitpositionen übertragen, die links frei werden.  Das bedeutet, dass die frei werdenden Positionen auf 1 gesetzt werden, wenn `pattern` einen negativen Wert hat. Andernfalls werden sie auf 0 \(null\) gesetzt.  
  
 Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger` und `ULong` kein Vorzeichen enthalten und daher kein Vorzeichenbit weitergegeben werden muss.  Wenn `pattern` ein vorzeichenloser Typ ist, werden die frei werdenden Positionen immer auf 0 \(null\) gesetzt.  
  
 Um eine Verschiebung um mehr Bits, als das Ergebnis aufnehmen kann, zu verhindern, maskiert Visual Basic den Wert von `amount` mit einer dem Datentyp von `pattern` entsprechenden Größenmaske.  Das binäre AND dieser Werte wird für den Verschiebungsbetrag verwendet.  Die Größenmasken lauten wie folgt:  
  
|Datentyp von `pattern`|Größenmaske \(dezimal\)|Größenmaske \(hexadezimal\)|  
|----------------------------|-----------------------------|---------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Wenn `amount` 0 \(null\) ist, ist der Wert von `result` mit dem Wert von `pattern` identisch.  Wenn `amount` negativ ist, wird der Wert als Wert ohne Vorzeichen interpretiert und mit der entsprechenden Größenmaske maskiert.  
  
 Arithmetische Verschiebungen generieren niemals Überlaufausnahmen.  
  
## Überladen  
 Der Operator `>>` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel werden mit dem Operator `>>` arithmetische Verschiebungen nach rechts für ganzzahlige Werte ausgeführt.  Das Ergebnis hat immer den gleichen Datentyp wie der zu verschiebende Ausdruck.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/right-shift-operator_1.vb)]  
  
 Das vorangehende Beispiel hat folgende Ergebnisse:  
  
-   `result1` ist 2560 \(0000 1010 0000 0000\).  
  
-   `result2` ist 160 \(0000 0000 1010 0000\).  
  
-   `result3` ist 2 \(0000 0000 0000 0010\).  
  
-   `result4` ist 640 \(0000 0010 1000 0000\).  
  
-   `result5` ist 0 \(15 Stellen nach rechts verschoben\).  
  
 Der Verschiebungsbetrag für `result4` wird als 18 AND 15 berechnet, dies ergibt 2.  
  
 Im folgenden Beispiel werden arithmetische Verschiebungen in einem negativen Wert veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/right-shift-operator_2.vb)]  
  
 Das vorangehende Beispiel hat folgende Ergebnisse:  
  
-   `negresult1` ist \-512 \(1111 1110 0000 0000\).  
  
-   `negresult2` ist \-1 \(das Vorzeichenbit wird weitergegeben\).  
  
## Siehe auch  
 [Bit Shift Operators](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [\>\>\= Operator](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)