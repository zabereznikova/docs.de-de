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
ms.openlocfilehash: 332cee57c8d25d7f51737e01e70ba515d50bd6e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604392"
---
# <a name="not-operator-visual-basic"></a>Not-Operator (Visual Basic)
Führt eine logische Negation für einen `Boolean` Ausdruck oder eine bitweise Negation eines numerischen Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
 `expression`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für `Boolean` Ausdrücke, die in der folgenden Tabelle veranschaulicht wie `result` bestimmt wird.  
  
|Wenn `expression` ist|Der Wert des `result` ist|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Bei numerischen Ausdrücken die `Not` Operator Invertiert die Bitwerte ein beliebiger numerischer Ausdruck, und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.  
  
|Wenn bit `expression` ist|Das entsprechende Bit im `result` ist|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Bei einer booleschen Negation der Datentyp des Ergebnisses ist `Boolean`. Datentyp des Ergebnisses für eine bitweise Negation ist identisch mit der `expression`. Allerdings ist der Ausdruck `Decimal`, das Ergebnis ist `Long`.  
  
## <a name="overloading"></a>Überladen  
 Die `Not` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn Operanden den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Not` Operator auszuführenden logischen Negation für einen `Boolean` Ausdruck. Das Ergebnis ist ein `Boolean` Wert, der das Gegenteil des Werts des Ausdrucks darstellt.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 Das obige Beispiel erzeugt die Ergebnisse der `False` und `True`zugeordnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Not` Operator, um die logische Negation von den einzelnen Bit eines numerischen Ausdrucks ausgeführt. Das Bit im Ergebnismuster ist das Gegenteil des entsprechenden Bits in den Operandenmuster, einschließlich des Vorzeichenbits fest.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 Im vorherige Beispiel werden die Ergebnisse von – 11 – 9 und –7, bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
