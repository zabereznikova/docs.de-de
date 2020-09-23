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
ms.openlocfilehash: c15b9337f262563941699c0ff8fe5219ca6a5c93
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085996"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Logische und bitweise Operatoren in Visual Basic

Logische Operatoren vergleichen `Boolean` Ausdrücke und geben ein `Boolean` Ergebnis zurück. Die `And` `Or` `AndAlso` Operatoren,,, `OrElse` und `Xor` sind *Binär* , da Sie zwei Operanden annehmen, während der `Not` Operator *unär* ist, da er einen einzelnen Operanden annimmt. Einige dieser Operatoren können auch bitweise logische Operationen für ganzzahlige Werte ausführen.  
  
## <a name="unary-logical-operator"></a>Unärer logischer Operator  

 Der [Not-Operator](../../../language-reference/operators/not-operator.md) führt eine logische *Negation* für einen- `Boolean` Ausdruck aus. Es ergibt das logische Gegenteil des Operanden. Wenn der Ausdruck ergibt `True` , wird `Not` zurückgegeben `False` . wenn der Ausdruck ergibt `False` , wird zurückgegeben `Not` `True` . Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>Binäre logische Operatoren  

 Der [and-Operator](../../../language-reference/operators/and-operator.md) führt eine logische *Konjunktion* zweier `Boolean` Ausdrücke aus. Wenn beide Ausdrücke als ausgewertet `True` werden, `And` gibt zurück `True` . Wenn mindestens einer der Ausdrücke als ausgewertet `False` wird, wird `And` zurückgegeben `False` .  
  
 Der [OR-Operator](../../../language-reference/operators/or-operator.md) führt eine logische *Disjunktion* oder die *Einbindung* zweier `Boolean` Ausdrücke aus. Wenn einer der Ausdrücke ergibt `True` oder beide als ausgewertet `True` werden, `Or` gibt zurück `True` . Wenn keiner der Ausdrücke ergibt `True` , wird `Or` zurückgegeben `False` .  
  
 Der [Xor-Operator](../../../language-reference/operators/xor-operator.md) führt einen logischen *Ausschluss* für zwei `Boolean` Ausdrücke aus. Wenn genau ein Ausdruck ergibt `True` , aber nicht beides, wird `Xor` zurückgegeben `True` . Wenn beide Ausdrücke als ausgewertet `True` werden oder beide als ausgewertet `False` werden, `Xor` gibt zurück `False` .  
  
 Im folgenden Beispiel werden die `And` `Or` Operatoren, und veranschaulicht `Xor` .  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Kurzschluss logische Vorgänge  

 Der [andwas-Operator](../../../language-reference/operators/andalso-operator.md) ist dem-Operator sehr ähnlich `And` , da er auch eine logische Konjunktion für zwei `Boolean` Ausdrücke ausführt. Der Hauptunterschied zwischen den beiden besteht darin, dass das `AndAlso` *Kurzschluss* Verhalten aufweist. Wenn der erste Ausdruck in einem `AndAlso` Ausdruck als `False` ausgewertet wird, wird der zweite Ausdruck nicht ausgewertet, da er das Endergebnis nicht ändern kann, und `AndAlso` gibt zurück `False` .  
  
 Entsprechend führt der [OrElse-Operator](../../../language-reference/operators/orelse-operator.md) eine Kurzschluss logische Disjunktion für zwei `Boolean` Ausdrücke aus. Wenn der erste Ausdruck in einem `OrElse` Ausdruck als `True` ausgewertet wird, wird der zweite Ausdruck nicht ausgewertet, da er das Endergebnis nicht ändern kann, und `OrElse` gibt zurück `True` .  
  
