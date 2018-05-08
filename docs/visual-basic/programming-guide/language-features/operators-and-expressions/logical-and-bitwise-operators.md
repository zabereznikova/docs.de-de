---
title: Logische und bitweise Operatoren in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 371d28629b39fb2808ca018ea69da3306a31f50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Logische und bitweise Operatoren in Visual Basic
Logische Operatoren vergleichen `Boolean` Ausdrücke und der Rückgabewert eine `Boolean` Ergebnis. Die `And`, `Or`, `AndAlso`, `OrElse`, und `Xor` Operatoren sind *binäre* , da sie zwei Operanden in Anspruch nehmen, während er sich die `Not` Operator *unäre* , da er einen einzigen Operanden akzeptiert. Einige dieser Operatoren können auch bitweise logische Operationen für ganzzahlige Werte ausführen.  
  
## <a name="unary-logical-operator"></a>Unärer logischer Operator  
 Die [Not-Operator](../../../../visual-basic/language-reference/operators/not-operator.md) führt logische *Negation* auf eine `Boolean` Ausdruck. Das Ergebnis ist des logischen Gegenteil des Operanden. Wenn der ausgewertete Ausdruck `True`, klicken Sie dann `Not` gibt `False`; Wenn der ausgewertete Ausdruck `False`, klicken Sie dann `Not` gibt `True`. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a>Binäre logische Operatoren  
 Die [And-Operators](../../../../visual-basic/language-reference/operators/and-operator.md) führt logische *zusammen* für zwei `Boolean` Ausdrücke. Wenn beide Ausdrücke `True`, klicken Sie dann `And` gibt `True`. Wenn mindestens einer der Ausdrücke ergibt `False`, klicken Sie dann `And` gibt `False`.  
  
 Die [oder-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) führt logische *Disjunktion* oder *Aufnahme* für zwei `Boolean` Ausdrücke. Wenn einer der Ausdrücke ergibt `True`, oder beide auswerten `True`, klicken Sie dann `Or` gibt `True`. Wenn weder Ausdruck ergibt `True`, `Or` gibt `False`.  
  
 Die [Xor-Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) führt logische *Ausschluss* für zwei `Boolean` Ausdrücke. Wenn genau ein Ausdruck ergibt `True`, jedoch nicht zu beiden `Xor` gibt `True`. Wenn beide Ausdrücke `True` oder beide auswerten `False`, `Xor` gibt `False`.  
  
 Das folgende Beispiel veranschaulicht die `And`, `Or`, und `Xor` Operatoren.  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a>Kurzschließen von logischen Operationen  
 Die [AndAlso-Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) ähnelt stark der `And` -Operator, insofern, dass die logischen Konjunktion für zwei führt es `Boolean` Ausdrücke. Der Hauptunterschied zwischen den beiden ist, `AndAlso` weist *verkürzte* Verhalten. Wenn der erste Ausdruck in eine `AndAlso` Ausdruck wird ausgewertet, `False`, und klicken Sie dann der zweite Ausdruck nicht ausgewertet, weil sie nicht können, das Endergebnis ändern und `AndAlso` gibt `False`.  
  
 Auf ähnliche Weise die [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) führt eine verkürzte logischen Disjunktion für zwei `Boolean` Ausdrücke. Wenn der erste Ausdruck in eine `OrElse` Ausdruck wird ausgewertet, `True`, und klicken Sie dann der zweite Ausdruck nicht ausgewertet, weil sie nicht können, das Endergebnis ändern und `OrElse` gibt `True`.  
  
