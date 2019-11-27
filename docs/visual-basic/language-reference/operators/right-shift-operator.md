---
title: '>> Operator'
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
ms.openlocfilehash: cabf8c569435cc0fc98282f5e8f5fd410e6708dc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347827"
---
# <a name="-operator-visual-basic"></a>> > Operator (Visual Basic)
Führt eine arithmetische Rechtsverschiebung in einem Bitmuster aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = pattern >> amount  
```  
  
## <a name="parts"></a>-Komponenten  
 `result`  
 Erforderlich Ganzzahliger numerischer Wert. Das Ergebnis der Verschiebung des Bitmusters. Der-Datentyp entspricht dem-Wert `pattern`.  
  
 `pattern`  
 Erforderlich Ganzzahliger numerischer Ausdruck. Das Bitmuster, das verschoben werden soll. Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`oder `ULong`).  
  
 `amount`  
 Erforderlich Numerischer Ausdruck. Die Anzahl der Bits, um die das Bitmuster verschoben werden soll. Der Datentyp muss `Integer` oder auf `Integer`erweitert werden.  
  
## <a name="remarks"></a>Hinweise  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. In einer arithmetischen rechten Schicht werden die Bits, die über die bitmost-Bitposition hinaus verschoben werden, verworfen, und das äußteste äußteste Bit (Vorzeichen) wird an die auf der linken Seite freigegebenen Bitpositionen weitergegeben. Dies bedeutet, dass, wenn `pattern` einen negativen Wert hat, die frei gewordenen Positionen auf 1 festgelegt sind. Andernfalls werden Sie auf 0 (null) festgelegt.  
  
 Beachten Sie, dass die Datentypen `Byte`, `UShort`, `UInteger`und `ULong` nicht signiert sind, sodass kein Signier Bit zur Weitergabe vorhanden ist. Wenn `pattern` einen beliebigen Typ ohne Vorzeichen hat, werden die frei gewordenen Positionen immer auf 0 (null) festgelegt.  
  
 Um zu verhindern, dass mehr Bits verschoben werden, als das Ergebnis enthalten kann, maskiert Visual Basic den Wert `amount` mit einer Größen Maske, die dem Datentyp von `pattern`entspricht. Die Binärdatei und diese Werte werden für die UMSCHALT Menge verwendet. Die Größen Masken lauten wie folgt:  
  
|Datentyp von `pattern`|Größen Maske (dezimal)|Größen Maske (hexadezimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Wenn `amount` 0 (null) ist, ist der Wert von `result` identisch mit dem Wert von `pattern`. Wenn `amount` negativ ist, wird es als nicht signierter Wert angenommen und mit der entsprechenden Größen Maske maskiert.  
  
 Arithmetische Verschiebungen generieren niemals Überlauf Ausnahmen.  
  
## <a name="overloading"></a>Überladen  
 Der `>>`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `>>`-Operator verwendet, um arithmetische Rechte Verschiebungen für ganzzahlige Werte auszuführen. Das Ergebnis weist immer den gleichen Datentyp wie der zu Verschiebe Ausdruck auf.  
  
 [!code-vb[VbVbalrOperators#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#14)]  
  
 Die Ergebnisse des vorherigen Beispiels lauten wie folgt:  
  
- `result1` ist 2560 (0000 1010 0000 0000).  
  
- `result2` ist 160 (0000 0000 1010 0000).  
  
- `result3` ist 2 (0000 0000 0000 0010).  
  
- `result4` ist 640 (0000 0010 1000 0000).  
  
- `result5` ist 0 (verschiebt 15 Stellen nach rechts).  
  
 Der Verschiebungs Betrag für `result4` wird als 18 und 15 berechnet, was dem Wert 2 entspricht.  
  
 Das folgende Beispiel zeigt arithmetische Verschiebungen bei einem negativen Wert.  
  
 [!code-vb[VbVbalrOperators#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#55)]  
  
 Die Ergebnisse des vorherigen Beispiels lauten wie folgt:  
  
- `negresult1` ist-512 (1111 1110 0000 0000).  
  
- `negresult2` ist-1 (das Signier Bit wird weitergegeben).  
  
## <a name="see-also"></a>Siehe auch

- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [>>=-Operator](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
