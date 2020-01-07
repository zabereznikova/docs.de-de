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
ms.openlocfilehash: 0d259e11a969f4eb7e64626a4adf498db06ece06
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347838"
---
# <a name="nullable-value-types-visual-basic"></a>Auf NULL festlegbare Werttypen (Visual Basic)

Manchmal arbeiten Sie mit einem Werttyp, der unter bestimmten Umständen keinen definierten Wert hat. Beispielsweise muss ein Feld in einer Datenbank möglicherweise zwischen einem zugewiesenen Wert unterscheiden, der aussagekräftig ist und keinem zugewiesenen Wert zugeordnet ist. Werttypen können so erweitert werden, dass Sie entweder Ihre normalen Werte oder einen NULL-Wert akzeptieren. Eine solche Erweiterung wird als Typ bezeichnet, der *NULL-Werte*zulässt.

Jeder Typ, der NULL-Werte zulässt, wird aus der generischen <xref:System.Nullable%601> Struktur erstellt. Stellen Sie sich eine Datenbank vor, die arbeitsbezogene Aktivitäten nachverfolgt. Im folgenden Beispiel wird ein `Boolean` Typ erstellt, der NULL-Werte zulässt, und eine Variable dieses Typs deklariert. Es gibt drei Möglichkeiten, die Deklaration zu schreiben:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

Die Variable `ridesBusToWork` kann den Wert `True`, den Wert `False`oder keinen Wert enthalten. Der anfängliche Standardwert ist überhaupt kein Wert, was in diesem Fall bedeuten könnte, dass die Informationen für diese Person noch nicht abgerufen wurden. Im Gegensatz dazu kann `False` bedeuten, dass die Informationen abgerufen wurden und die Person den Bus nicht zum Arbeiten fährt.

Sie können Variablen und Eigenschaften mit Typen deklarieren, die NULL-Werte zulassen, und Sie können ein Array mit Elementen eines Typs deklarieren, der NULL-Werte zulässt. Sie können Prozeduren mit Typen, die NULL-Werte zulassen, als Parameter deklarieren und einen Typ, der NULL-Werte zulässt, aus einer `Function` Prozedur