### <a name="short-circuiting-trade-offs"></a>Kurzschließen von vor-und Nachteile  
 Verkürzte kann die Leistung erhöht nicht die Auswertung eines Ausdrucks, das das Ergebnis der logischen Operation nicht ändern können. Jedoch wenn dieser Ausdruck zusätzliche Aktionen ausführt, überspringt die verkürzte dieser Aktionen. Z. B., wenn der Ausdruck einen Aufruf von umfasst eine `Function` Prozedur, die, dass die Prozedur nicht aufgerufen wird, wenn der Ausdruck kurzgeschlossen ist und keinen zusätzlicher Code, in enthalten der `Function` wird nicht ausgeführt. Aus diesem Grund wird die Funktion möglicherweise nur gelegentlich ausgeführt und möglicherweise nicht ordnungsgemäß getestet werden. Oder die Programmlogik abhängen, den Code in der `Function`.  
  
 Das folgende Beispiel veranschaulicht den Unterschied zwischen `And`, `Or`, und ihren entsprechenden Kurzschlussoperatoren.  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 Im vorherigen Beispiel beachten Sie, dass einige wichtige Code innerhalb `checkIfValid()` wird nicht ausgeführt werden, wenn der Aufruf kurzgeschlossen wird. Die erste `If` Anweisung ruft `checkIfValid()` , obwohl `12 > 45` gibt `False`, da `And` keinen Kurzschluss ausführt. Die zweite `If` rufen Anweisung nicht `checkIfValid()`, da beim `12 > 45` gibt `False`, `AndAlso` kurzgeschlossen wird den zweiten Ausdruck. Das dritte `If` Anweisung ruft `checkIfValid()` , obwohl `12 < 45` gibt `True`, da `Or` keinen Kurzschluss ausführt. Das vierte `If` rufen Anweisung nicht `checkIfValid()`, da beim `12 < 45` gibt `True`, `OrElse` kurzgeschlossen wird den zweiten Ausdruck.  
  
## <a name="bitwise-operations"></a>Bitweise Operationen  
 Bitweise Operationen Werten zwei ganzzahlige Werte im binären (Basis 2)-Formular. Vergleichen die Bits an den entsprechenden Positionen, und weisen Sie dann die Werte auf Grundlage des Vergleichs. Das folgende Beispiel veranschaulicht die `And` Operator.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 Im vorherigen Beispiel wird den Wert des `x` auf 1. Dies geschieht aus den folgenden Gründen:  
  
-   Die Werte werden als Binärdatei behandelt:  
  
     3 in binärer Form = 011  
  
     5 in binärer Form = 101  
  
-   Die `And` Operator vergleicht die binären Darstellungen, die eine binäre Position (Bit) zu einem Zeitpunkt. Wenn beide Bits an einer bestimmten Position 1 sind, wird eine 1 an dieser Stelle im Resultset platziert. Wenn ein der Bits 0 ist, wird eine 0 in dieser Position im Resultset platziert. Im vorherigen Beispiel ist dies wie folgt:  
  
     011 (3 in binärer Form)  
  
     101 (5 in binärer Form)  
  
     001 (Ergebnis in binärer Form)  
  
-   Das Ergebnis wird als Dezimalzahl behandelt. Der Wert 001 ist die binäre Darstellung von 1, sodass `x` = 1.  
  
 Der bitweise `Or` Vorgang ist ähnlich, außer dass das Ergebnisbit 1 zugewiesen wird, wenn eine oder beide der verglichenen Bits 1 ist. `Xor` weist 1 mit dem Ergebnisbit ein, wenn genau einem der (nicht beide) der verglichenen Bits 1 ist. `Not` nimmt einen einzelnen Operanden aus und kehrt alle Bits, einschließlich des Vorzeichenbits und weist diesen Wert auf das Ergebnis. Dies bedeutet, dass für positive Zahlen mit Vorzeichen `Not` gibt immer einen negativen Wert zurück, und für negative Zahlen `Not` gibt immer eine positive Zahl oder 0 (null) zurück.  
  
 Die `AndAlso` und `OrElse` Operatoren unterstützen keine bitweise Operationen.  
  
> [!NOTE]
>  Bitweise Operationen können nur für ganzzahlige Typen ausgeführt werden. Gleitkommawerte müssen in ganzzahlige Typen konvertiert werden, bevor bitweise Operation fortgesetzt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Logische/bitweise Operatoren (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Verkettungsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
