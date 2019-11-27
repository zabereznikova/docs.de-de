---
title: Operator If
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
ms.openlocfilehash: 6d25519dac31dc91f8560fd3252ba3e2622de370
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331018"
---
# <a name="if-operator-visual-basic"></a>If-Operator (Visual Basic)

Verwendet die Kurzschluss Auswertung, um einen von zwei Werten bedingt zurückzugeben. Der `If`-Operator kann mit drei Argumenten oder mit zwei Argumenten aufgerufen werden.

## <a name="syntax"></a>Syntax

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>If-Operator mit drei Argumenten aufgerufen

Wenn `If` mithilfe von drei Argumenten aufgerufen wird, muss das erste Argument einen Wert ergeben, der als `Boolean`umgewandelt werden kann. Durch diesen `Boolean` Wert wird festgelegt, welche der beiden anderen Argumente ausgewertet und zurückgegeben werden. Die folgende Liste gilt nur, wenn der `If`-Operator mit drei Argumenten aufgerufen wird.

### <a name="parts"></a>-Komponenten

|Begriff|Definition|
|---|---|
|`argument1`|Erforderlich `Boolean`. Bestimmt, welches der anderen Argumente ausgewertet und zurückgegeben werden soll.|
|`argument2`|Erforderlich `Object`. Wird ausgewertet und zurückgegeben, wenn `argument1` zu `True`ausgewertet wird.|
|`argument3`|Erforderlich `Object`. Wird ausgewertet und zurückgegeben, wenn `argument1` ergibt `False` oder wenn `argument1` eine`Boolean` Variable ist, die [NULL-Werte](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) zulässt, die zu [Nothing](../../../visual-basic/language-reference/nothing.md)ausgewertet wird.|

Ein `If` Operator, der mit drei Argumenten aufgerufen wird, funktioniert wie eine `IIf`-Funktion, mit der Ausnahme, dass Sie eine Kurzschluss Auswertung verwendet. Eine `IIf` Funktion wertet immer alle drei ihrer Argumente aus, wohingegen ein `If` Operator, der über drei Argumente verfügt, nur zwei Werte auswertet. Das erste `If` Argument wird ausgewertet, und das Ergebnis wird als `Boolean` Wert, `True` oder `False`umgewandelt. Wenn der Wert `True`ist, wird `argument2` ausgewertet und sein Wert zurückgegeben, `argument3` aber nicht ausgewertet wird. Wenn der Wert des `Boolean` Ausdrucks `False`ist, wird `argument3` ausgewertet und sein Wert zurückgegeben, `argument2` aber nicht ausgewertet wird. Die folgenden Beispiele veranschaulichen die Verwendung von `If`, wenn drei Argumente verwendet werden:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

Im folgenden Beispiel wird der Wert der Kurzschluss Auswertung veranschaulicht. Das Beispiel zeigt zwei Versuche, Variablen `number` durch Variable aufzuteilen `divisor`, außer wenn `divisor` 0 (null) ist. In diesem Fall sollte 0 (null) zurückgegeben werden, und es sollte nicht versucht werden, die Division auszuführen, da ein Laufzeitfehler entstehen würde. Da der `If` Ausdruck eine Kurzschluss Auswertung verwendet, wertet er je nach dem Wert des ersten Arguments entweder das zweite oder das dritte Argument aus. Wenn das erste Argument true ist, ist der Divisor nicht NULL, und es ist sicher, das zweite Argument auszuwerten und die Division auszuführen. Wenn das erste Argument false ist, wird nur das dritte Argument ausgewertet, und es wird 0 zurückgegeben. Wenn der Divisor also 0 ist, wird nicht versucht, die Division und keine Fehler Ergebnisse auszuführen. Da `IIf` jedoch keine Kurzschluss Auswertung verwendet, wird das zweite Argument auch dann ausgewertet, wenn das erste Argument false ist. Dies führt zu einem Laufzeitfehler aufgrund einer Division durch 0 (null).

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>If-Operator mit zwei Argumenten aufgerufen

Das erste Argument für `If` kann weggelassen werden. Dadurch kann der Operator nur mit zwei Argumenten aufgerufen werden. Die folgende Liste gilt nur, wenn der `If`-Operator mit zwei Argumenten aufgerufen wird.

### <a name="parts"></a>-Komponenten

|Begriff|Definition|
|---|---|
|`argument2`|Erforderlich `Object`. Muss ein Verweis oder ein Typ sein, der NULL-Werte zulässt. Wird ausgewertet und zurückgegeben, wenn es etwas anderes als `Nothing`ausgewertet wird.|
|`argument3`|Erforderlich `Object`. Wird ausgewertet und zurückgegeben, wenn `argument2` zu `Nothing`ausgewertet wird.|

Wenn das `Boolean`-Argument weggelassen wird, muss das erste Argument ein Verweis oder ein Typ sein, der NULL-Werte zulässt. Wenn das erste Argument als `Nothing`ausgewertet wird, wird der Wert des zweiten Arguments zurückgegeben. In allen anderen Fällen wird der Wert des ersten Arguments zurückgegeben. Im folgenden Beispiel wird veranschaulicht, wie diese Auswertung funktioniert:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