Sie können einen Typ, der NULL-Werte zulässt, nicht für einen Referenztyp erstellen, z. b. ein Array, ein `String`oder eine Klasse. Der zugrunde liegende Typ muss ein Werttyp sein. Weitere Informationen finden Sie unter [Value Types and Reference Types](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Verwenden einer Typvariablen, die NULL-Werte zulässt

Die wichtigsten Member eines Typs, der NULL-Werte zulässt, sind die Eigenschaften <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A>. Für eine Variable eines Typs, der NULL-Werte zulässt, gibt <xref:System.Nullable%601.HasValue%2A> Aufschluss darüber, ob die Variable einen definierten Wert enthält. Wenn <xref:System.Nullable%601.HasValue%2A> `True`ist, können Sie den Wert aus <xref:System.Nullable%601.Value%2A>lesen. Beachten Sie, dass sowohl <xref:System.Nullable%601.HasValue%2A> als auch <xref:System.Nullable%601.Value%2A> `ReadOnly` Eigenschaften sind.

### <a name="default-values"></a>Standardwerten

Wenn Sie eine Variable mit einem Typ deklarieren, der NULL-Werte zulässt, hat die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft den Standardwert `False`. Dies bedeutet, dass die Variable standardmäßig keinen definierten Wert anstelle des Standardwerts des zugrunde liegenden Werttyps aufweist. Im folgenden Beispiel hat die Variable `numberOfChildren` anfänglich keinen definierten Wert, obwohl der Standardwert des `Integer` Typs 0 ist.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Ein NULL-Wert ist nützlich, um einen nicht definierten oder unbekannten Wert anzugeben. Wenn `numberOfChildren` als `Integer`deklariert wurde, wäre kein Wert vorhanden, der darauf hindeuten kann, dass die Informationen zurzeit nicht verfügbar sind.

### <a name="storing-values"></a>Speichern von Werten

Sie speichern einen Wert in einer Variablen oder Eigenschaft eines Typs, der NULL-Werte zulässt, auf die übliche Weise. Im folgenden Beispiel wird der Variablen `numberOfChildren`, die im vorherigen Beispiel deklariert wurde, ein Wert zugewiesen.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Wenn eine Variable oder Eigenschaft eines Typs, der NULL-Werte zulässt, einen definierten Wert enthält, können Sie bewirken, dass Sie in den ursprünglichen Zustand zurückversetzt wird, dass kein Wert zugewiesen ist. Hierzu legen Sie die Variable oder Eigenschaft auf `Nothing`fest, wie im folgenden Beispiel gezeigt.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Obwohl Sie `Nothing` einer Variablen eines Typs zuweisen können, der NULL-Werte zulässt, können Sie ihn nicht mit dem Gleichheitszeichen für `Nothing` testen. Ein Vergleich, bei dem das Gleichheitszeichen (`someVar = Nothing`) verwendet wird, ergibt immer `Nothing`. Sie können die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft der Variablen für `False`testen oder mithilfe des Operators `Is` oder `IsNot` testen.

### <a name="retrieving-values"></a>Abrufen von Werten

Zum Abrufen des Werts einer Variablen eines Typs, der NULL-Werte zulässt, sollten Sie zunächst die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft testen, um zu bestätigen, dass Sie über einen Wert verfügt. Wenn Sie versuchen, den Wert zu lesen, wenn <xref:System.Nullable%601.HasValue%2A> `False`ist, löst Visual Basic eine <xref:System.InvalidOperationException> Ausnahme aus. Das folgende Beispiel zeigt die empfohlene Vorgehensweise zum Lesen der Variablen `numberOfChildren` der vorherigen Beispiele.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Vergleichen von Typen mit Nullwert

Wenn `Boolean` Variablen, die NULL-Werte zulassen, in booleschen Ausdrücken verwendet werden, kann das Ergebnis `True`, `False`oder `Nothing`sein. Im folgenden finden Sie die Wahrheitstabelle für `And` und `Or`. Da `b1` und `b2` nun drei mögliche Werte aufweisen, gibt es neun zu bewertende Kombinationen.

|b1|b2|B1 und B2|B1 oder B2|
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

Wenn der Wert einer booleschen Variablen oder eines Ausdrucks `Nothing`ist, ist er weder `true` noch `false`. Betrachten Sie das folgende Beispiel.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

In diesem Beispiel ergibt `b1 And b2` `Nothing`. Folglich wird die `Else`-Klausel in jeder `If`-Anweisung ausgeführt, und die Ausgabe sieht wie folgt aus:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` und `OrElse`, bei denen die Kurzschluss Auswertung verwendet wird, müssen die zweiten Operanden auswerten, wenn der erste zu `Nothing`ausgewertet wird.

## <a name="propagation"></a>Weitergabe

Wenn einer der Operanden eines arithmetischen, Vergleichs-, Verschiebungs-oder typvorgangs NULL-Werte zulässt, kann das Ergebnis des Vorgangs ebenfalls NULL-Werte zulassen. Wenn beide Operanden über Werte verfügen, die nicht `Nothing`sind, wird der Vorgang für die zugrunde liegenden Werte der Operanden ausgeführt, als wären keine NULL-Werte zulässig. Im folgenden Beispiel werden Variablen `compare1` und `sum1` implizit eingegeben. Wenn Sie den Mauszeiger darüber bewegen, sehen Sie, dass der Compiler Werte zulässt-Typen für beide ausleitet.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Wenn ein oder beide Operanden den Wert `Nothing`haben, wird das Ergebnis `Nothing`.

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Verwenden von Nullable-Typen mit Daten

Eine Datenbank ist einer der wichtigsten Orte für die Verwendung von Typen, die NULL-Werte zulassen. Nicht alle Datenbankobjekte unterstützen zurzeit Typen, die NULL-Werte zulassen, aber die vom Designer generierten Tabellen Adapter. Siehe [TableAdapter-Unterstützung für Typen](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types), die NULL-Werte zulassen

## <a name="see-also"></a>Siehe auch

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Datentypen](index.md)
- [Werttypen und Verweistypen](value-types-and-reference-types.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Füllen von Datasets mit TableAdapters](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [If-Operator](../../../language-reference/operators/if-operator.md)
- [Lokaler Typrückschluss](../variables/local-type-inference.md)
- [Is-Operator](../../../language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../language-reference/operators/isnot-operator.md)
- [Auf NULL festleg BareC#Werttypen ()](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
