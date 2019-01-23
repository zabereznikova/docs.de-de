---
title: Boolesche Ausdrücke (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: a86df2734d315e5fed0784b0394bb305b15562a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562751"
---
# <a name="boolean-expressions-visual-basic"></a>Boolesche Ausdrücke (Visual Basic)
Ein *booleschen Ausdruck* ist ein Ausdruck, der auf einen Wert ergibt die [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` oder `False`. `Boolean` Ausdrücke können verschiedene Formen annehmen. Die einfachste Form des direkten Zeichenfolgenvergleichs den Wert der ist eine `Boolean` Variable eine `Boolean` Literal, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>Zwei Bedeutungen, die von den =-Operator  
 Beachten Sie, dass die zuweisungsanweisung `newCustomer = True` sieht genauso aus wie des Ausdrucks im vorherigen Beispiel, aber es führt eine andere Funktion und wird anders verwendet werden kann. Im vorherigen Beispiel, den Ausdruck `newCustomer = True` stellt einen booleschen Wert, und die `=` anmelden werden als Vergleichsoperator interpretiert. In einer eigenständigen Anweisung die `=` anmelden, wird als Zuweisungsoperator interpretiert, und weist den Wert auf der rechten Seite auf die Variable auf der linken Seite. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Weitere Informationen finden Sie unter [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) und [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Vergleichsoperatoren  
 Vergleichsoperatoren wie `=`, `<`, `>`, `<>`, `<=`, und `>=` ergeben boolesche Ausdrücke, durch den Ausdruck auf der linken Seite des Operators, der den Ausdruck auf der rechten Seite vergleichen der Operator und bewerten das Ergebnis als `True` oder `False`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `42 < 81`  
  
 Da 42 kleiner als 81 ist, der boolesche Ausdruck im obigen Beispiel ergibt `True`. Weitere Informationen über diese Art von Ausdrücken finden Sie unter [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Vergleichsoperatoren, die mit logischen Operatoren kombiniert  
 Ausdrücke zum Vergleichen können mithilfe von logischen Operatoren zum Erzeugen komplexer boolescher Ausdrücken kombiniert werden. Das folgende Beispiel veranschaulicht die Verwendung von Vergleichsoperatoren in Verbindung mit einem logischen Operator.  
  
 `x > y And x < 1000`  
  
 Im vorherigen Beispiel ist der Wert des gesamten Ausdrucks hängt die Werte der Ausdrücke auf beiden Seiten des der `And` Operator. Wenn beide Ausdrücke sind `True`, und klicken Sie dann der gesamte Ausdruck ergibt `True`. Falls ein Ausdruck ist `False`, und klicken Sie dann der gesamte Ausdruck ergibt `False`.  
  
## <a name="short-circuiting-operators"></a>Kurzschlussoperatoren  
 Die logischen Operatoren `AndAlso` und `OrElse` Verhalten sich genannt *kurzschließen*. Ein Kurzschlussoperator wertet zuerst den linken Operand aus. Wenn der linke Operand den Wert des gesamten Ausdrucks bestimmt wird, wird die programmausführung fortgesetzt, ohne den rechten Ausdruck auszuwerten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 Im vorherigen Beispiel wertet der Operator der linken Ausdruck `45 < 12`. Da der linke Ausdruck ergibt `False`, muss der gesamte logische Ausdruck ergeben `False`. Ausführung des Programms überspringt daher die Ausführung des Codes innerhalb der `If` -Block ohne dem rechten Ausdruck `testFunction(3)`. In diesem Beispiel wird nicht aufgerufen. `testFunction()` , da der linke Ausdruck den gesamten Ausdruck fälscht.  
  
 Auf ähnliche Weise, wenn der linke Ausdruck in einem logischen Ausdruck mit `OrElse` ergibt `True`, Ausführung wird fortgesetzt, in die nächste Zeile des Codes ohne Auswertung des rechten Ausdrucks ist, da der linke Ausdruck den gesamten bereits überprüft wurde -Ausdruck.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Vergleich mit nicht kurzschließen Operatoren  
 Im Gegensatz dazu, beide Seiten des logischen Operators ausgewertet werden bei der die logischen Operatoren `And` und `Or` verwendet werden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 Im vorherigen Beispiel wird `testFunction()` , obwohl der linke Ausdruck ergibt `False`.  
  
## <a name="parenthetical-expressions"></a>Ausdrücke in Klammern  
 Sie können Klammern verwenden, um die Reihenfolge der Auswertung von booleschen Ausdrücken zu steuern. Ausdrücke in Klammern werden zuerst ausgewertet. Für mehrere Schachtelungsebenen erhält die am tiefsten geschachtelte Ausdrücke Vorrang. Innerhalb von Klammern wird die Auswertung gemäß den Regeln der Operatorrangfolge. Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch
- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Anweisungen](../../../../visual-basic/programming-guide/language-features/statements.md)
- [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
