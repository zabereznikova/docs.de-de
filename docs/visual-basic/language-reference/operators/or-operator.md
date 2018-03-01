---
title: Or-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4c9429eb2bdeb86bfa73786433231fdc22a230d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="or-operator-visual-basic"></a>Or-Operator (Visual Basic)
Führt eine logische Disjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Disjunktion zweier numerischer Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck. Für `Boolean` Vergleich `result` ist die inklusive logische Disjunktion zweier `Boolean` Werte. Für bitweise Operationen `result` ist ein numerischer Wert, der die inklusive bitweise Disjunktion von zwei numerischen Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
 `expression2`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für `Boolean` Vergleich `result` ist `False` Wenn und nur wenn beide `expression1` und `expression2` ergeben `False`. Die folgende Tabelle veranschaulicht wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einer `Boolean` Vergleich der `Or` Operator immer beide Ausdrücke, die Prozeduraufrufe enthalten, werden ausgewertet. Die [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) führt *verkürzte*, was bedeutet, dass bei `expression1` ist `True`, klicken Sie dann `expression2` wird nicht ausgewertet.  
  
 Für bitweise Operationen der `Or` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle.  
  
|Wenn bit `expression1` ist|Und Bit in `expression2` ist|Das entsprechende Bit im `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren auf einen geringere Rangfolge als der andere arithmetischen und relationalen Operatoren verfügen, sollten alle bitweisen Operationen in Klammern einschließen, um die genaue Ausführung gewährleistet eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic die `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.  
  
 Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses ist `Boolean`. Einen bitweisen Vergleich ist Datentyp des Ergebnisses eines numerischen Typs, der für die Datentypen der entsprechenden `expression1` und `expression2`. Siehe die Tabelle "Relationale und bitweise Vergleiche" im [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Überladen  
 Die `Or` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Or` Operator, um eine inklusive logische Disjunktion zweier Ausdrücke ausgeführt. Das Ergebnis ist ein `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke `True`.  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 Das obige Beispiel erzeugt die Ergebnisse der `True`, `True`, und `False`zugeordnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Or` Operator, um die einzelnen Bits von zwei numerischen Ausdrücken inklusiven logische Disjunktion ausgeführt. Das Bit im Ergebnismuster wird festgelegt, wenn entweder der entsprechenden Bits in den Operanden auf 1 festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 Im vorherige Beispiel werden die Ergebnisse von 10, 14 und 14, bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)  
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
