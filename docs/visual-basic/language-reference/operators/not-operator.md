---
title: Not-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824212"
---
# <a name="not-operator-visual-basic"></a>Not-Operator (Visual Basic)
Führt eine logische Negation für einen `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck.  
  
 `expression`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für `Boolean` Ausdrücke, in der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.  
  
|Wenn `expression` ist|Der Wert des `result` ist|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Bei numerischen Ausdrücken der `Not` Operator kehrt die Bitwerte ein beliebiger numerischer Ausdruck, und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle.  
  
|Wenn bit `expression` ist|Das entsprechende Bit im `result` ist|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf eine niedrigere Rangfolge als der anderen arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern, um die genaue Ausführung sicherzustellen eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Der Datentyp des Ergebnisses einer booleschen Negation ist `Boolean`. Der Ergebnistyp für die Daten für die eine bitweise Negation, ist identisch mit der `expression`. Allerdings ist der Ausdruck `Decimal`, das Ergebnis ist `Long`.  
  
## <a name="overloading"></a>Überladen  
 Die `Not` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn der Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Not` Operator, um die logischen Negation für Ausführen einer `Boolean` Ausdruck. Das Ergebnis ist eine `Boolean` Wert, der die Umkehrung des Werts des Ausdrucks darstellt.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 Im vorherige Beispiel erzeugt die Ergebnisse der `False` und `True`bzw.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Not` Operator, um die logische Negation der einzelnen Bits eines numerischen Ausdrucks ausgeführt. Das Bit im Ergebnismuster ist das Gegenteil von das entsprechende Bit im Operandenmuster, einschließlich des Vorzeichenbits fest.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 Im vorherige Beispiel werden die Ergebnisse der – 11 – 9 und –7, bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
