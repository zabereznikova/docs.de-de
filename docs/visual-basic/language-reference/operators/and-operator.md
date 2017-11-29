---
title: And-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.And
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a>And-Operator (Visual Basic)
Führt eine logische Konjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck. Für den booleschen Vergleich `result` ist die logische Konjunktion zweier `Boolean` Werte. Für bitweise Operationen `result` ist ein numerischer Wert, der die bitweise Konjunktion von zwei numerischen Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
 `expression2`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für den booleschen Vergleich `result` ist `True` Wenn und nur wenn beide `expression1` und `expression2` ergeben `True`. Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einen booleschen Vergleich zwischen den `And` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet. Die [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) führt *verkürzte*, was bedeutet, dass bei `expression1` ist `False`, klicken Sie dann `expression2` wird nicht ausgewertet.  
  
 Bei Anwendung auf numerische Werte, die `And` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.  
  
|Wenn bit `expression1` ist|Und Bit in `expression2` ist|Das entsprechende Bit im `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um genaue Ergebnisse sicherzustellen eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.  
  
 Für einen booleschen Vergleich, der Datentyp des Ergebnisses ist `Boolean`. Einen bitweisen Vergleich ist Datentyp des Ergebnisses eines numerischen Typs, der für die Datentypen der entsprechenden `expression1` und `expression2`. Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  Die `And` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `And` Operator, um eine logische Konjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` -Wert, der angibt, ob die beiden Ausdrücke sind `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 Das obige Beispiel erzeugt die Ergebnisse der `True` und `False`zugeordnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `And` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken logische Konjunktion ausgeführt. Das Bit im Ergebnismuster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt werden.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 Im vorherige Beispiel werden die Ergebnisse von 8, 2 und 0 (null) bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
