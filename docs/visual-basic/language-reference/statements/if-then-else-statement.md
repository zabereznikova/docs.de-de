---
title: If...Then...Else-Anweisung (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 97ac8c82df14eb5ddc5e26fdaddf61cc774a0476
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046573"
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else-Anweisung (Visual Basic)

Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.

## <a name="syntax"></a>Syntax

```
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a>Quick Links zum Beispielcode

Dieser Artikel enthält einige Beispiele, in denen die `If`Verwendung von veranschaulicht wird... `Then`... `Else` Anweisung:

* [Beispiel für mehrzeilige Syntax](#multi-line)
* [Beispiel für eine Beispiel Syntax](#nested)
* [Beispiel für einzeilige Syntax](#single-line)

## <a name="parts"></a>Teile

`condition` \
Erforderlich. Begriff. Muss zu `True` oder `False`oder zu einem Datentyp ausgewertet werden, der implizit in `Boolean`konvertierbar ist.

Wenn der Ausdruck eine Variable ist, die [null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` `False` -Werte zulässt, die als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird die Bedingung so behandelt, als ob der Ausdruck und der `Else` -Block ausgeführt wird.

`Then` \
Erforderlich in der einzeiligen Syntax; optional in der mehrzeiligen Syntax.

`statements` \
Optional. Mindestens eine-Anweisung folgt `If`... , die ausgeführt wird, wenn `True`zu ausgewertet wird `condition`. `Then`

`elseifcondition` \
Erforderlich, `ElseIf` wenn vorhanden ist. Begriff. Muss zu `True` oder `False`oder zu einem Datentyp ausgewertet werden, der implizit in `Boolean`konvertierbar ist.

`elseifstatements` \
Optional. Mindestens eine-Anweisung folgt `ElseIf`... , die ausgeführt wird, wenn `True`zu ausgewertet wird `elseifcondition`. `Then`

`elsestatements` \
Optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, `condition` Wenn `elseifcondition` kein vorheriger- `True`oder-Ausdruck als ausgewertet wird.

`End If` \
Beendet die mehrzeilige Version `If`von... `Then`... `Else` blockieren.

## <a name="remarks"></a>Hinweise

### <a name="multiline-syntax"></a>Mehrzeilige Syntax

Wenn ein `If`... `Then`... -Anweisung gefunden wurde `condition` , wird getestet. `Else` Wenn `condition`den Wert `Then` hat, werden die folgenden Anweisungen ausgeführt. `True` Wenn `condition`den Wert `ElseIf` hat, wird jede-Anweisung (sofern vorhanden) in der richtigen Reihenfolge ausgewertet. `False` Wenn eine `True` `elseifcondition` gefunden wird, werden die Anweisungen, die unmittelbar `ElseIf` auf die zugeordneten folgen, ausgeführt. Wenn keine `elseifcondition` `ElseIf` ausgewertet wird oder wenn keine-Anweisungen vorhanden sind, werden die folgenden `Else` Anweisungen ausgeführt. `True` Nach dem Ausführen der Anweisungen `Then`, `ElseIf`die nach `Else`, oder ausgeführt werden, wird die `End If`Ausführung mit der folgenden Anweisung fortgesetzt.

Die `ElseIf` Klauseln `Else` und sind optional. Sie können beliebig viele `ElseIf` Klauseln in einem `If`... `Then`... -Anweisung, aber `ElseIf` keine-Klausel kann nach `Else` einer-Klausel angezeigt werden. `Else` `If`... `Then`... `Else` -Anweisungen können ineinander geschachtelt werden.

In der mehrzeiligen Syntax muss `If` die-Anweisung die einzige Anweisung in der ersten Zeile sein. Der `ElseIf`- `Else`,- `End If` und-Anweisung kann nur eine Zeilen Bezeichnung vorangestellt werden. Die `If`... `Then`... Block muss mit einer `End If` -Anweisung enden. `Else`

> [!TIP]
> Die [SELECT... Die Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) ist möglicherweise nützlicher, wenn Sie einen einzelnen Ausdruck mit mehreren möglichen Werten auswerten.

### <a name="single-line-syntax"></a>Einzeilige Syntax

Sie können die einzeilige Syntax für eine einzelne Bedingung mit Code verwenden, der ausgeführt wird, wenn der Wert true ist. Die mehrzeilige Syntax bietet jedoch mehr Struktur und Flexibilität und ist leichter zu lesen, zu warten und zu debuggen.

Wie das `Then` -Schlüsselwort folgt, wird überprüft, um zu bestimmen, ob eine `If`-Anweisung eine einzeilige ist. Wenn etwas anderes als ein Kommentar nach `Then` in derselben Zeile angezeigt wird, wird die-Anweisung als einzeilige `If` Anweisung behandelt. Wenn `Then` nicht vorhanden ist, muss es sich um den Anfang eines mehrzeiligen `If`... `Then`... `Else`.

In der einzeiligen Syntax können mehrere-Anweisungen als Ergebnis eines `If`... `Then` Entscheidung. Alle-Anweisungen müssen sich in derselben Zeile befinden und durch Doppelpunkte getrennt werden.

## <a name="multiline-syntax-example"></a>Beispiel für mehrzeilige Syntax

<a name="multi-line"></a>

Das folgende Beispiel veranschaulicht die Verwendung der mehrzeiligen Syntax von `If`... `Then`... `Else` -Anweisung.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Beispiel für eine Beispiel Syntax

<a name="nested"></a>

Das folgende Beispiel enthält `If`die-Tabelle... `Then`... `Else` -Anweisungen.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Beispiel für einzeilige Syntax

<a name="single-line"></a>Im folgenden Beispiel wird die Verwendung der einzeiligen Syntax veranschaulicht.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Entscheidungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)
