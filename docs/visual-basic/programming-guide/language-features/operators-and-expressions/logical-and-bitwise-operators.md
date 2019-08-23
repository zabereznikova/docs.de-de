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
ms.openlocfilehash: 40076b2ad6606b4c565bcd39dbeea9e55da47211
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963315"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Logische und bitweise Operatoren in Visual Basic
Logische Operatoren `Boolean` vergleichen Ausdrücke und geben `Boolean` ein Ergebnis zurück. Die `And`Operatoren `AndAlso`, `Or` `Not` ,, `OrElse` und`Xor` sind *Binär* , da Sie zwei Operanden annehmen, während der Operator *unär* ist, da er einen einzelnen Operanden annimmt. Einige dieser Operatoren können auch bitweise logische Operationen für ganzzahlige Werte ausführen.  
  
## <a name="unary-logical-operator"></a>Unärer logischer Operator  
 Der [Not-Operator](../../../../visual-basic/language-reference/operators/not-operator.md) führt eine logische Negation `Boolean` für einen-Ausdruck aus. Es ergibt das logische Gegenteil des Operanden. `True`Wenn der Ausdruck ergibt `Not` , wird zurück `False`gegeben. wenn der Ausdruck `False`ergibt, wird `Not` zurück `True`gegeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Binäre logische Operatoren  
 Der [and-Operator](../../../../visual-basic/language-reference/operators/and-operator.md) führt eine logische *Konjunktion* zweier `Boolean` Ausdrücke aus. Wenn beide Ausdrücke als `True`ausgewertet `And` werden, gibt `True`zurück. Wenn mindestens einer der Ausdrücke als `False`ausgewertet `And` wird, wird zurück `False`gegeben.  
  
 Der [OR-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) führt eine logische Disjunktion oder `Boolean` die *Einbindung* zweier Ausdrücke aus. Wenn einer der `True`Ausdrücke ergibt oder beide als `True`ausgewertet werden `Or` , gibt zurück `True`. Wenn keiner der Ausdrücke `True`ergibt, wird `False` `Or` zurückgegeben.  
  
 Der [Xor-Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) führt einen logischen Ausschluss `Boolean` für zwei Ausdrücke aus. Wenn genau ein Ausdruck `True`ergibt, aber nicht `Xor` beides, wird zurück `True`gegeben. Wenn beide Ausdrücke als ausgewertet `True` `False`werden oder beide als ausgewertet `Xor` werden `False`, gibt zurück.  
  
 Im folgenden Beispiel werden die `And`Operatoren, `Xor` `Or`und veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Kurzschluss logische Vorgänge  
 Der [andwas-Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) ist dem `And` -Operator sehr ähnlich, da er auch eine logische Konjunktion für zwei `Boolean` Ausdrücke ausführt. Der Hauptunterschied zwischen den beiden besteht darin `AndAlso` , dass das *Kurzschluss* Verhalten aufweist. Wenn der erste Ausdruck in einem `AndAlso` Ausdruck als `False`ausgewertet wird, wird der zweite Ausdruck nicht ausgewertet, da er das Endergebnis nicht ändern kann, `AndAlso` und `False`gibt zurück.  
  
 Entsprechend führt der [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) eine Kurzschluss logische Disjunktion für zwei `Boolean` Ausdrücke aus. Wenn der erste Ausdruck in einem `OrElse` Ausdruck als `True`ausgewertet wird, wird der zweite Ausdruck nicht ausgewertet, da er das Endergebnis nicht ändern kann, `OrElse` und `True`gibt zurück.  
  
