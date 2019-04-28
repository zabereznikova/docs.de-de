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
ms.openlocfilehash: 270b226d0a1aa7d08721e6f9ed36d68492685af3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864390"
---
# <a name="value-comparisons-visual-basic"></a>Wertevergleich (Visual Basic)
Vergleichsoperatoren können verwendet werden, um Ausdrücke zu erstellen, die die Werte von numerischen Variablen vergleichen. Diese Ausdrücke geben eine `Boolean` Wert basiert, ob der Vergleich "true" oder "false". Beispiele für ein solcher Ausdruck sind wie folgt aus.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Der erste Ausdruck wird zu `True`, da 45 größer als 26 ist. Im zweite Beispiel ergibt `False`, da 26 nicht größer als 45 befindet.  
  
 Sie können auch die numerische Ausdrücken auf diese Weise vergleichen. Die Ausdrücke, die Sie vergleichen, können selbst komplexe Ausdrücke, wie im folgenden Beispiel sein.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Die obige komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe. Die Ausdrücke auf beiden Seiten des Vergleichsoperators werden ausgewertet, und die resultierenden Werte werden dann verglichen mit der `>=` Vergleichsoperator. Wenn der Wert des Ausdrucks auf der linken Seite größer als oder gleich dem Wert des Ausdrucks auf der rechten Seite, der gesamte Ausdruck ergibt `True`ist, andernfalls ist er `False`.  
  
 Ausdrücke, die Werte zu vergleichen sind am häufigsten in `If...Then` Konstruktionen, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 Die `=` Vorzeichen ist, ein Vergleichsoperator als auch ein Zuweisungsoperator. Wenn als Vergleichsoperator verwendet wird, wertet er, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 Sie können auch einen Vergleichsausdruck an einer beliebigen Stelle verwenden eine `Boolean` Wert ist erforderlich, z. B. in einer `If`, `While`, `Loop`, oder `ElseIf` -Anweisung, oder beim Zuweisen oder das Übergeben eines Werts an eine `Boolean` Variable. Im folgenden Beispiel der von der Vergleichsausdruck zurückgegebene Wert zugewiesen ist eine `Boolean` Variable.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Siehe auch

- [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Vorgehensweise: Berechnen von numerischen Werten](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
