---
title: '&lt;&lt; Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: bdec015309526aeac2499bc7b459b6ccab6f1e4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt; Operator (Visual Basic)
Führt eine arithmetische linksverschiebung in einem Bitmuster aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ganzzahlige numerische Wert ist. Das Ergebnis der Verschiebung des Bitmusters. Der Datentyp ist dieselbe wie `pattern`.  
  
 `pattern`  
 Erforderlich. Ganzzahlige numerische Ausdruck. Das Bitmuster verschoben werden sollen. Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).  
  
 `amount`  
 Erforderlich. Numerischer Ausdruck. Die Anzahl der zu verschiebenden Bitmusters Bits. Der Datentyp muss `Integer` oder erweitert werden, um `Integer`.  
  
## <a name="remarks"></a>Hinweise  
 Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden. In eine arithmetische linksverschiebung der Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite ist auf 0 festgelegt.  
  
 Um zu verhindern, dass eine Verschiebung um mehr Bits, als das Ergebnis aufnehmen kann, maskiert Visual Basic den Wert der `amount` mit einer Größenmaske, die den Datentyp der entspricht `pattern`. Das binäre AND dieser Werte wird für den Betrag der Verschiebung verwendet. Die Größenmasken lauten wie folgt:  
  
|Datentyp `pattern`|Größenmaske (dezimal)|Größenmaske (hexadezimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&AMP; H00000007|  
|`Short`, `UShort`|15|&AMP; H0000000F|  
|`Integer`, `UInteger`|31|&AMP; H0000001F|  
|`Long`, `ULong`|63|&AMP; H0000003F|  
  
 Wenn `amount` gleich NULL ist, werden den Wert der `result` ist identisch mit dem Wert des `pattern`. Wenn `amount` ist negativ ist, es als Wert ohne Vorzeichen und wird mit der entsprechenden Größe maskiert.  
  
 Arithmetische Schichten generieren nie Stapelüberlauf-Ausnahmen.  
  
> [!NOTE]
>  Die `<<` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `<<` Operator, um die Durchführung von Berechnungen Schichten auf ganzzahlige Werte nach links. Das Ergebnis hat immer den gleichen Datentyp wie der zu verschiebende Ausdruck.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 Die Ergebnisse des vorherigen Beispiels sind wie folgt aus:  
  
-   `result1` ist 192 (0000 0000 1100 0000).  
  
-   `result2` 3072 (0000 1100 0000 0000) ist.  
  
-   `result3` ist zwischen-32768 (1000 0000-0000-0000).  
  
-   `result4` ist 384 (0000 0001 1000 0000).  
  
-   `result5` ist 0 (15 Stellen links verschoben).  
  
 Der Betrag der Verschiebung für `result4` wird berechnet als 17 und 15, die gleich 1 ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<<=-Operator](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
