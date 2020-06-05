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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404588"
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

Dieser Artikel enthält einige Beispiele, in denen die Verwendung von veranschaulicht wird `If` .. `Then` . ...`Else` an

- [Beispiel für mehrzeilige Syntax](#multi-line)
- [Beispiel für eine Beispiel Syntax](#nested)
- [Beispiel für einzeilige Syntax](#single-line)

## <a name="parts"></a>Bestandteile

`condition` \
Erforderlich. Ausdruck Muss zu `True` oder `False` oder zu einem Datentyp ausgewertet werden, der implizit in konvertierbar ist `Boolean` .

Wenn der Ausdruck eine Variable ist, die [NULL-Werte](../../programming-guide/language-features/data-types/nullable-value-types.md) zulässt, die als "Nothing" ausgewertet wird `Boolean` , wird die Bedingung so behandelt, als wäre der Ausdruck [Nothing](../nothing.md) `False` , und die `ElseIf` Blöcke werden ausgewertet, wenn Sie vorhanden sind, oder der `Else` Block wird ausgeführt, wenn er vorhanden ist.

`Then` \
Erforderlich in der einzeiligen Syntax; optional in der mehrzeiligen Syntax.

`statements` \
Optional. Eine oder mehrere-Anweisungen `If` `Then` , die ausgeführt werden, wenn `condition` zu ausgewertet wird `True` .

`elseifcondition` \
Erforderlich, wenn `ElseIf` vorhanden ist. Ausdruck Muss zu `True` oder `False` oder zu einem Datentyp ausgewertet werden, der implizit in konvertierbar ist `Boolean` .

`elseifstatements` \
Optional. Eine oder mehrere-Anweisungen `ElseIf` `Then` , die ausgeführt werden, wenn `elseifcondition` zu ausgewertet wird `True` .

`elsestatements` \
Optional. Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn kein vorheriger- `condition` oder- `elseifcondition` Ausdruck als ausgewertet wird `True` .

`End If` \
Beendet die mehrzeilige Version von `If` ... `Then` ...`Else` Baustein.

## <a name="remarks"></a>Bemerkungen

### <a name="multiline-syntax"></a>Mehrzeilige Syntax

Wenn ein `If` ... `Then` ...`Else` -Anweisung gefunden wurde, `condition` wird getestet. Wenn `condition` `True` den Wert hat, werden die folgenden Anweisungen `Then` ausgeführt. Wenn den Wert `condition` `False` hat, wird jede- `ElseIf` Anweisung (sofern vorhanden) in der richtigen Reihenfolge ausgewertet. Wenn eine `True` `elseifcondition` gefunden wird, werden die Anweisungen, die unmittelbar auf die zugeordneten folgen, `ElseIf` ausgeführt. Wenn keine `elseifcondition` ausgewertet `True` wird oder wenn keine-Anweisungen vorhanden sind `ElseIf` , werden die folgenden Anweisungen `Else` ausgeführt. Nach dem Ausführen der Anweisungen `Then` , die nach, `ElseIf` oder ausgeführt `Else` werden, wird die Ausführung mit der folgenden Anweisung fortgesetzt `End If` .

Die `ElseIf` `Else` Klauseln und sind optional. Sie können beliebig viele `ElseIf` Klauseln in einem `If` ... `Then` ...`Else` -Anweisung, aber keine- `ElseIf` Klausel kann nach einer-Klausel angezeigt werden `Else` . `If`...`Then` ...`Else` -Anweisungen können ineinander geschachtelt werden.

In der mehrzeiligen Syntax muss die- `If` Anweisung die einzige Anweisung in der ersten Zeile sein. Der `ElseIf` `Else` -,-und- `End If` Anweisung kann nur eine Zeilen Bezeichnung vorangestellt werden. Die `If` ... `Then` ...`Else` Block muss mit einer- `End If` Anweisung enden.

> [!TIP]
> Die [SELECT... Die Case-Anweisung](select-case-statement.md) ist möglicherweise nützlicher, wenn Sie einen einzelnen Ausdruck mit mehreren möglichen Werten auswerten.

### <a name="single-line-syntax"></a>Einzeilige Syntax

Sie können die einzeilige Syntax für eine einzelne Bedingung mit Code verwenden, der ausgeführt wird, wenn der Wert true ist. Die mehrzeilige Syntax bietet jedoch mehr Struktur und Flexibilität und ist leichter zu lesen, zu warten und zu debuggen.

Wie das- `Then` Schlüsselwort folgt, wird überprüft, um zu bestimmen, ob eine-Anweisung eine einzeilige ist `If` . Wenn etwas anderes als ein Kommentar nach `Then` in derselben Zeile angezeigt wird, wird die-Anweisung als einzeilige `If` Anweisung behandelt. Wenn nicht `Then` vorhanden ist, muss es sich um den Anfang eines mehrzeiligen `If` ... `Then` ...`Else`.

In der einzeiligen Syntax können mehrere-Anweisungen als Ergebnis einer `If` ...-Entscheidung ausgeführt werden `Then` . Alle-Anweisungen müssen sich in derselben Zeile befinden und durch Doppelpunkte getrennt werden.

## <a name="multiline-syntax-example"></a>Beispiel für mehrzeilige Syntax

<a name="multi-line"></a>

Das folgende Beispiel veranschaulicht die Verwendung der mehrzeiligen Syntax von `If` ... `Then` ...`Else` an.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Beispiel für eine Beispiel Syntax

<a name="nested"></a>

Das folgende Beispiel enthält die-Tabelle `If` ... `Then` ...`Else` Äußerungen.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Beispiel für einzeilige Syntax

<a name="single-line"></a>Im folgenden Beispiel wird die Verwendung der einzeiligen Syntax veranschaulicht.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If...Then...#Else-Anweisungen](../directives/if-then-else-directives.md)
- [Select...Case-Anweisung](select-case-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Entscheidungsstrukturen](../../programming-guide/language-features/control-flow/decision-structures.md)
- [Logische und bitweise Operatoren in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [If-Operator](../operators/if-operator.md)
