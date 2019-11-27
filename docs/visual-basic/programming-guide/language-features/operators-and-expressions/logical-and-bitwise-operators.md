---
title: Logische und bitweise Operatoren
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
ms.openlocfilehash: 55a246c0d56501a409ebbc7d0d0aa39ae9fa1770
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343591"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Logische und bitweise Operatoren in Visual Basic
Logische Operatoren vergleichen `Boolean` Ausdrücke und geben ein `Boolean` Ergebnis zurück. Die Operatoren "`And`", "`Or`", "`AndAlso`", "`OrElse`" und "`Xor`" sind *Binär* , da Sie zwei Operanden annehmen, während der `Not` Operator *unär* ist, da er einen einzelnen Operanden annimmt Einige dieser Operatoren können auch bitweise logische Operationen für ganzzahlige Werte ausführen.  
  
## <a name="unary-logical-operator"></a>Unärer logischer Operator  
 Der [Not-Operator](../../../../visual-basic/language-reference/operators/not-operator.md) führt eine logische *Negation* für einen `Boolean` Ausdruck aus. Es ergibt das logische Gegenteil des Operanden. Wenn der Ausdruck als `True`ausgewertet wird, gibt `Not` `False`zurück. Wenn der Ausdruck als `False`ausgewertet wird, gibt `Not` `True`zurück. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Binäre logische Operatoren  
 Der [and-Operator](../../../../visual-basic/language-reference/operators/and-operator.md) führt eine logische *Konjunktion* für zwei `Boolean` Ausdrücke aus. Wenn beide Ausdrücke als `True`ausgewertet werden, gibt `And` `True`zurück. Wenn mindestens einer der Ausdrücke als `False`ausgewertet wird, gibt `And` `False`zurück.  
  
 Der [OR-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) führt eine logische *Disjunktion* oder die *Einbindung* zweier `Boolean` Ausdrücke aus. Wenn ein Ausdruck zu `True`ausgewertet wird oder beide als `True`ausgewertet werden, gibt `Or` `True`zurück. Wenn keiner der Ausdrücke als `True`ausgewertet wird, gibt `Or` `False`zurück.  
  
 Der [Xor-Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) führt einen logischen *Ausschluss* für zwei `Boolean` Ausdrücke aus. Wenn genau ein Ausdruck `True`, aber nicht beides ergibt, gibt `Xor` `True`zurück. Wenn beide Ausdrücke als `True` ausgewertet werden oder beide als `False`ausgewertet werden, gibt `Xor` `False`zurück.  
  
 Im folgenden Beispiel werden die Operatoren `And`, `Or`und `Xor` veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Kurzschluss logische Vorgänge  
 Der [andwas-Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) ist dem `And`-Operator sehr ähnlich, da er auch eine logische Konjunktion für zwei `Boolean` Ausdrücke ausführt. Der Hauptunterschied zwischen den beiden besteht darin, dass `AndAlso` *Kurzschluss* Verhalten aufweist. Wenn der erste Ausdruck in einem `AndAlso` Ausdruck zu `False`ausgewertet wird, wird der zweite Ausdruck nicht ausgewertet, da er das Endergebnis nicht ändern kann, und `AndAlso` gibt `False`zurück.  
  
 Entsprechend führt der [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) eine Kurzschluss logische Disjunktion für zwei `Boolean` Ausdrücke aus. Wenn der erste Ausdruck in einem `OrElse` Ausdruck zu `True`ausgewertet wird, wird der zweite Ausdruck nicht ausgewertet, da er das Endergebnis nicht ändern kann, und `OrElse` gibt `True`zurück.  
  
