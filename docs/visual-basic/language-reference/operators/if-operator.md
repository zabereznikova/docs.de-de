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
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249486"
---
# <a name="if-operator-visual-basic"></a>If-Operator (Visual Basic)

Verwendet Kurzschlussauswertung, um bedingt einen von zwei Werten zurückzugeben. Der `If` Operator kann mit drei Argumenten oder mit zwei Argumenten aufgerufen werden.

## <a name="syntax"></a>Syntax

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>Wenn Operator mit drei Argumenten aufgerufen wird

Wenn `If` das erste Argument mit drei Argumenten aufgerufen wird, muss `Boolean`es zu einem Wert ausgewertet werden, der als . Dieser `Boolean` Wert bestimmt, welches der beiden anderen Argumente ausgewertet und zurückgegeben wird. Die folgende Liste gilt `If` nur, wenn der Operator mit drei Argumenten aufgerufen wird.

### <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`argument1`|Erforderlich. `Boolean`. Bestimmt, welche der anderen Argumente ausgewertet und zurückgegeben werden sollen.|
|`argument2`|Erforderlich. `Object`. Ausgewertet und `argument1` zurückgegeben, `True`wenn ausgewertet auf .|
|`argument3`|Erforderlich. `Object`. Ausgewertet und `argument1` zurückgegeben, `False` wenn `argument1` eine [Nullable-Variable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` ausgewertet wird oder wenn sie eine Nullable-Variable ist, die [zu Nothing](../../../visual-basic/language-reference/nothing.md)ausgewertet wird.|

Ein `If` Operator, der mit drei `IIf` Argumenten aufgerufen wird, funktioniert wie eine Funktion, außer dass er eine Kurzschlussauswertung verwendet. Eine `IIf` Funktion wertet immer alle drei `If` Argumente aus, während ein Operator mit drei Argumenten nur zwei auswertet. Das `If` erste Argument wird ausgewertet, und `Boolean` das `True` `False`Ergebnis wird als Wert oder umgegossen. Wenn der `True`Wert `argument2` ist , ausgewertet wird `argument3` und sein Wert zurückgegeben, aber nicht ausgewertet wird. Wenn der Wert `Boolean` des `False` `argument3` Ausdrucks ist , wird `argument2` ausgewertet, und sein Wert wird zurückgegeben, aber nicht ausgewertet. Die folgenden Beispiele veranschaulichen die Verwendung von `If` drei Argumenten:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

Das folgende Beispiel veranschaulicht den Wert der Kurzschlussauswertung. Das Beispiel zeigt zwei `number` Versuche, `divisor` die `divisor` Variable durch variable zu dividieren, außer wenn null ist. In diesem Fall sollte eine 0 zurückgegeben werden, und es sollte kein Versuch unternommen werden, die Division auszuführen, da ein Laufzeitfehler auftreten würde. Da `If` der Ausdruck eine Kurzschlussauswertung verwendet, wertet er je nach Wert des ersten Arguments entweder das zweite oder das dritte Argument aus. Wenn das erste Argument wahr ist, ist der Divisor nicht Null und es ist sicher, das zweite Argument auszuwerten und die Division auszuführen. Wenn das erste Argument false ist, wird nur das dritte Argument ausgewertet und eine 0 zurückgegeben. Wenn der Divisor 0 ist, wird daher kein Versuch unternommen, die Division durchzuführen, und es werden keine Fehlerergebnisse erzielt. Da `IIf` jedoch keine Kurzschlussauswertung verwendet wird, wird das zweite Argument auch dann ausgewertet, wenn das erste Argument falsch ist. Dies verursacht einen Laufzeit-Divide-by-Null-Fehler.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>Wenn Operator mit zwei Argumenten aufgerufen wird

Das erste `If` Argument, das weggelassen werden soll. Dadurch kann der Operator nur mit zwei Argumenten aufgerufen werden. Die folgende Liste gilt `If` nur, wenn der Operator mit zwei Argumenten aufgerufen wird.

### <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`argument2`|Erforderlich. `Object`. Es muss ein Verweis- oder NULLwerttyp sein. Ausgewertet und zurückgegeben, wenn es `Nothing`zu etwas anderem als ausgewertet wird.|
|`argument3`|Erforderlich. `Object`. Ausgewertet und `argument2` zurückgegeben, `Nothing`wenn ausgewertet auf .|

Wenn `Boolean` das Argument weggelassen wird, muss das erste Argument ein Verweis- oder NULL-Werttyp sein. Wenn das erste Argument `Nothing`zu ausgewertet wird, wird der Wert des zweiten Arguments zurückgegeben. In allen anderen Fällen wird der Wert des ersten Arguments zurückgegeben. Das folgende Beispiel veranschaulicht, wie diese Auswertung funktioniert:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