### <a name="short-circuiting-trade-offs"></a>Kurze Schluss Kompromisse  
 Kurzschluss Vorgänge können die Leistung verbessern, indem Sie keinen Ausdruck auswerten, der das Ergebnis der logischen Operation nicht ändern kann. Wenn dieser Ausdruck jedoch weitere Aktionen ausführt, überspringt der Kurzschluss diese Aktionen. Wenn der Ausdruck z. b. einen Aufruf `Function` einer Prozedur enthält, wird diese Prozedur nicht aufgerufen, wenn der Ausdruck kurzgeschlossen wird, und jeglicher zusätzlicher Code, der in der `Function` enthalten ist, wird nicht ausgeführt. Daher kann die Funktion nur gelegentlich ausgeführt werden und wird möglicherweise nicht ordnungsgemäß getestet. Oder die Programmlogik hängt möglicherweise vom Code in der `Function`ab.  
  
 Das folgende Beispiel veranschaulicht den Unterschied `And`zwischen `Or`, und ihren Kurzschluss Entsprechungen.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Beachten Sie im vorhergehenden Beispiel, dass einige wichtige Codes `checkIfValid()` in nicht ausgeführt werden, wenn der-Befehl kurzgeschlossen wird. Die erste `If` Anweisung ruft `checkIfValid()` auf, `12 > 45` Obwohl `False`zurückgibt `And` , da keine Kurzschluss ist. Mit der `If` zweiten Anweisung wird nicht `checkIfValid()`aufgerufen, da `12 > 45` bei `False`Rückgabe `AndAlso` von der zweite Ausdruck kurz ist. Die dritte `If` -Anweisung `checkIfValid()` wird aufgerufen `12 < 45` , `True`obwohl zurück `Or` gibt, da keine Kurzschluss ist. In der `If` vierten Anweisung wird nicht `checkIfValid()`aufgerufen, da `12 < 45` bei `True`Rückgabe `OrElse` von der zweite Ausdruck kurz ist.  
  
## <a name="bitwise-operations"></a>Bitweise Vorgänge  
 Bitweise Operationen Werten zwei ganzzahlige Werte im Binär Formular (Basis 2) aus. Sie vergleichen die Bits an den entsprechenden Positionen und weisen dann basierend auf dem Vergleich Werte zu. Im folgenden Beispiel wird der `And` -Operator veranschaulicht.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Im vorangehenden Beispiel wird der Wert `x` von auf 1 festgelegt. Dies geschieht aus folgenden Gründen:  
  
- Die Werte werden als Binär Werte behandelt:  
  
     3 in binärer Form = 011  
  
     5 in binärer Form = 101  
  
- Der `And` Operator vergleicht die binären Darstellungen, eine binäre Position (Bit) gleichzeitig. Wenn beide Bits an einer bestimmten Position 1 sind, wird ein 1 an dieser Position im Ergebnis platziert. Wenn ein Bit 0 (null) ist, wird ein Wert von 0 an dieser Position im Ergebnis eingefügt. Im vorangehenden Beispiel funktioniert dies wie folgt:  
  
     011 (3 in binärer Form)  
  
     101 (5 in binärer Form)  
  
     001 (das Ergebnis, in binärer Form)  
  
- Das Ergebnis wird als Dezimalwert behandelt. Der Wert 001 ist die binäre Darstellung von 1, sodass `x` = 1 ist.  
  
 Der `Or` bitweise Vorgang ist ähnlich, mit der Ausnahme, dass dem Ergebnisbit 1 zugewiesen wird, wenn eine oder beide der verglichenen Bits 1 sind. `Xor`weist dem Ergebnisbit 1 zu, wenn genau eines der verglichenen Bits (nicht beides) 1 ist. `Not`nimmt einen einzelnen Operanden an und kehrt alle Bits einschließlich des Signier Bits um und weist diesen Wert dem Ergebnis zu. Dies bedeutet, dass für positive Zahlen `Not` mit Vorzeichen immer einen negativen Wert zurückgibt, und bei negativen Zahlen wird `Not` immer ein positiver oder NULL-Wert zurückgegeben.  
  
 Bitweise `OrElse` Vorgänge werden von den `AndAlso` Operatoren und nicht unterstützt.  
  
> [!NOTE]
> Bitweise Vorgänge können nur für ganzzahlige Typen ausgeführt werden. Gleit Komma Werte müssen in ganzzahlige Typen konvertiert werden, bevor die bitweise Operation fortgesetzt werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Boolesche Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [Arithmetische Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Vergleichs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Verkettungs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
