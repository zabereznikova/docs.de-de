---
title: "&lt;&lt; Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.<<"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bit shift operators"
  - "<< operator [Visual Basic]"
  - "operator <<, Visual Basic left shift operator"
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# &lt;&lt; Operator (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Führt eine arithmetische Verschiebung nach links für ein Bitmuster aus.  
  
## Syntax  
  
```  
  
result = pattern << amount  
```  
  
## Teile  
 `result`  
 Erforderlich.  Ganzzahliger numerischer Wert.  Das Ergebnis der Verschiebung des Bitmusters.  Der Datentyp entspricht dem von `pattern`.  
  
 `pattern`  
 Erforderlich.  Ein ganzzahliger numerischer Ausdruck.  Das zu verschiebende Bitmuster.  Der Datentyp muss ein ganzzahliger Typ \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` oder `ULong`\) sein.  
  
 `amount`  
 Erforderlich.  Ein numerischer Ausdruck.  Die Anzahl der Bits, um die das Bitmuster verschoben werden soll.  Der Datentyp muss `Integer` sein oder zu `Integer` erweitert werden.  
  
## Hinweise  
 Arithmetische Verschiebungen sind nicht zyklisch, d. h., die Bits, die an einem Ende des Ergebnisses durch die Verschiebung herausfallen, werden nicht am anderen Ende wieder eingefügt.  In einer arithmetischen Verschiebung nach links werden die Bits, die über den Bereich des Ergebnisdatentyps hinaus verschoben werden, verworfen, und die Bitpositionen, die auf der rechten Seite frei werden, werden auf 0 \(null\) gesetzt.  
  
 Um eine Verschiebung um mehr Bits, als das Ergebnis aufnehmen kann, zu verhindern, maskiert Visual Basic den Wert von `amount` mit einer dem Datentyp von `pattern` entsprechenden Größenmaske.  Das binäre AND dieser Werte wird für den Verschiebungsbetrag verwendet.  Die Größenmasken lauten wie folgt:  
  
|Datentyp von `pattern`|Größenmaske \(dezimal\)|Größenmaske \(hexadezimal\)|  
|----------------------------|-----------------------------|---------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Wenn `amount` 0 \(null\) ist, ist der Wert von `result` mit dem Wert von `pattern` identisch.  Wenn `amount` negativ ist, wird der Wert als Wert ohne Vorzeichen interpretiert und mit der entsprechenden Größenmaske maskiert.  
  
 Arithmetische Verschiebungen generieren niemals Überlaufausnahmen.  
  
> [!NOTE]
>  Der Operator `<<` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall dessen neu definiertes Verhalten kennen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 Im folgenden Beispiel werden mit dem Operator `<<` arithmetische Verschiebungen nach links für ganzzahlige Werte ausgeführt.  Das Ergebnis hat immer den gleichen Datentyp wie der zu verschiebende Ausdruck.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 Das vorangehende Beispiel hat folgende Ergebnisse:  
  
-   `result1` ist 192 \(0000 0000 1100 0000\).  
  
-   `result2` ist 3072 \(0000 1100 0000 0000\).  
  
-   `result3` ist \-32768 \(1000 0000 0000 0000\).  
  
-   `result4` ist 384 \(0000 0001 1000 0000\).  
  
-   `result5` ist 0 \(15 Stellen nach links verschoben\).  
  
 Der Verschiebungsbetrag für `result4` wird als 17 AND 15 berechnet, dies ergibt 1.  
  
## Siehe auch  
 [Bit Shift Operators](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [\<\<\= Operator](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)