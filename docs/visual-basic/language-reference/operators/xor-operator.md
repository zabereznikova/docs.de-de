---
title: Xor-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: 34d317da5d85127e371c2df7229e0f0873972f50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604795"
---
# <a name="xor-operator-visual-basic"></a>Xor-Operator (Visual Basic)
Führt einen logischen Ausschluss für zwei `Boolean` Ausdrücke oder einen bitweisen Ausschluss zweier numerischer Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerische Variable. Für den booleschen Vergleich `result` ist die logische Exklusion (exklusive logische Disjunktion) zweier `Boolean` Werte. Für bitweise Operationen `result` ist ein numerischer Wert, der die bitweisen Ausschluss (exklusive bitweise Disjunktion) von zwei numerischen Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
 `expression2`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für den booleschen Vergleich `result` ist `True` nur, wenn genau einem der `expression1` und `expression2` ergibt `True`. D. h. wenn `expression1` und `expression2` auswerten entgegengesetzte `Boolean` Werte. Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einen booleschen Vergleich zwischen den `Xor` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet. Es gibt keine verkürzte Entsprechung zu `Xor`, da das Ergebnis immer beide Operanden abhängig. Für *verkürzte* logische Operatoren finden Sie unter [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) und [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Für bitweise Operationen der `Xor` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.  
  
|Wenn bit `expression1` ist|Und Bit in `expression2` ist|Das entsprechende Bit im `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.  
  
 Z. B. 5 `Xor` 3 ist 6. Um festzustellen, warum dies ist deshalb 5 und 3 in ihre binären Darstellungen, 101 und 011 konvertieren. Ermitteln, dass 101 Xor 011 110, ist die binäre Darstellung der Dezimalzahl 6 mithilfe der vorherigen Tabelle.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.  
  
 Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses ist `Boolean`. Einen bitweisen Vergleich ist Datentyp des Ergebnisses eines numerischen Typs, der für die Datentypen der entsprechenden `expression1` und `expression2`. Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Überladen  
 Die `Xor` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Xor` Operator zwei Ausdrücke logischen Ausschluss (exklusive logische Disjunktion) ausgeführt. Das Ergebnis ist ein `Boolean` -Wert, der angibt, ob genau einer der Ausdrücke ist `True`.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 Im vorherige Beispiel erzeugt die Ergebnisse der `False`, `True`, und `False`zugeordnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Xor` Operator logischen Ausschluss (exklusive logische Disjunktion) der einzelnen Bits von zwei numerischen Ausdrücken ausgeführt. Das Bit im Ergebnismuster wird festgelegt, wenn nur eines der entsprechenden Bits in den Operanden auf 1 festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 Im vorherige Beispiel werden die Ergebnisse von 2, 12 und 14, bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