### <a name="short-circuiting-trade-offs"></a>Kurze Schluss Kompromisse  
 Kurzschluss Vorgänge können die Leistung verbessern, indem Sie keinen Ausdruck auswerten, der das Ergebnis der logischen Operation nicht ändern kann. Wenn dieser Ausdruck jedoch weitere Aktionen ausführt, überspringt der Kurzschluss diese Aktionen. Wenn der Ausdruck z. b. einen Aufruf einer `Function` Prozedur enthält, wird diese Prozedur nicht aufgerufen, wenn der Ausdruck kurzgeschlossen wird, und jeglicher zusätzlicher Code, der in der `Function` enthalten ist, wird nicht ausgeführt. Daher kann die Funktion nur gelegentlich ausgeführt werden und wird möglicherweise nicht ordnungsgemäß getestet. Oder die Programmlogik hängt möglicherweise vom Code in der `Function`ab.  
  
 Das folgende Beispiel veranschaulicht den Unterschied zwischen `And`, `Or`und ihren Kurzschluss Entsprechungen.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Beachten Sie im vorhergehenden Beispiel, dass einige wichtige Codes innerhalb `checkIfValid()` nicht ausgeführt werden, wenn der-Rückruf kurzgeschlossen wird. Mit der ersten `If`-Anweisung wird `checkIfValid()` aufgerufen, auch wenn `12 > 45` `False`zurückgibt, da `And` keine Kurzschluss-enthält. Die zweite `If`-Anweisung ruft `checkIfValid()`nicht auf, da der zweite Ausdruck `AndAlso`, wenn `12 > 45` `False`zurückgibt. Die dritte `If`-Anweisung ruft `checkIfValid()` auf, auch wenn `12 < 45` `True`zurückgibt, da `Or` keine Kurzschluss-enthält. Die vierte `If`-Anweisung ruft `checkIfValid()`nicht auf, da der zweite Ausdruck `OrElse`, wenn `12 < 45` `True`zurückgibt.  
  
## <a name="bitwise-operations"></a>Bitweise Vorgänge  
 Bitweise Operationen Werten zwei ganzzahlige Werte im Binär Formular (Basis 2) aus. Sie vergleichen die Bits an den entsprechenden Positionen und weisen dann basierend auf dem Vergleich Werte zu. Im folgenden Beispiel wird der `And`-Operator veranschaulicht.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Im vorangehenden Beispiel wird der Wert von `x` auf 1 festgelegt. Dies geschieht aus folgenden Gründen:  
  
- Die Werte werden als Binär Werte behandelt:  
  
     3 in binärer Form = 011  
  
     5 in binärer Form = 101  
  
- Der `And`-Operator vergleicht die binären Darstellungen, eine binäre Position (Bit) gleichzeitig. Wenn beide Bits an einer bestimmten Position 1 sind, wird ein 1 an dieser Position im Ergebnis platziert. Wenn ein Bit 0 (null) ist, wird ein Wert von 0 an dieser Position im Ergebnis eingefügt. Im vorangehenden Beispiel funktioniert dies wie folgt:  
  
     011 (3 in binärer Form)  
  
     101 (5 in binärer Form)  
  
     001 (das Ergebnis, in binärer Form)  
  
- Das Ergebnis wird als Dezimalwert behandelt. Der Wert 001 ist die binäre Darstellung von 1, sodass `x` = 1 ist.  
  
 Der bitweise `Or` Vorgang ist ähnlich, mit der Ausnahme, dass dem Ergebnisbit 1 zugewiesen wird, wenn eine oder beide der verglichenen Bits 1 sind. `Xor` weist dem Ergebnisbit den Wert 1 zu, wenn genau eines der verglichenen Bits (nicht beides) 1 ist. `Not` nimmt einen einzelnen Operanden an und kehrt alle Bits (einschließlich des Signier Bits) um und weist diesen Wert dem Ergebnis zu. Dies bedeutet, dass `Not` für positive Zahlen mit Vorzeichen immer einen negativen Wert zurückgibt, und bei negativen Zahlen gibt `Not` immer einen positiven oder NULL-Wert zurück.  
  
 Bitweise Vorgänge werden von den Operatoren `AndAlso` und `OrElse` nicht unterstützt.  
  
> [!NOTE]
> Bitweise Vorgänge können nur für ganzzahlige Typen ausgeführt werden. Gleit Komma Werte müssen in ganzzahlige Typen konvertiert werden, bevor die bitweise Operation fortgesetzt werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Verkettungs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