### <a name="short-circuiting-trade-offs"></a>Kurze Schluss Kompromisse  

 Kurzschluss Vorgänge können die Leistung verbessern, indem Sie keinen Ausdruck auswerten, der das Ergebnis der logischen Operation nicht ändern kann. Wenn dieser Ausdruck jedoch weitere Aktionen ausführt, überspringt der Kurzschluss diese Aktionen. Wenn der Ausdruck z. b. einen Aufruf einer `Function` Prozedur enthält, wird diese Prozedur nicht aufgerufen, wenn der Ausdruck kurzgeschlossen wird, und jeglicher zusätzlicher Code, der in der enthalten ist, wird `Function` nicht ausgeführt. Daher kann die Funktion nur gelegentlich ausgeführt werden und wird möglicherweise nicht ordnungsgemäß getestet. Oder die Programmlogik hängt möglicherweise vom Code in der ab `Function` .  
  
 Das folgende Beispiel veranschaulicht den Unterschied zwischen `And` , `Or` und ihren Kurzschluss Entsprechungen.  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 Beachten Sie im vorhergehenden Beispiel, dass einige wichtige Codes in `checkIfValid()` nicht ausgeführt werden, wenn der-Befehl kurzgeschlossen wird. Die erste `If` Anweisung ruft auf `checkIfValid()` `12 > 45` , obwohl zurückgibt `False` , da `And` keine Kurzschluss ist. Mit der zweiten `If` Anweisung wird nicht aufgerufen `checkIfValid()` , da bei `12 > 45` Rückgabe von `False` `AndAlso` der zweite Ausdruck kurz ist. Die dritte- `If` Anweisung `checkIfValid()` wird aufgerufen `12 < 45` , obwohl zurückgibt `True` , da `Or` keine Kurzschluss ist. In der vierten `If` Anweisung wird nicht aufgerufen `checkIfValid()` , da bei `12 < 45` Rückgabe von `True` `OrElse` der zweite Ausdruck kurz ist.  
  
## <a name="bitwise-operations"></a>Bitweise Vorgänge  

 Bitweise Operationen Werten zwei ganzzahlige Werte im Binär Formular (Basis 2) aus. Sie vergleichen die Bits an den entsprechenden Positionen und weisen dann basierend auf dem Vergleich Werte zu. Im folgenden Beispiel wird der- `And` Operator veranschaulicht.  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 Im vorangehenden Beispiel wird der Wert von `x` auf 1 festgelegt. Dies geschieht aus folgenden Gründen:  
  
- Die Werte werden als Binär Werte behandelt:  
  
     3 in binärer Form = 011  
  
     5 in binärer Form = 101  
  
- Der `And` Operator vergleicht die binären Darstellungen, eine binäre Position (Bit) gleichzeitig. Wenn beide Bits an einer bestimmten Position 1 sind, wird ein 1 an dieser Position im Ergebnis platziert. Wenn ein Bit 0 (null) ist, wird ein Wert von 0 an dieser Position im Ergebnis eingefügt. Im vorangehenden Beispiel funktioniert dies wie folgt:  
  
     011 (3 in binärer Form)  
  
     101 (5 in binärer Form)  
  
     001 (das Ergebnis, in binärer Form)  
  
- Das Ergebnis wird als Dezimalwert behandelt. Der Wert 001 ist die binäre Darstellung von 1, sodass `x` = 1 ist.  
  
 Der `Or` bitweise Vorgang ist ähnlich, mit der Ausnahme, dass dem Ergebnisbit 1 zugewiesen wird, wenn eine oder beide der verglichenen Bits 1 sind. `Xor` weist dem Ergebnisbit 1 zu, wenn genau eines der verglichenen Bits (nicht beides) 1 ist. `Not` nimmt einen einzelnen Operanden an und kehrt alle Bits einschließlich des Signier Bits um und weist diesen Wert dem Ergebnis zu. Dies bedeutet, dass für positive Zahlen mit Vorzeichen `Not` immer einen negativen Wert zurückgibt, und bei negativen Zahlen wird `Not` immer ein positiver oder NULL-Wert zurückgegeben.  
  
 `AndAlso` `OrElse` Bitweise Vorgänge werden von den Operatoren und nicht unterstützt.  
  
> [!NOTE]
> Bitweise Vorgänge können nur für ganzzahlige Typen ausgeführt werden. Gleit Komma Werte müssen in ganzzahlige Typen konvertiert werden, bevor die bitweise Operation fortgesetzt werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [Boolesche Ausdrücke](boolean-expressions.md)
- [Arithmetische Operatoren in Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Verkettungsoperatoren in Visual Basic](concatenation-operators.md)
- [Effiziente Kombination von Operatoren](efficient-combination-of-operators.md)
