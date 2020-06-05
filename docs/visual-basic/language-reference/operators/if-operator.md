---
title: If-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 28fb2afb2c4cf78ffbbb028145de647a8dc512ed
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371102"
---
# <a name="if-operator-visual-basic"></a>If-Operator (Visual Basic)

Verwendet die Kurzschluss Auswertung, um einen von zwei Werten bedingt zurückzugeben. Der `If` Operator kann mit drei Argumenten oder mit zwei Argumenten aufgerufen werden.

## <a name="syntax"></a>Syntax

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>If-Operator mit drei Argumenten aufgerufen

Wenn `If` mithilfe von drei Argumenten aufgerufen wird, muss das erste Argument zu einem Wert ausgewertet werden, der als umgewandelt werden kann `Boolean` . Dieser `Boolean` Wert bestimmt, welche der beiden anderen Argumente ausgewertet und zurückgegeben werden. Die folgende Liste gilt nur, wenn der- `If` Operator mit drei Argumenten aufgerufen wird.

### <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`argument1`|Erforderlich. `Boolean`. Bestimmt, welches der anderen Argumente ausgewertet und zurückgegeben werden soll.|
|`argument2`|Erforderlich. `Object`. Wird ausgewertet und zurückgegeben, wenn zu ausgewertet wird `argument1` `True` .|
|`argument3`|Erforderlich. `Object`. Wird ausgewertet und zurückgegeben, wenn `argument1` `False` als ausgewertet wird oder wenn `argument1` eine Variable ist [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` , [Nothing](../nothing.md)die NULL-Werte zulässt|

Ein `If` Operator, der mit drei Argumenten aufgerufen wird, funktioniert wie eine `IIf` Funktion, mit der Ausnahme, dass er eine Kurzschluss Auswertung verwendet. Eine `IIf` Funktion wertet immer alle drei ihrer Argumente aus, wohingegen ein `If` Operator mit drei Argumenten nur zwei davon auswertet. Das erste `If` Argument wird ausgewertet, und das Ergebnis wird in einen- `Boolean` Wert `True` umgewandelt `False` . Wenn der Wert ist `True` , `argument2` wird ausgewertet und sein Wert zurückgegeben, aber `argument3` nicht ausgewertet. Wenn der Wert des `Boolean` Ausdrucks ist `False` , `argument3` wird ausgewertet und sein Wert zurückgegeben, aber `argument2` nicht ausgewertet. In den folgenden Beispielen wird die Verwendung von veranschaulicht, `If` Wenn drei Argumente verwendet werden:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

Im folgenden Beispiel wird der Wert der Kurzschluss Auswertung veranschaulicht. Das Beispiel zeigt zwei Versuche, Variablen durch Variable zu unterteilen, `number` `divisor` außer wenn `divisor` 0 (null) ist. In diesem Fall sollte 0 (null) zurückgegeben werden, und es sollte nicht versucht werden, die Division auszuführen, da ein Laufzeitfehler entstehen würde. Da der `If` Ausdruck eine Kurzschluss Auswertung verwendet, wertet er je nach dem Wert des ersten Arguments entweder das zweite oder das dritte Argument aus. Wenn das erste Argument true ist, ist der Divisor nicht NULL, und es ist sicher, das zweite Argument auszuwerten und die Division auszuführen. Wenn das erste Argument false ist, wird nur das dritte Argument ausgewertet, und es wird 0 zurückgegeben. Wenn der Divisor also 0 ist, wird nicht versucht, die Division und keine Fehler Ergebnisse auszuführen. Da jedoch `IIf` keine Kurzschluss Auswertung verwendet, wird das zweite Argument auch dann ausgewertet, wenn das erste Argument false ist. Dies führt zu einem Laufzeitfehler aufgrund einer Division durch 0 (null).

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>If-Operator mit zwei Argumenten aufgerufen

Das erste Argument für `If` kann weggelassen werden. Dadurch kann der Operator nur mit zwei Argumenten aufgerufen werden. Die folgende Liste gilt nur, wenn der- `If` Operator mit zwei Argumenten aufgerufen wird.

### <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`argument2`|Erforderlich. `Object`. Muss ein Verweis oder ein Werte zulässt-Werttyp sein. Wird ausgewertet und zurückgegeben, wenn es etwas anderes als ausgewertet wird `Nothing` .|
|`argument3`|Erforderlich. `Object`. Wird ausgewertet und zurückgegeben, wenn zu ausgewertet wird `argument2` `Nothing` .|

Wenn das `Boolean` Argument weggelassen wird, muss das erste Argument ein Verweis oder ein Werte zulässt-Werttyp sein. Wenn das erste Argument als ausgewertet wird `Nothing` , wird der Wert des zweiten Arguments zurückgegeben. In allen anderen Fällen wird der Wert des ersten Arguments zurückgegeben. Im folgenden Beispiel wird veranschaulicht, wie diese Auswertung funktioniert:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Nullable-Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Schweigen](../nothing.md)
