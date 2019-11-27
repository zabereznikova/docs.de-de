---
title: Wertvergleiche
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
ms.openlocfilehash: f766eaaada486a0f70838bafb754d25070ff4174
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346288"
---
# <a name="value-comparisons-visual-basic"></a>Wertevergleich (Visual Basic)
Vergleichs Operatoren können verwendet werden, um Ausdrücke zu erstellen, die die Werte numerischer Variablen vergleichen. Diese Ausdrücke geben einen `Boolean` Wert zurück, je nachdem, ob der Vergleich true oder false ist. Beispiele für einen solchen Ausdruck:  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Der erste Ausdruck wird zu `True`ausgewertet, da 45 größer als 26 ist. Im zweiten Beispiel wird zu `False`ausgewertet, da 26 nicht größer als 45 ist.  
  
 Sie können numerische Ausdrücke auch auf diese Weise vergleichen. Die Ausdrücke, die Sie vergleichen, können selbst komplexe Ausdrücke sein, wie im folgenden Beispiel gezeigt.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Der vorangehende komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe. Die Ausdrücke auf beiden Seiten des Vergleichs Operators werden ausgewertet, und die resultierenden Werte werden dann mithilfe des `>=` Vergleichs Operators verglichen. Wenn der Wert des Ausdrucks auf der linken Seite größer oder gleich dem Wert des Ausdrucks auf der rechten Seite ist, wird der gesamte Ausdruck als `True`ausgewertet; Andernfalls wird zu `False`ausgewertet.  
  
 Ausdrücke, die Werte vergleichen, werden am häufigsten in `If...Then` Konstruktionen verwendet, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 Das `=` Vorzeichen ist ein Vergleichs Operator und ein Zuweisungs Operator. Wenn es als Vergleichs Operator verwendet wird, wird ausgewertet, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite ist, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 Sie können einen Vergleichs Ausdruck auch dann verwenden, wenn ein `Boolean` Wert benötigt wird, z. b. in einer `If`-, `While`-, `Loop`-oder `ElseIf`-Anweisung oder beim Zuweisen oder übergeben eines Werts an eine `Boolean` Variable. Im folgenden Beispiel wird der vom Vergleichs Ausdruck zurückgegebene Wert einer `Boolean` Variablen zugewiesen.  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>Siehe auch

- [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Vergleichs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Gewusst wie: Berechnen von numerischen Werten](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
