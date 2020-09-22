---
title: Or-Operator
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
ms.openlocfilehash: f6cfd1073ada42aa2db8be9b14c81319bc0db294
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874756"
---
# <a name="or-operator-visual-basic"></a>Or-Operator (Visual Basic)

Führt eine logische Disjunktion zweier `Boolean` Ausdrücke oder eine bitweise Disjunktion zweier numerischer Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Bestandteile  

 `result`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck. Zum `Boolean` Vergleich `result` ist die inklusivlogische Disjunktion von zwei `Boolean` Werten. Für bitweise Vorgänge `result` ist ein numerischer Wert, der die inklusive bitweise Disjunktion zweier numerischer Bitmuster darstellt.  
  
 `expression1`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein beliebiger `Boolean`-Ausdruck oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Bemerkungen  

 Zum `Boolean` Vergleich `result` ist `False` nur dann, wenn sowohl `expression1` als `expression2` `False` auch als ausgewertet werden. In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` gleich |Und `expression2` ist|Der Wert von `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> In einem `Boolean` Vergleich wertet der- `Or` Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können. Der [OrElse-Operator](orelse-operator.md) führt *Kurzschluss*aus, was bedeutet, dass `expression1` , wenn gleich ist `True` , `expression2` nicht ausgewertet wird.  
  
 Für bitweise Operationen führt der- `Or` Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken aus und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.  
  
|Wenn `expression1` Bit in|Und Bit in `expression2` ist|Das Bit in `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.  
  
## <a name="data-types"></a>Datentypen  

 Wenn die Operanden aus einem `Boolean` Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False` ) und führt eine bitweise Operation aus.  
  
 Für einen `Boolean` Vergleich ist der Datentyp des Ergebnisses `Boolean` . Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und geeignet ist `expression2` . Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Überladen  

 Der `Or` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `Or` Operator verwendet, um eine inklusivlogische Disjunktion für zwei Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob einer der beiden Ausdrücke ist `True` .  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 Im vorherigen Beispiel werden die Ergebnisse von `True` , `True` `False` bzw. erzeugt.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `Or` Operator verwendet, um die inklusive logische Disjunktion der einzelnen Bits zweier numerischer Ausdrücke auszuführen. Das Bit im Ergebnis Muster wird festgelegt, wenn eine der entsprechenden Bits in den Operanden auf 1 festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 Das vorherige Beispiel erzeugt die Ergebnisse von 10, 14 und 14.  
  
## <a name="see-also"></a>Weitere Informationen

- [Logische/bitweise Operatoren (Visual Basic)](logical-bitwise-operators.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [OrElse-Operator](orelse-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
