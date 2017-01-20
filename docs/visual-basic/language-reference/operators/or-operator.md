---
title: "Or-Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Or"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Or-Operator"
  - "bitweise Operatoren [Visual Basic]"
  - "Inklusiver Or-Operator"
  - "bitweise Operatoren, OR-operator"
  - "Or-Schlüsselwort"
  - "Operatoren [Visual Basic], inklusive oder"
  - "Operatoren [Visual Basic], Disjunktion"
  - "Bitweiser Vergleich"
  - "Logische Disjunktion"
  - "Disjunktionsoperator"
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Or-Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Führt eine logische Disjunktion für zwei `Boolean` Ausdrücke oder eine bitweise Disjunktion für zwei numerische Ausdrücke.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck. Für `Boolean` Vergleich `result` ist die inklusive logische Disjunktion zweier `Boolean` Werte. Bei bitweisen Operationen `result` einen numerischen Wert, der die inklusive bitweise Disjunktion von zwei numerischen Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
 `expression2`  
 Erforderlich. Alle `Boolean` oder numerische Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Für `Boolean` Vergleich `result` ist `False` Wenn und nur wenn beide `expression1` und `expression2` ergeben `False`. Die folgende Tabelle verdeutlicht, wie `result` bestimmt ist.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert des `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  In einem `Boolean` Vergleich der `Or` Operator ergibt immer beide Ausdrücke aus, wobei u. u. Prozeduraufrufe. Die [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) führt *verkürzte*, was bedeutet, dass bei `expression1` ist `True`, dann `expression2` wird nicht ausgewertet.  
  
 Bei bitweisen Operationen der `Or` Operator führt einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken durch und legt das entsprechende Bit im `result` gemäß der folgenden Tabelle.  
  
|Wenn bit im `expression1` ist|Und Bit in `expression2` ist|Das Bit im `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Da die logischen und bitweisen Operatoren einen niedrigeren Rang als andere arithmetischen und relationalen Operatoren haben, sollten alle bitweisen Operationen in Klammern, um genaue Ausführung gewährleistet eingeschlossen werden.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden eines bestehen `Boolean` Ausdruck und einem numerischen Ausdruck konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation.  
  
 Für eine `Boolean` Vergleich, der Datentyp des Ergebnisses ist `Boolean`. Einen bitweisen Vergleich ist der resultierende Datentyp eines numerischen Typs für die Datentypen der `expression1` und `expression2`. Siehe die Tabelle "Relationale und bitweise Vergleiche" in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Überladen  
 Die `Or` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur aufweist. Wenn Ihr Code auf eine solche Klasse oder Struktur dieser Operator verwendet wird, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Or` Operator, um eine inklusive logische Disjunktion zweier Ausdrücke ausgeführt. Das Ergebnis ist ein `Boolean` Wert, der darstellt, ob einer der beiden Ausdrücke `True`.  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 Im vorherigen Beispiel ergibt der `True`, `True`, und `False`, bzw..  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Or` Operator inklusive logische Disjunktion der einzelnen Bits von zwei numerischen Ausdrücken ausgeführt. Das Bit im Ergebnismuster wird festgelegt, wenn eine der entsprechenden Bits in den Operanden auf 1 festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 Im vorherigen Beispiel werden die Ergebnisse 10, 14 und 14 bzw. erzeugt.  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operatorrangfolge in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)   
 [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)