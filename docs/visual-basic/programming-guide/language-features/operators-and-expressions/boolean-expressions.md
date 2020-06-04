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
ms.openlocfilehash: 8d34eb4c8b14bb4754f2a3cf5b6f9a7601aa4662
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388957"
---
# <a name="boolean-expressions-visual-basic"></a>Boolesche Ausdrücke (Visual Basic)
Ein *boolescher Ausdruck* ist ein Ausdruck, der zu einem Wert des [booleschen Datentyps](../../../language-reference/data-types/boolean-data-type.md)ausgewertet wird: `True` oder `False` . `Boolean`Ausdrücke können mehrere Formen annehmen. Am einfachsten ist der direkte Vergleich des Werts einer `Boolean` Variablen mit einem `Boolean` Literalwert, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a>Zwei Bedeutungen des =-Operators  
 Beachten Sie, dass die Zuweisungsanweisung `newCustomer = True` wie der Ausdruck im vorherigen Beispiel aussieht, aber eine andere Funktion ausführt und anders verwendet wird. Im vorherigen Beispiel stellt der Ausdruck `newCustomer = True` einen booleschen Wert dar, und das `=` Vorzeichen wird als Vergleichs Operator interpretiert. In einer eigenständigen-Anweisung wird das `=` Vorzeichen als Zuweisungs Operator interpretiert und weist der Variablen auf der linken Seite den Wert auf der rechten Seite zu. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 Weitere Informationen finden Sie unter [Wert Vergleiche](value-comparisons.md) und- [Anweisungen](../../../language-reference/statements/index.md).  
  
## <a name="comparison-operators"></a>Vergleichsoperatoren  
 Vergleichs Operatoren wie `=` , `<` , `>` , `<>` , `<=` und werden `>=` boolesche Ausdrücke erzeugt, indem der Ausdruck auf der linken Seite des Operators mit dem Ausdruck auf der rechten Seite des Operators verglichen und das Ergebnis als oder ausgewertet `True` wird `False` . Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 `42 < 81`  
  
 Da 42 kleiner als 81 ist, wird der boolesche Ausdruck im vorherigen Beispiel zu ausgewertet `True` . Weitere Informationen zu dieser Art von Ausdruck finden Sie unter [Wert Vergleiche](value-comparisons.md).  
  
### <a name="comparison-operators-combined-with-logical-operators"></a>Vergleichs Operatoren in Kombination mit logischen Operatoren  
 Vergleichsausdrücke können mit logischen Operatoren kombiniert werden, um komplexere boolesche Ausdrücke zu entwickeln. Das folgende Beispiel veranschaulicht die Verwendung von Vergleichs Operatoren in Verbindung mit einem logischen Operator.  
  
 `x > y And x < 1000`  
  
 Im vorherigen Beispiel hängt der Wert des allgemeinen Ausdrucks von den Werten der Ausdrücke auf den einzelnen Seiten des `And` Operators ab. Wenn beide Ausdrücke sind `True` , wird der allgemeine Ausdruck als ausgewertet `True` . Wenn einer der Ausdrücke ist `False` , wird der gesamte Ausdruck als ausgewertet `False` .  
  
## <a name="short-circuiting-operators"></a>Kurzschluss Operatoren  
 Die logischen Operatoren und weisen das Verhalten auf, das `AndAlso` `OrElse` als *Kurzschluss*bezeichnet wird. Ein Kurzschluss Operator wertet den linken Operanden zuerst aus. Wenn der linke Operand den Wert des gesamten Ausdrucks bestimmt, wird die Programmausführung fortgesetzt, ohne den rechten Ausdruck auszuwerten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 Im vorherigen Beispiel wertet der Operator den linken Ausdruck aus `45 < 12` . Da der linke Ausdruck als ausgewertet `False` wird, muss der gesamte logische Ausdruck zu ausgewertet werden `False` . Die Programmausführung überspringt somit die Ausführung des Codes innerhalb des `If` Blocks, ohne den rechten Ausdruck auszuwerten `testFunction(3)` . In diesem Beispiel wird nicht aufgerufen, `testFunction()` da der linke Ausdruck den gesamten Ausdruck fälert.  
  
 Entsprechend geht die Ausführung, wenn der linke Ausdruck in einem logischen Ausdruck mit `OrElse` ausgewertet `True` wird, mit der nächsten Codezeile fort, ohne den rechten Ausdruck auszuwerten, da der linke Ausdruck bereits den gesamten Ausdruck überprüft hat.  
  
### <a name="comparison-with-non-short-circuiting-operators"></a>Vergleich mit nicht Kurzschluss Operatoren  
 Im Gegensatz dazu werden beide Seiten des logischen Operators ausgewertet, wenn die logischen Operatoren `And` und `Or` verwendet werden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 Im vorangehenden Beispiel wird aufgerufen `testFunction()` , auch wenn der linke Ausdruck als ausgewertet wird `False` .  
  
## <a name="parenthetical-expressions"></a>Klammer Ausdrücke  
 Sie können Klammern verwenden, um die Reihenfolge der Auswertung von booleschen Ausdrücken zu steuern. Ausdrücke, die in Klammern eingeschlossen sind, werden zuerst ausgewertet. Bei mehreren Schachtelungs Ebenen wird den untersten geschachtelten Ausdrücken Vorrang eingeräumt. Innerhalb von Klammern verläuft die Auswertung gemäß den Regeln der Operator Rangfolge. Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Logische und bitweise Operatoren in Visual Basic](logical-and-bitwise-operators.md)
- [Wertvergleiche](value-comparisons.md)
- [Anweisungen](../statements.md)
- [Vergleichs Operatoren](../../../language-reference/operators/comparison-operators.md)
- [Effiziente Kombination von Operatoren](efficient-combination-of-operators.md)
- [Operatorrangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md)
- [Boolean-Datentyp](../../../language-reference/data-types/boolean-data-type.md)
