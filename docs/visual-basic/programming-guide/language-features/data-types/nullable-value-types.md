---
title: Auf NULL festlegbare Werttypen – Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: d17d2ad3fd99c6d563c21ddd646396ccb1c1ca48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008227"
---
# <a name="nullable-value-types-visual-basic"></a>Auf NULL festlegbare Werttypen (Visual Basic)

In einigen Fällen arbeiten Sie mit einem Werttyp, der nicht über einen definierten Wert unter bestimmten Umständen verfügt. Z. B. möglicherweise ein Feld in einer Datenbank zu unterscheiden, dass einen Wert zugewiesen, der sinnvoll ist, ohne dass einen Wert zugewiesen. Werttypen können erweitert werden, um entweder die normalen Werte oder ein null-Wert. Eine solche Erweiterung wird aufgerufen, eine *nullable-Typ*.

Jede nullable-Typ erstellt wird, von der generischen <xref:System.Nullable%601> Struktur. Nehmen Sie eine Datenbank, die geschäftliche Aktivitäten nachverfolgt werden soll. Das folgende Beispiel erstellt eine auf NULL festlegbare `Boolean` geben und deklariert eine Variable dieses Typs. Sie können die Deklaration gibt drei Möglichkeiten zum Schreiben:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

Die Variable `ridesBusToWork` kann einen Wert von aufzunehmen `True`, einen Wert von `False`, oder überhaupt kein Wert. Der anfängliche Standardwert ist kein Wert, der bedeuten in diesem Fall, dass sich die Informationen noch nicht für diese Person abgerufen wurde. Im Gegensatz dazu `False` bedeuten, dass sich die Informationen abgerufen wurden und die Person, die nicht mit den Bus zur Arbeit kommt.

Sie können Variablen und Eigenschaften mit auf NULL festlegbare Typen deklarieren, und Sie können ein Array mit Elementen von einem nullable-Typ deklarieren. Sie können Prozeduren mit nullable-Typen als Parameter deklarieren, und Sie können einen nullable-Typ von Zurückgeben einer `Function` Verfahren.

