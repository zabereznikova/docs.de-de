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
ms.openlocfilehash: 59f27b92996e1506be5967de88c22fb88e06f5b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965847"
---
# <a name="xor-operator-visual-basic"></a>Xor-Operator (Visual Basic)
Führt einen logischen Ausschluss für zwei `Boolean` Ausdrücke oder einen bitweisen Ausschluss zweier numerischer Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Eine `Boolean` beliebige oder numerische Variable. Bei einem booleschen Vergleich `result` ist der logische Ausschluss (exklusive logische Disjunktion) von `Boolean` zwei Werten. Bei bitweisen Vorgängen `result` ist ein numerischer Wert, der den bitweisen Ausschluss (exklusive bitweise Disjunktion) von zwei numerischen Bitmustern darstellt.  
  
 `expression1`  
 Erforderlich. Ein `Boolean` beliebiger oder numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein `Boolean` beliebiger oder numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Bei einem booleschen Vergleich `result` ist `True` nur dann der Wert, wenn genau `expression1` `True`einer `expression2` von und als ausgewertet wird. Das heißt, wenn und nur, `expression1` Wenn `expression2` und als gegen `Boolean` überliegende Werte ausgewertet werden. In der folgenden Tabelle wird `result` veranschaulicht, wie bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert von `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> Bei einem booleschen Vergleich wertet der `Xor` Operator immer beide Ausdrücke aus, die das Ausführen von Prozedur aufrufen einschließen können. Es ist kein Kurzschluss-Gegenstück zu `Xor`vorhanden, da das Ergebnis immer von beiden Operanden abhängig ist. Informationen zu *kurzen Schluss* logischen Operatoren finden Sie unter andgleich- [Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) und [OrElse-Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Für bitweise Operationen führt der `Xor` -Operator einen bitweisen Vergleich von identisch positionierten Bits in zwei numerischen Ausdrücken aus und legt das entsprechende Bit in `result` entsprechend der folgenden Tabelle fest.  
  
|Wenn Bit in `expression1`|Und Bit in `expression2` ist|Das Bit in `result` ist|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Da die logischen und bitweisen Operatoren Vorrang vor anderen arithmetischen und relationalen Operatoren sind, sollten alle bitweisen Vorgänge in Klammern eingeschlossen werden, um eine exakte Ausführung sicherzustellen.  
  
 Beispielsweise ist der `Xor` Wert für 5 3 6. Um zu sehen, warum dies der Fall ist, konvertieren Sie 5 und 3 in die Binär Darstellungen 101 und 011. Verwenden Sie dann die vorherige Tabelle, um zu bestimmen, dass 101 Xor 011 110 ist, was die binäre Darstellung der Dezimalzahl 6 ist.  
  
## <a name="data-types"></a>Datentypen  
 Wenn die `Boolean` Operanden aus einem Ausdruck und einem numerischen Ausdruck bestehen, konvertiert Visual Basic den `Boolean` Ausdruck in einen numerischen Wert (– 1 für `True` und 0 für `False`) und führt eine bitweise Operation aus.  
  
 Für einen `Boolean` Vergleich ist `Boolean`der Datentyp des Ergebnisses. Bei einem bitweisen Vergleich ist der Ergebnis Datentyp ein numerischer Typ, der für die Datentypen von `expression1` und `expression2`geeignet ist. Weitere Informationen finden Sie in der Tabelle "relationale und bitweise Vergleiche" in den [Datentypen der Operator Ergebnisse](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Überladen  
 Der `Xor` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `Xor` -Operator verwendet, um einen logischen Ausschluss (exklusive logische Disjunktion) für zwei Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean` Wert, der angibt, ob genau einer der Ausdrücke `True`ist.  
  
 [!code-vb[VbVbalrOperators#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#40)]  
  
 Im vorherigen Beispiel werden die Ergebnisse `False`von `True`, `False`bzw. erzeugt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `Xor` -Operator verwendet, um einen logischen Ausschluss (exklusive logische Disjunktion) für die einzelnen Bits zweier numerischer Ausdrücke auszuführen. Das Bit im Ergebnis Muster wird festgelegt, wenn genau eines der entsprechenden Bits in den Operanden auf 1 festgelegt ist.  
  
 [!code-vb[VbVbalrOperators#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#41)]  
  
 Im vorherigen Beispiel werden die Ergebnisse 2, 12 bzw. 14 erzeugt.  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
