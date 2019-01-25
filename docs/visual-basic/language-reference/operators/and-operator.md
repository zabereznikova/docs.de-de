---
title: And-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 2cdc272c07f3b30f61716f0c5ae72f0655c3f46b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597319"
---
# <a name="and-operator-visual-basic"></a>And-Operator (Visual Basic)
Führt eine logische Konjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck. Boolescher Vergleich `result` ist die logische Konjunktion zweier `Boolean` Werte. Für bitweise Operationen: `result` ist ein numerischer Wert, der die bitweise Konjunktion von zwei numerischen Bitmustern darstellt.  
  
 `expression1`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Boolescher Vergleich `result` ist `True` Wenn und nur wenn beide `expression1` und `expression2` ergeben `True`. In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einen booleschen Vergleich zwischen den `And` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet. Die [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) führt *kurzschließen*, was bedeutet, dass bei `expression1` ist `False`, klicken Sie dann `expression2` wird nicht ausgewertet.  
  
 Bei Anwendung auf numerische Werte, die `And` Operator führt einen bitweisen Vergleich gleich positionierter Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle.  
  
|Wenn bit `expression1` ist|Ist und Bit in `expression2` ist|Das entsprechende Bit im `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf eine niedrigere Rangfolge als der anderen arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern einschließen, um genaue Ergebnisse zu gewährleisten eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.  
  
 Für einen booleschen Vergleich zwischen der Datentyp des Ergebnisses ist `Boolean`. Einen bitweisen Vergleich, der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`. Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  Die `And` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `And` Operator, um eine logische Konjunktion zweier Ausdrücke ausgeführt. Das Ergebnis ist eine `Boolean` -Wert, der angibt, ob beide Ausdrücke sind `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 Im vorherige Beispiel erzeugt die Ergebnisse der `True` und `False`bzw.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `And` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken logischen Konjunktion ausgeführt. Das Bit im Ergebnismuster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt wurden.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 Im vorherige Beispiel werden die Ergebnisse von 8, 2 und 0 (null) bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch
- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
