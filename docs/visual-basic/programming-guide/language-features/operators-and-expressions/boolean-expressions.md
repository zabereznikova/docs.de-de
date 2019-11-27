---
title: Boolesche Ausdrücke
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
ms.openlocfilehash: 1000ec6e4b35d0cb2c6232b50f9a9551cb0dfdcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350811"
---
# <a name="boolean-expressions-visual-basic"></a>Boolesche Ausdrücke (Visual Basic)
Ein *boolescher Ausdruck* ist ein Ausdruck, der einen Wert des [booleschen Datentyps](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)ergibt: `True` oder `False`. `Boolean` Ausdrücke können mehrere Formen annehmen. Am einfachsten ist der direkte Vergleich des Werts einer `Boolean` Variablen mit einem `Boolean` Literalwert, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Zwei Bedeutungen des =-Operators  
 Beachten Sie, dass die Zuweisungsanweisung `newCustomer = True` wie der Ausdruck im vorherigen Beispiel aussieht, aber eine andere Funktion ausführt und anders verwendet wird. Im vorherigen Beispiel stellt der Ausdruck `newCustomer = True` einen booleschen Wert dar, und das `=` Vorzeichen wird als Vergleichs Operator interpretiert. In einer eigenständigen Anweisung wird das `=` Vorzeichen als Zuweisungs Operator interpretiert und weist der Variablen auf der linken Seite den Wert auf der rechten Seite zu. Das folgende Beispiel veranschaulicht dies.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Weitere Informationen finden Sie unter [Wert Vergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) und- [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Vergleichsoperatoren  
 Vergleichs Operatoren wie `=`, `<`, `>`, `<>`, `<=`und `>=` erzeugt boolesche Ausdrücke, indem der Ausdruck auf der linken Seite des Operators mit dem Ausdruck auf der rechten Seite des Operators verglichen und das Ergebnis als `True` oder `False`ausgewertet wird. Das folgende Beispiel veranschaulicht dies.  
  
 `42 < 81`  
  
 Da 42 kleiner als 81 ist, wird der boolesche Ausdruck im vorangehenden Beispiel zu `True`ausgewertet. Weitere Informationen zu dieser Art von Ausdruck finden Sie unter [Wert Vergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Vergleichs Operatoren in Kombination mit logischen Operatoren  
 Vergleichsausdrücke können mit logischen Operatoren kombiniert werden, um komplexere boolesche Ausdrücke zu entwickeln. Das folgende Beispiel veranschaulicht die Verwendung von Vergleichs Operatoren in Verbindung mit einem logischen Operator.  
  
 `x > y And x < 1000`  
  
 Im vorherigen Beispiel hängt der Wert des allgemeinen Ausdrucks von den Werten der Ausdrücke auf den einzelnen Seiten des `And` Operators ab. Wenn beide Ausdrücke `True`sind, wird der allgemeine Ausdruck als `True`ausgewertet. Wenn ein Ausdruck `False`ist, wird der gesamte Ausdruck als `False`ausgewertet.  
  
## <a name="short-circuiting-operators"></a>Kurzschluss Operatoren  
 Die logischen Operatoren `AndAlso` und `OrElse` ein Verhalten aufweisen, das als *Kurzschluss*bezeichnet wird. Ein Kurzschluss Operator wertet den linken Operanden zuerst aus. Wenn der linke Operand den Wert des gesamten Ausdrucks bestimmt, wird die Programmausführung fortgesetzt, ohne den rechten Ausdruck auszuwerten. Das folgende Beispiel veranschaulicht dies.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 Im vorherigen Beispiel wertet der Operator den linken Ausdruck aus, `45 < 12`. Da der linke Ausdruck als `False`ausgewertet wird, muss der gesamte logische Ausdruck zu `False`ausgewertet werden. Durch die Programmausführung wird die Ausführung des Codes innerhalb des `If` Blocks überdies, ohne den rechten Ausdruck, `testFunction(3)`, auszuwerten. In diesem Beispiel wird `testFunction()` nicht aufgerufen, da der linke Ausdruck den gesamten Ausdruck verfältet.  
  
 Wenn der linke Ausdruck in einem logischen Ausdruck, der `OrElse` verwendet, `True`ergibt, erfolgt die Ausführung mit der nächsten Codezeile, ohne den rechten Ausdruck auszuwerten, da der linke Ausdruck bereits den gesamten Ausdruck überprüft hat.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Vergleich mit nicht Kurzschluss Operatoren  
 Im Gegensatz dazu werden beide Seiten des logischen Operators ausgewertet, wenn die logischen Operatoren `And` und `Or` verwendet werden. Das folgende Beispiel veranschaulicht dies.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 Im vorangehenden Beispiel wird `testFunction()` aufgerufen, obwohl der linke Ausdruck als `False`ausgewertet wird.  
  
## <a name="parenthetical-expressions"></a>Klammer Ausdrücke  
 Sie können Klammern verwenden, um die Reihenfolge der Auswertung von booleschen Ausdrücken zu steuern. Ausdrücke, die in Klammern eingeschlossen sind, werden zuerst ausgewertet. Bei mehreren Schachtelungs Ebenen wird den untersten geschachtelten Ausdrücken Vorrang eingeräumt. Innerhalb von Klammern verläuft die Auswertung gemäß den Regeln der Operator Rangfolge. Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch

- [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Anweisungen](../../../../visual-basic/programming-guide/language-features/statements.md)
- [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Boolean-Datentyp](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
