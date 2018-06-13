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
ms.openlocfilehash: ff5843c815658468ac69fe5d62a9ea4cac2be830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655797"
---
# <a name="boolean-expressions-visual-basic"></a>Boolesche Ausdrücke (Visual Basic)
Ein *booleschen Ausdruck* ist ein Ausdruck, der einen Wert ergibt die [booleschen Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` oder `False`. `Boolean` Ausdrücke können mehrere Formen annehmen. Die einfachste Technologie ist des direkten Zeichenfolgenvergleichs den Wert des eine `Boolean` -Variable auf einen `Boolean` Literal, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## <a name="two-meanings-of-the--operator"></a>Zwei Bedeutungen von den =-Operator  
 Beachten Sie, dass die zuweisungsanweisung `newCustomer = True` sieht so aus wie des Ausdrucks im vorherigen Beispiel, aber es führt eine andere Funktion und wird anders. Im vorherigen Beispiel der Ausdruck `newCustomer = True` stellt einen booleschen Wert und die `=` Anmeldung wird als Vergleichsoperator interpretiert. In einer eigenständigen Anweisung die `=` Zeichen wird als Zuweisungsoperator interpretiert, und weist den Wert auf der rechten Seite der Variablen auf der linken Seite. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 Weitere Informationen finden Sie unter [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) und [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Vergleichsoperatoren  
 Vergleichsoperatoren wie `=`, `<`, `>`, `<>`, `<=`, und `>=` boolesche Ausdrücke durch Vergleichen des Ausdrucks auf der linken Seite des Operators, der den Ausdruck auf der rechten Seite erstellen des Operators und das Ergebnis als auswerten `True` oder `False`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `42 < 81`  
  
 Da 42 kleiner als 81 ist, ergibt der boolesche Ausdruck im vorherigen Beispiel um `True`. Weitere Informationen über diese Art von Ausdruck finden Sie unter [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Vergleichsoperatoren mit logischen Operatoren kombiniert  
 Vergleichsausdrücke können komplexe boolesche Ausdrücke erzeugen mithilfe von logischen Operatoren kombiniert werden. Das folgende Beispiel veranschaulicht die Verwendung von Vergleichsoperatoren in Verbindung mit einem logischen Operator.  
  
 `x > y And x < 1000`  
  
 Im vorherigen Beispiel der Wert des gesamten Ausdrucks hängt die Werte der Ausdrücke auf beiden Seiten des der `And` Operator. Wenn beide Ausdrücke `True`, und klicken Sie dann der gesamte Ausdruck ergibt `True`. Wenn einer der Ausdrücke ist `False`, und klicken Sie dann der gesamte Ausdruck ergibt `False`.  
  
## <a name="short-circuiting-operators"></a>Kurzschließen von Operatoren  
 Die logischen Operatoren `AndAlso` und `OrElse` genannte Verhalten *verkürzte*. Ein Kurzschlussoperator wertet zuerst den linken Operand. Wenn der linke Operand der Wert des gesamten Ausdrucks bestimmt, wird die Ausführung des Programms fortgesetzt, ohne den rechten Ausdruck auszuwerten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 Im vorherigen Beispiel wertet der Operator den linken Ausdruck `45 < 12`. Da der linke Ausdruck ergibt `False`, muss der gesamte logische Ausdruck ergeben `False`. Programm überspringt daher die Ausführung des Codes in der `If` -Block ohne den rechten Ausdruck auswerten `testFunction(3)`. In diesem Beispiel rufen nicht `testFunction()` , da der linke Ausdruck den gesamten Ausdruck fälscht.  
  
 Auf ähnliche Weise, wenn der linke Ausdruck in einem logischen Ausdruck mit `OrElse` ergibt `True`, die Ausführung zur nächsten Zeile des Codes ohne Auswerten des rechten Ausdrucks erfolgt, da der linke Ausdruck den gesamten bereits überprüft wurde Ausdruck.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Vergleich mit Operatoren nicht Kurzschlussoperationen  
 Im Gegensatz dazu werden beide Seiten des logischen Operators ausgewertet Wenn die logischen Operatoren `And` und `Or` verwendet werden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 Im vorherigen Beispiel wird `testFunction()` , obwohl der linke Ausdruck ergibt `False`.  
  
## <a name="parenthetical-expressions"></a>Ausdrücke in Klammern  
 Sie können Klammern verwenden, um die Reihenfolge der Auswertung von booleschen Ausdrücken aus zu steuern. Ausdrücke in Klammern werden zuerst ausgewertet. Für mehrere Schachtelungsebenen erhält die am tiefsten geschachtelte Ausdrücke Vorrang. Innerhalb der Klammern wird die Auswertung entsprechend den Regeln der Operatorrangfolge. Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Anweisungen](../../../../visual-basic/programming-guide/language-features/statements.md)  
 [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
