---
title: Auf NULL festlegbare Werttypen
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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249681"
---
# <a name="nullable-value-types-visual-basic"></a>Auf NULL festlegbare Werttypen (Visual Basic)

Manchmal arbeiten Sie mit einem Werttyp, der unter bestimmten Umständen keinen definierten Wert hat. Beispielsweise muss ein Feld in einer Datenbank möglicherweise unterscheiden, ob ein wertschätzender Wert zugewiesen ist und kein Wert zugewiesen ist. Werttypen können erweitert werden, um entweder ihre Normalwerte oder einen NULL-Wert zu verwenden. Eine solche Erweiterung wird als *nullabler Typ*bezeichnet.

Jeder nullable Werttyp wird <xref:System.Nullable%601> aus der generischen Struktur erstellt. Betrachten Sie eine Datenbank, die arbeitsbezogene Aktivitäten nachverfolgt. Im folgenden Beispiel wird `Boolean` ein nullabler Typ erstellt und eine Variable dieses Typs deklariert. Sie können die Deklaration auf drei Arten schreiben:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

Die `ridesBusToWork` Variable kann einen `True`Wert von `False`, einen Wert von oder gar keinen Wert enthalten. Sein anfänglicher Standardwert ist überhaupt kein Wert, was in diesem Fall bedeuten könnte, dass die Informationen für diese Person noch nicht abgerufen wurden. Im Gegensatz `False` dazu könnte bedeuten, dass die Informationen erhalten wurden und die Person nicht mit dem Bus zur Arbeit fährt.

Sie können Variablen und Eigenschaften mit nullablen Werttypen deklarieren und Sie können ein Array mit Elementen eines nullablen Werttyps deklarieren. Sie können Prozeduren mit NULL-Werttypen als Parameter deklarieren und `Function` einen nullablen Werttyp aus einer Prozedur zurückgeben.

