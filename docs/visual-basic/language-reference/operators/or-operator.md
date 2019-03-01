---
title: Or-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: cbfc94ad70695e9a785375f2460f9f9d8f3a20c5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977538"
---
# <a name="or-operator-visual-basic"></a>Or-Operator (Visual Basic)
Führt eine logische Disjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Disjunktion zweier numerischer Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck. Für `Boolean` hingegen `result` ist die einschließende logische Disjunktion zweier `Boolean` Werte. Für bitweise Operationen: `result` ist ein numerischer Wert, der die inklusive bitweise Disjunktion von zwei numerischen Bitmustern darstellt.  
  
 `expression1`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Alle `Boolean` oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für `Boolean` hingegen `result` ist `False` Wenn und nur wenn beide `expression1` und `expression2` ergeben `False`. In der folgende Tabelle wird veranschaulicht, wie `result` bestimmt ist.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einer `Boolean` Vergleich der `Or` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet. Die [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) führt *kurzschließen*, was bedeutet, dass bei `expression1` ist `True`, klicken Sie dann `expression2` wird nicht ausgewertet.  
  
 Für bitweise Operationen: die `Or` Operator führt einen bitweisen Vergleich gleich positionierter Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle.  
  
|Wenn bit `expression1` ist|Ist und Bit in `expression2` ist|Das entsprechende Bit im `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf eine niedrigere Rangfolge als der anderen arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern, um die genaue Ausführung sicherzustellen eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.  
  
 Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses wird die `Boolean`. Einen bitweisen Vergleich, der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`. Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Überladen  
 Die `Or` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Or` Operator, um eine einschließende logische Disjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist eine `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke `True`.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 Im vorherige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False`bzw.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Or` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken einschließende logischen Disjunktion ausgeführt. Das Bit im Ergebnismuster wird festgelegt, wenn eine der entsprechenden Bits in den Operanden auf 1 festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 Im vorherige Beispiel werden die Ergebnisse von 10, 14 und 14, bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch
- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