Sie können keinen nullable-Typ in einen Verweistyp handelt, z. B. ein Array ist, erstellen eine `String`, oder eine Klasse. Der zugrunde liegende Typ muss ein Werttyp sein. Weitere Informationen finden Sie unter [Value Types and Reference Types](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Verwenden die Variable ein Nullable-Typ

Die wichtigsten Mitglieder von einem nullable-Typ werden die <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A> Eigenschaften. Für eine Variable vom einen nullable-Typ <xref:System.Nullable%601.HasValue%2A> Aufschluss darüber, ob die Variable einen definierten Wert enthält. Wenn <xref:System.Nullable%601.HasValue%2A> ist `True`, Sie können den Wert von lesen <xref:System.Nullable%601.Value%2A>. Beachten Sie, dass beide <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A> sind `ReadOnly` Eigenschaften.

### <a name="default-values"></a>Standardwerte

Wenn Sie eine Variable mit einem NULL-Werte zulässt, deklarieren die <xref:System.Nullable%601.HasValue%2A> Eigenschaft hat den Standardwert `False`. Dies bedeutet, dass standardmäßig die Variable keinen definierten Wert statt des Standardwerts, der den zugrunde liegenden Werttyp hat. Im folgenden Beispiel ist die Variable `numberOfChildren` Anfangs hat keinen definierter Wert, obwohl den Standardwert der `Integer` ist 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Ein null-Wert ist hilfreich, einen nicht definierten oder unbekannten Wert anzugeben. Wenn `numberOfChildren` deklariert wurde als `Integer`, es gäbe keine-Wert, der anzeigen kann, dass die Informationen zurzeit nicht verfügbar ist.

### <a name="storing-values"></a>Speichern von Werten

Sie speichern einen Wert in einer Variablen oder die Eigenschaft einen nullable-Typ, auf die gewohnte Weise. Im folgende Beispiel wird die Variable ein Wert zugewiesen `numberOfChildren` im vorherigen Beispiel deklariert.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Wenn eine Variable oder eine Eigenschaft einen nullable-Typ um einen definierten Wert enthält, können Sie es auf seinen ursprünglichen Zustand des ohne eines zugewiesenen Wert zurückgesetzt auslösen. Hierzu legen Sie die Variable oder Eigenschaft, um `Nothing`, wie im folgende Beispiel gezeigt.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Sie können zwar zuweisen `Nothing` auf eine Variable eines Typs mit NULL-Werte zulässt, kann nicht für test `Nothing` mit dem Gleichheitszeichen. Vergleich, das Gleichheitszeichen verwendet `someVar = Nothing`, ergibt immer `Nothing`. Sie können des Wert der Variablentyps testen <xref:System.Nullable%601.HasValue%2A> -Eigenschaft für `False`, oder testen, indem die `Is` oder `IsNot` Operator.

### <a name="retrieving-values"></a>Abrufen von Werten

Sie sollten zunächst testen, zum Abrufen des Werts einer Variablen mit einem nullable-Typ der <xref:System.Nullable%601.HasValue%2A> Eigenschaft, um sicherzustellen, dass es sich um einen Wert aufweist. Wenn Sie versuchen, den Wert zu lesen bei <xref:System.Nullable%601.HasValue%2A> ist `False`, Visual Basic löst eine <xref:System.InvalidOperationException> Ausnahme. Das folgende Beispiel zeigt die empfohlene Methode zum Lesen der Variablen `numberOfChildren` von den vorherigen Beispielen.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Vergleichen von Nullable-Typen

Wenn auf NULL festlegbare `Boolean` Variablen in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False`, oder `Nothing`. Im folgenden finden Sie die Wahrheitstabelle für `And` und `Or`. Da `b1` und `b2` haben jetzt drei mögliche Werte sind neun Kombinationen ausgewertet.

|b1|b2|B1 und b2|b1 Or b2|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

Wenn der Wert, der eine boolesche Variable oder einen Ausdruck ist `Nothing`, es ist keines von beiden `true` noch `false`. Betrachten Sie das folgende Beispiel.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

In diesem Beispiel `b1 And b2` ergibt `Nothing`. Daher die `Else` -Klausel ausgeführt wird, in den einzelnen `If` -Anweisung und die Ausgabe sieht folgendermaßen aus:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` und `OrElse`, welche verwenden kurzschlussauswertung muss ihrer zweiten Operanden ausgewertet werden, wenn die erste ergibt `Nothing`.

## <a name="propagation"></a>Weitergabe

Wenn eine oder beide der Operanden des eine Arithmetik, Vergleich, UMSCHALT oder einem Rollenporttyp-Vorgang ist NULL-Werte zulässt, ist das Ergebnis des Vorgangs auch NULL-Werte zulässt. Wenn beide Operanden Werte verfügen, die nicht `Nothing`, der Vorgang erfolgt auf die zugrunde liegenden Werte der Operanden, als wäre keine nullable-Typ. Im folgenden Beispiel Variablen `compare1` und `sum1` implizit typisiert werden. Wenn Sie den Mauszeiger darüber bewegen, sehen Sie sich, dass leitet der Compiler die nullable-Typen für beide Ausgaben.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Wenn eine oder beide der Operanden einen Wert `Nothing`, das Ergebnis `Nothing`.

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Verwenden von Nullable-Typen mit Daten

Eine Datenbank ist eine der wichtigsten Quellen für die nullable-Typen zu verwenden. Nicht alle Datenbankobjekte wird derzeit auf NULL festlegbare Typen unterstützt, aber die vom Designer generierten Tabellenadaptern. Finden Sie unter [TableAdapter-Unterstützung für auf NULL festlegbare Typen](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>Siehe auch

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Verwenden von Typen mit Nullwert](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Datentypen](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Füllen von Datasets mit TableAdapters](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [If-Operator](../../../language-reference/operators/if-operator.md)
- [Lokaler Typrückschluss](../variables/local-type-inference.md)
- [Is-Operator](../../../language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../language-reference/operators/isnot-operator.md)