Sie können keinen nullbaren Typ für einen Verweistyp wie ein Array, eine `String`oder eine Klasse erstellen. Der zugrunde liegende Typ muss ein Werttyp sein. Weitere Informationen finden Sie unter [Werttypen und Referenztypen](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Verwenden einer Nullbaren Typvariablen

Die wichtigsten Member eines nullbaren <xref:System.Nullable%601.HasValue%2A> Werttyps sind seine und <xref:System.Nullable%601.Value%2A> Eigenschaften. Gibt für eine Variable des <xref:System.Nullable%601.HasValue%2A> Nullwerttyps an, ob die Variable einen definierten Wert enthält. Wenn <xref:System.Nullable%601.HasValue%2A> `True`dies der Falle <xref:System.Nullable%601.Value%2A>ist, können Sie den Wert aus aus lesen. Beachten Sie, <xref:System.Nullable%601.Value%2A> `ReadOnly` dass beides <xref:System.Nullable%601.HasValue%2A> und eigenschaften sind.

### <a name="default-values"></a>Standardwerte

Wenn Sie eine Variable mit einem NULL-Werttyp deklarieren, hat ihre <xref:System.Nullable%601.HasValue%2A> Eigenschaft den Standardwert von `False`. Dies bedeutet, dass die Variable standardmäßig keinen definierten Wert anstelle des Standardwerts des zugrunde liegenden Werttyps hat. Im folgenden Beispiel hat `numberOfChildren` die Variable zunächst keinen definierten Wert, `Integer` obwohl der Standardwert des Typs 0 ist.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Ein NULL-Wert ist nützlich, um einen nicht definierten oder unbekannten Wert anzugeben. Wenn `numberOfChildren` als `Integer`deklariert worden wäre, gäbe es keinen Wert, der darauf hinweisen könnte, dass die Informationen derzeit nicht verfügbar sind.

### <a name="storing-values"></a>Speichern von Werten

Sie speichern einen Wert in einer Variablen oder Eigenschaft eines NULL-Werttyps auf die typische Weise. Im folgenden Beispiel wird der `numberOfChildren` im vorherigen Beispiel deklarierten Variablen ein Wert zugewiesen.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Wenn eine Variable oder Eigenschaft eines NULL-Wert-Typs einen definierten Wert enthält, können Sie dazu führen, dass sie in den Anfangszustand zurückgesetzt wird, in dem kein Wert zugewiesen wurde. Dazu legen Sie die Variable `Nothing`oder Eigenschaft auf , wie das folgende Beispiel zeigt.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Obwohl Sie `Nothing` einer Variablen des Nullwerttyps zuweisen können, `Nothing` können Sie sie nicht mit dem Gleichheitszeichen testen. Vergleich, der das `someVar = Nothing`Gleichheitszeichen verwendet, wird immer zu `Nothing`ausgewertet. Sie können <xref:System.Nullable%601.HasValue%2A> die Eigenschaft der `False`Variablen für testen `Is` `IsNot` oder mit dem Operator oder testen.

### <a name="retrieving-values"></a>Abrufen von Werten

Um den Wert einer Variablen eines NULL-Wert-Typs <xref:System.Nullable%601.HasValue%2A> abzurufen, sollten Sie zuerst ihre Eigenschaft testen, um zu bestätigen, dass sie einen Wert hat. Wenn Sie versuchen, den <xref:System.Nullable%601.HasValue%2A> `False`Wert zu lesen, wenn es ist, löst Visual Basic eine <xref:System.InvalidOperationException> Ausnahme aus. Das folgende Beispiel zeigt die empfohlene `numberOfChildren` Methode zum Lesen der Variablen der vorherigen Beispiele.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Vergleichen von nullierbaren Typen

`Boolean` Wenn nullable Variablen in booleschen Ausdrücken `True` `False`verwendet `Nothing`werden, kann das Ergebnis , oder sein. Im Folgenden finden Sie `And` `Or`die Wahrheitstabelle für und . Da `b1` `b2` und jetzt drei mögliche Werte haben, gibt es neun Kombinationen zu bewerten.

|b1|B2|b1 Und b2|b1 Oder b2|
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

Wenn der Wert einer booleschen `Nothing`Variablen oder `true` `false`eines Ausdrucks ist, ist er weder noch . Betrachten Sie das folgende Beispiel.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

In diesem `b1 And b2` Beispiel werden `Nothing`Werte in ausgewertet. Daher wird die `Else` Klausel in jeder `If` Anweisung ausgeführt, und die Ausgabe lautet wie folgt:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso`und `OrElse`, die kurzschlussauswertung verwenden, müssen ihre zweiten Operanden `Nothing`bewerten, wenn der erste auf ausgewertet wird.

## <a name="propagation"></a>Weitergabe

Wenn einer oder beide Operanden eines Arithmetischen, Vergleichs-, Verschiebungs- oder Typvorgangs ein NULL-Werttyp ist, ist das Ergebnis des Vorgangs auch ein NULL-Werttyp. Wenn beide Operanden Werte `Nothing`haben, die nicht sind, wird der Vorgang für die zugrunde liegenden Werte der Operanden ausgeführt, als ob keines von beiden ein NULL-Werttyp wäre. Im folgenden Beispiel `compare1` `sum1` werden Variablen implizit eingegeben. Wenn Sie den Mauszeiger darüber bewegen, werden Sie sehen, dass der Compiler für beide nullable Werttypen ableitet.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Wenn einer oder beide Operanden `Nothing`den Wert `Nothing`von haben, wird das Ergebnis .

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Verwenden von Null-Typen mit Daten

Eine Datenbank ist einer der wichtigsten Orte für die Verwendung von NULL-Werttypen. Nicht alle Datenbankobjekte unterstützen derzeit nullfähige Werttypen, aber die vom Designer generierten Tabellenadapter. Siehe [TableAdapter-Unterstützung für nullfähige Typen](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>Siehe auch

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Datentypen](index.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Füllen von Datasets mit TableAdapters](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [If-Operator](../../../language-reference/operators/if-operator.md)
- [Lokaler Typrückschluss](../variables/local-type-inference.md)
- [Is-Operator](../../../language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../language-reference/operators/isnot-operator.md)
- [Nullable Wertetypen (C-Wert)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
