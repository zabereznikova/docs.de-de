---
title: And-Operator
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
ms.openlocfilehash: c2b135d27e14816c011a4f70793543aa835d960a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371946"
---
# <a name="and-operator-visual-basic"></a>And-Operator (Visual Basic)
Führt eine logische Konjunktion zweier `Boolean` Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Bestandteile  
 `result`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck. Bei einem booleschen Vergleich `result` ist die logische Verknüpfung von zwei `Boolean` Werten. Für bitweise Vorgänge `result` ist ein numerischer Wert, der die bitweise Konjunktion zweier numerischer Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  
 Bei einem booleschen Vergleich `result` ist `True` nur dann, wenn sowohl `expression1` als auch als `expression2` ausgewertet werden `True` . In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` gleich |Und `expression2` ist|Der Wert von `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> Bei einem booleschen Vergleich wertet der `And` Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können. Der [andwas-Operator](andalso-operator.md) führt *Kurzschluss*aus, was bedeutet, dass `expression1` , wenn ist `False` , `expression2` nicht ausgewertet wird.  
  
 Beim Anwenden auf numerische Werte führt der `And` Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken aus und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.  
  
|Wenn `expression1` Bit in|Und Bit in `expression2` ist|Das Bit in `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um genaue Ergebnisse sicherzustellen.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden aus einem `Boolean` Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False` ) und führt eine bitweise Operation aus.  
  
 Bei einem booleschen Vergleich ist der Datentyp des Ergebnisses `Boolean` . Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und geeignet ist `expression2` . Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](data-types-of-operator-results.md).  
  
> [!NOTE]
> Der `And` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der- `And` Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob beide Ausdrücke sind `True` .  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 Das vorherige Beispiel erzeugt die Ergebnisse von `True` und `False` .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der- `And` Operator verwendet, um eine logische Konjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen. Das Bit im Ergebnis Muster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt sind.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 Im vorherigen Beispiel werden die Ergebnisse von 8, 2 bzw. 0 erzeugt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Logische/bitweise Operatoren (Visual Basic)](logical-bitwise-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [AndAlso-Operator](andalso-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
