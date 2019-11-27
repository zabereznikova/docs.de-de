---
title: <<-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: 327d0e5cbd1ebcc43bd47fb068f4513940c2165a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350981"
---
# <a name="-operator-visual-basic"></a>\<\< Operator (Visual Basic)
Führt eine arithmetische linke Verschiebung in einem Bitmuster aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = pattern << amount  
```  
  
## <a name="parts"></a>-Komponenten  
 `result`  
 Erforderlich Ganzzahliger numerischer Wert. Das Ergebnis der Verschiebung des Bitmusters. Der-Datentyp entspricht dem-Wert `pattern`.  
  
 `pattern`  
 Erforderlich Ganzzahliger numerischer Ausdruck. Das Bitmuster, das verschoben werden soll. Der Datentyp muss ein ganzzahliger Typ sein (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`oder `ULong`).  
  
 `amount`  
 Erforderlich Numerischer Ausdruck. Die Anzahl der Bits, um die das Bitmuster verschoben werden soll. Der Datentyp muss `Integer` oder auf `Integer`erweitert werden.  
  
## <a name="remarks"></a>Hinweise  
 Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden. In einer arithmetischen linken Schicht werden die Bits, die nach dem Bereich des Ergebnis Datentyps verschoben werden, verworfen, und die auf der rechten Seite frei gewordenen Bitpositionen werden auf 0 (null) festgelegt.  
  
 Um eine Verschiebung um mehr Bits zu verhindern, als das Ergebnis enthalten kann, Visual Basic den Wert `amount` mit einer Größen Maske, die dem Datentyp von `pattern`entspricht. Die Binärdatei und diese Werte werden für die UMSCHALT Menge verwendet. Die Größen Masken lauten wie folgt:  
  
|Datentyp von `pattern`|Größen Maske (dezimal)|Größen Maske (hexadezimal)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Wenn `amount` 0 (null) ist, ist der Wert von `result` identisch mit dem Wert von `pattern`. Wenn `amount` negativ ist, wird es als nicht signierter Wert angenommen und mit der entsprechenden Größen Maske maskiert.  
  
 Arithmetische Verschiebungen generieren niemals Überlauf Ausnahmen.  
  
> [!NOTE]
> Der `<<`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `<<`-Operator verwendet, um die arithmetischen linken Verschiebungen für ganzzahlige Werte auszuführen. Das Ergebnis weist immer den gleichen Datentyp wie der zu Verschiebe Ausdruck auf.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 Die Ergebnisse des vorherigen Beispiels lauten wie folgt:  
  
- `result1` ist 192 (0000 0000 1100 0000).  
  
- `result2` ist 3072 (0000 1100 0000 0000).  
  
- `result3` ist-32768 (1000 0000 0000 0000).  
  
- `result4` ist 384 (0000 0001 1000 0000).  
  
- `result5` ist 0 (in 15 Stellen nach links verschoben).  
  
 Der Verschiebungs Betrag für `result4` wird als 17 und 15 berechnet, was dem Wert 1 entspricht.  
  
## <a name="see-also"></a>Siehe auch

- [Bitverschiebungsoperatoren](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<<=-Operator](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
