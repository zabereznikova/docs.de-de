---
title: Wertevergleich (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 6e1eda09784814d139ef94b6720b538aef30e5e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649606"
---
# <a name="value-comparisons-visual-basic"></a>Wertevergleich (Visual Basic)
Vergleichsoperatoren können verwendet werden, um Ausdrücke zu erstellen, die die Werte von numerischen Variablen vergleichen. Diese Ausdrücke Zurückgeben einer `Boolean` Wert basierend darauf, ob der Vergleich "true" oder "false". Beispiele für ein solcher Ausdruck sind wie folgt aus.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Der erste Ausdruck wird zu `True`, weil 45 größer als 26 ist. Im zweite Beispiel ergibt `False`, da 26 nicht größer als 45 befindet.  
  
 Sie können auch numerische Ausdrücke auf diese Weise vergleichen. Die Ausdrücke, die Sie vergleichen, können selbst komplexe Ausdrücke, wie im folgenden Beispiel werden.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Die vorangehende komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe. Die Ausdrücke auf beiden Seiten des Vergleichsoperators werden ausgewertet, und die erhaltenen Werte werden dann einem Vergleich unter Verwendung der `>=` Vergleichsoperator. Wenn der Wert des Ausdrucks auf der linken Seite größer als oder gleich dem Wert des Ausdrucks auf der rechten Seite, der gesamte Ausdruck wird zu `True`ist, andernfalls ist er `False`.  
  
 Ausdrücke, die Werte verglichen werden am häufigsten `If...Then` Konstruktionen, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 Die `=` Anmeldung ist ein Vergleichsoperator sowie ein Zuweisungsoperator. Wenn als Vergleichsoperator verwendet wird, wertet ihn an, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite ist, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 Sie können auch einen Vergleichsausdruck verwenden, an einer beliebigen Stelle ein `Boolean` Wert ist erforderlich, z. B. in einer `If`, `While`, `Loop`, oder `ElseIf` -Anweisung, oder beim Zuweisen oder zum Übergeben eines Werts an eine `Boolean` Variable. Im folgenden Beispiel durch den Vergleichsausdruck zurückgegebene Wert zugewiesen wird eine `Boolean` Variable.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Gewusst wie: Berechnen von numerischen Werten](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
