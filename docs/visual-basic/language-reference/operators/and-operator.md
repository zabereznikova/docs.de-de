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
ms.openlocfilehash: bd6ebbf5f53a7cf187b5d8ce7630080d44d46df2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591620"
---
# <a name="and-operator-visual-basic"></a>And-Operator (Visual Basic)
Führt eine logische Konjunktion zweier `Boolean`-Ausdrücke oder eine bitweise Konjunktion zweier numerischer Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ein `Boolean` beliebiger oder numerischer Ausdruck. Bei einem booleschen Vergleich ist `result` die logische Verknüpfung von zwei `Boolean`-Werten. Bei bitweisen Vorgängen ist `result` ein numerischer Wert, der die bitweise Konjunktion zweier numerischer Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Ein `Boolean` beliebiger oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein `Boolean` beliebiger oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Bei einem booleschen Vergleich ist `result` nur dann `True`, wenn sowohl `expression1` als auch `expression2` zu `True` ausgewertet werden. In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert von `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> Bei einem booleschen Vergleich wertet der `And`-Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können. Der [andwas-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) führt *Kurzschluss*aus, was bedeutet, dass `expression2` nicht ausgewertet wird, wenn `expression1` `False` ist.  
  
 Beim Anwenden auf numerische Werte führt der `And`-Operator einen bitweisen Vergleich identischer positionierter Bits in zwei numerischen Ausdrücken durch und legt das entsprechende Bit in `result` gemäß der folgenden Tabelle fest.  
  
|Wenn Bit in `expression1` ist|Und Bit in `expression2` ist|Das Bit in `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um genaue Ergebnisse sicherzustellen.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die Operanden aus einem `Boolean`-Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean`-Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise-Operation aus.  
  
 Bei einem booleschen Vergleich ist der Datentyp des Ergebnisses `Boolean`. Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und `expression2` geeignet ist. Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
> Der `And`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `And`-Operator verwendet, um eine logische Konjunktion zweier Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean`-Wert, der angibt, ob beide Ausdrücke `True` sind.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 Im vorangehenden Beispiel werden Ergebnisse von `True` bzw. `False` erzeugt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `And`-Operator verwendet, um eine logische Konjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen. Das Bit im Ergebnis Muster wird festgelegt, wenn die entsprechenden Bits in den Operanden auf 1 festgelegt sind.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 Im vorherigen Beispiel werden die Ergebnisse von 8, 2 bzw. 0 erzeugt.  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso-Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
