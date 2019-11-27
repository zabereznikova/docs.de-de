---
title: If...Then...Else-Anweisung
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
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351165"
---
# <a name="ifthenelse-statement-visual-basic"></a>If...Then...Else-Anweisung (Visual Basic)

Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.

## <a name="syntax"></a>Syntax

```vb
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

Dieser Artikel enthält einige Beispiele, die die Verwendung der `If`...`Then`...`Else`-Anweisung veranschaulichen:

- [Beispiel für mehrzeilige Syntax](#multi-line)
- [Beispiel für eine Beispiel Syntax](#nested)
- [Beispiel für einzeilige Syntax](#single-line)

## <a name="parts"></a>-Komponenten

`condition` \
Erforderlich Begriff. Muss zu `True` oder `False`oder zu einem Datentyp ausgewertet werden, der implizit in `Boolean`konvertiert werden kann.

Wenn der Ausdruck eine `Boolean` Variable ist, die [NULL-Werte](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) zulässt, die als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird die Bedingung so behandelt, als wäre der Ausdruck `False`, und die `ElseIf` Blöcke werden ausgewertet, wenn Sie vorhanden sind, oder der `Else` Block wird ausgeführt, wenn er vorhanden ist.

`Then` \
Erforderlich in der einzeiligen Syntax; optional in der mehrzeiligen Syntax.

`statements` \
Optional. Mindestens eine-Anweisung nach `If`...`Then`, die ausgeführt werden, wenn `condition` als `True`ausgewertet wird.

`elseifcondition` \
Erforderlich, wenn `ElseIf` vorhanden ist. Begriff. Muss zu `True` oder `False`oder zu einem Datentyp ausgewertet werden, der implizit in `Boolean`konvertiert werden kann.

`elseifstatements` \
Optional. Mindestens eine-Anweisung nach `ElseIf`...`Then`, die ausgeführt werden, wenn `elseifcondition` als `True`ausgewertet wird.

`elsestatements` \
Optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn kein vorheriger `condition` oder `elseifcondition` Ausdruck zu `True`ausgewertet wird.

`End If` \
Beendet die mehrzeilige Version von `If`...`Then`...`Else` Block.

## <a name="remarks"></a>Hinweise

### <a name="multiline-syntax"></a>Mehrzeilige Syntax

Wenn eine `If`...`Then`...`Else`-Anweisung gefunden wird, wird `condition` getestet. Wenn `condition` `True`ist, werden die Anweisungen, die nach `Then` ausgeführt werden, ausgeführt. Wenn `condition` `False`ist, wird jede `ElseIf`-Anweisung (sofern vorhanden) in der richtigen Reihenfolge ausgewertet. Wenn ein `True` `elseifcondition` gefunden wird, werden die Anweisungen, die unmittelbar auf die zugeordneten `ElseIf` folgen, ausgeführt. Wenn keine `elseifcondition` als `True`ausgewertet wird oder wenn keine `ElseIf`-Anweisungen vorhanden sind, werden die folgenden Anweisungen ausgeführt `Else`. Nach dem Ausführen der Anweisungen, die nach `Then`, `ElseIf`oder `Else`ausgeführt werden, wird die Ausführung mit der folgenden Anweisung fortgesetzt: `End If`.

Die Klauseln `ElseIf` und `Else` sind optional. Sie können beliebig viele `ElseIf` Klauseln in einer `If`...`Then`...`Else`-Anweisung haben, aber nach einer `ElseIf`-Klausel kann keine `Else`-Klausel angezeigt werden. `If`...`Then`...`Else`-Anweisungen können ineinander geschachtelt werden.

In der mehrzeiligen Syntax muss die `If`-Anweisung die einzige Anweisung in der ersten Zeile sein. Der `ElseIf`-, `Else`-und `End If`-Anweisung kann nur eine Zeilen Bezeichnung vorangestellt werden. Der `If`...`Then`...`Else`-Block muss mit einer `End If`-Anweisung enden.

> [!TIP]
> Die [SELECT... Die Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) ist möglicherweise nützlicher, wenn Sie einen einzelnen Ausdruck mit mehreren möglichen Werten auswerten.

### <a name="single-line-syntax"></a>Einzeilige Syntax

Sie können die einzeilige Syntax für eine einzelne Bedingung mit Code verwenden, der ausgeführt wird, wenn der Wert true ist. Die mehrzeilige Syntax bietet jedoch mehr Struktur und Flexibilität und ist leichter zu lesen, zu warten und zu debuggen.

Das `Then`-Schlüsselwort wird untersucht, um zu bestimmen, ob eine-Anweisung eine einzeilige `If`ist. Wenn nach `Then` in derselben Zeile etwas anderes als ein Kommentar angezeigt wird, wird die Anweisung als einzeilige `If` Anweisung behandelt. Wenn `Then` nicht vorhanden ist, muss es sich um den Anfang eines mehrzeiligen `If`...`Then`...`Else`.

In der einzeiligen Syntax können mehrere-Anweisungen als Ergebnis einer `If`...`Then` Entscheidung ausgeführt werden. Alle-Anweisungen müssen sich in derselben Zeile befinden und durch Doppelpunkte getrennt werden.

## <a name="multiline-syntax-example"></a>Beispiel für mehrzeilige Syntax

<a name="multi-line"></a>

Im folgenden Beispiel wird die Verwendung der mehrzeiligen Syntax der `If`...`Then`...`Else`-Anweisung veranschaulicht.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Beispiel für eine Beispiel Syntax

<a name="nested"></a>

Das folgende Beispiel enthält die `If`...`Then`...`Else`-Anweisungen.

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
