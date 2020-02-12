---
title: 'Nullable-Werttypen: C#-Referenz'
description: Informationen zu Werttypen, die Nullwerte zulassen, in C# und der Verwendung dieser Typen
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: bd90a0b1b77349efe581eb8aae44c58802ba756d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093187"
---
# <a name="nullable-value-types-c-reference"></a>Nullable-Werttypen (C#-Referenz)

Ein *Werttyp, der NULL zulässt* (wie `T?`) stellt alle Werte des zugrunde liegenden [Werttyps](value-types.md) `T` und einen zusätzlichen [NULL](../keywords/null.md)-Wert dar. Beispielsweise können Sie einer `bool?`-Variablen einen der folgenden drei Werte zuweisen: `true`, `false` oder `null`. Ein zugrunde liegender Werttyp `T` darf selbst kein Nullable-Werttyp sein.

> [!NOTE]
> C# 8.0 führt das Feature der Nullable-Verweistypen ein. Weitere Informationen finden Sie unter [Nullable-Verweistypen](../../nullable-references.md). Nullable-Werttypen sind ab C# 2 verfügbar.

Jeder Nullable-Werttyp ist eine Instanz der generischen Struktur <xref:System.Nullable%601?displayProperty=nameWithType>. Sie können auf einen Nullable-Werttyp mit einem zugrunde liegenden Typ `T` in einer der folgenden austauschbaren Formen verweisen: `Nullable<T>` oder `T?`.

Sie verwenden in der Regel einen Nullable-Werttyp, wenn Sie den nicht definierten Wert eines zugrunde liegenden Werttyps darstellen müssen. Beispielsweise kann ein boolescher Wert eine `bool`-Variable nur `true` oder `false` sein. In einigen Anwendungen kann ein Variablenwert jedoch nicht definiert sein oder fehlen. Beispielsweise kann ein Datenbankfeld `true` oder `false`enthalten, oder es enthält gar keinen Wert, ist also `NULL`. In diesem Szenario können Sie den `bool?`-Typ verwenden.

## <a name="declaration-and-assignment"></a>Deklaration und Zuweisung

Da ein Werttyp implizit in den entsprechenden Nullable-Werttyp konvertiert werden kann, können Sie einer Variablen eines Nullable-Werttyps auf die gleiche Weise wie seinem zugrunde liegenden Werttyp einen Wert zuweisen. Sie können auch den `null`-Wert zuweisen. Zum Beispiel:

[!code-csharp[declare and assign](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Declaration)]

Der Standardwert eines Nullable-Werttyps stellt `null` dar, es handelt sich also um eine-Instanz, deren <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType>-Eigenschaft `false` zurückgibt.

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a>Untersuchung einer Instanz eines Nullable-Werttyps

Ab C# 7.0 können Sie den [`is`-Operator mit einem Typmuster](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) verwenden, um eine Instanz eines Nullable-Werttyps für `null` zu untersuchen und einen Wert eines zugrunde liegenden Typs abzurufen:

[!code-csharp-interactive[use pattern matching](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#PatternMatching)]

Sie können immer die folgenden schreibgeschützten Eigenschaften verwenden, um einen Wert einer Variablen des Nullable-Werttyps zu untersuchen und abzurufen:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> gibt an, ob eine Instanz des Nullable-Werttyps über einen Wert des zugrunde liegenden Typs verfügt.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ruft den Wert eines zugrunde liegenden Typs ab, wenn <xref:System.Nullable%601.HasValue%2A>`true` ist. Wenn <xref:System.Nullable%601.HasValue%2A>`false` ist, löst die <xref:System.Nullable%601.Value%2A>-Eigenschaft eine <xref:System.InvalidOperationException> aus.

Im folgenden Beispiel wird mit der `HasValue`-Eigenschaft überprüft, ob die Variable einen Wert enthält. Erst danach erfolgt die Anzeige:

[!code-csharp-interactive[use HasValue](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#HasValue)]

Sie können eine Variable eines Nullable-Typs auch mit `null` anstelle der `HasValue`-Eigenschaft vergleichen, wie im folgenden Beispiel gezeigt wird:

[!code-csharp-interactive[use comparison with null](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Konvertieren eines Nullable-Werttyps in einen zugrunde liegenden Typ

Wenn Sie einen Wert eines Nullable-Werttyps einer Variablen eines Nicht-Nullable-Werttyps zuweisen möchten, müssen Sie möglicherweise den zuzuweisenden Wert anstelle von `null` angeben. Verwenden Sie zu diesem Zweck den [NULL-Sammeloperator `??`](../operators/null-coalescing-operator.md) (Sie können auch die <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>-Methode für denselben Zweck verwenden):

[!code-csharp-interactive[?? operator](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#NullCoalescing)]

Wenn Sie den [Standardwert](default-values.md) des zugrunde liegenden Werttyps anstelle von `null` verwenden möchten, verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode.

Sie können einen Nullable-Werttyp wie im folgenden Beispiel gezeigt auch explizit in einen Nicht-Nullable-Typ umwandeln:

[!code-csharp[explicit cast](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Cast)]

Wenn der Wert eines Nullable-Typs zur Laufzeit `null` ist, wird durch die explizite Umwandlung eine <xref:System.InvalidOperationException> ausgelöst.

Ein Nicht-Nullable-Werttyp `T` kann implizit in den entsprechenden Nullable-Werttyp `T?` konvertiert werden.

## <a name="lifted-operators"></a>„Lifted“ Operatoren

Die vordefinierten unären und binären [Operatoren](../operators/index.md) oder alle überladenen Operatoren, die von einem Werttyp `T` unterstützt werden, werden auch vom entsprechenden Werttyp `T?` unterstützt, der NULL zulässt. Durch diese Operatoren (auch als *„lifted“ Operatoren* bezeichnet) wird `null` generiert, wenn mindestens ein Operand `null` ist. Andernfalls verwendet der Operator die enthaltenen Werte seiner Operanden zur Berechnung des Ergebnisses. Zum Beispiel:

[!code-csharp[lifted operators](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> Für den `bool?`-Typ gelten für die vordefinierten Operatoren `&` und `|` nicht die in diesem Abschnitt beschriebenen Regeln. Die Auswertung eines Operators kann auch dann einen anderen Wert als NULL ergeben, wenn einer der beiden Operanden `null` ist. Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../operators/boolean-logical-operators.md).

Für die [Vergleichsoperatoren](../operators/comparison-operators.md) `<`, `>`, `<=` und `>=` ist das Ergebnis `false`, wenn einer oder beide Operanden `null` sind. Andernfalls werden die enthaltenen Werte von Operanden verglichen. Falsch wäre die Annahme, dass im Fall des Rückgabewerts `false` für einen bestimmten Vergleich (beispielsweise `<=`) der gegenteilige Vergleich (`>`) `true` zurückgibt. Das folgende Beispiel zeigt, dass 10

- weder größer als oder gleich `null`
- noch kleiner als `null` ist.

[!code-csharp-interactive[relational and equality operators](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#ComparisonOperators)]

Für den [Gleichheitsoperator](../operators/equality-operators.md#equality-operator-) `==` ist das Ergebnis `true`, wenn beide Operanden `null` sind. Das Ergebnis ist `false`, wenn nur einer der Operanden `null` ist. Andernfalls werden die enthaltenen Werte von Operanden verglichen.

Für den [Ungleichheitsoperator](../operators/equality-operators.md#inequality-operator-) `!=` ist das Ergebnis `false`, wenn beide Operanden `null` sind. Das Ergebnis ist `true`, wenn nur einer der Operanden `null` ist. Andernfalls werden die enthaltenen Werte von Operanden verglichen.

Wenn eine [benutzerdefinierte Konvertierung](../operators/user-defined-conversion-operators.md) zwischen zwei Werttypen vorhanden ist, kann die gleiche Konvertierung auch zwischen den entsprechenden Nullable-Werttypen verwendet werden.

## <a name="boxing-and-unboxing"></a>Boxing und Unboxing

Das [Boxing](../../programming-guide/types/boxing-and-unboxing.md) einer Instanz eines Nullable-Werttyps `T?` erfolgt folgendermaßen:

- Wenn <xref:System.Nullable%601.HasValue%2A>`false` zurückgibt, wird der Nullverweis erstellt.
- Wenn <xref:System.Nullable%601.HasValue%2A>`true` zurückgibt, wird nicht für eine Instanz von <xref:System.Nullable%601>, sondern für den entsprechenden Wert des zugrunde liegenden Werttyps `T` Boxing durchgeführt.

Sie können den Werttyp, für den das Boxing durchgeführt wurde, vom Werttyp `T` mittels Unboxing in den entsprechenden Nullable-Werttyp `T?` konvertieren, wie im folgenden Beispiel gezeigt wird:

[!code-csharp-interactive[boxing and unboxing](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a>Identifizieren eines Nullable-Werttyps

Das folgende Beispiel zeigt, wie Sie bestimmen können, ob eine <xref:System.Type?displayProperty=nameWithType>-Instanz einen konstruierten Nullable-Werttyp darstellt, d.h. den <xref:System.Nullable%601?displayProperty=nameWithType>-Typ mit einem angegebenen Typparameter `T`:

[!code-csharp-interactive[whether Type is nullable](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsTypeNullable)]

Wie Sie im Beispiel sehen können, wird der Operator [typeof](../operators/type-testing-and-cast.md#typeof-operator) verwendet, um eine <xref:System.Type?displayProperty=nameWithType>-Instanz zu erstellen.

Wenn Sie bestimmen möchten, ob eine Instanz einen Nullable-Werttyp aufweist, verwenden Sie nicht die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode, um eine <xref:System.Type>-Instanz abzurufen, die mit dem vorangehenden Code überprüft werden soll. Wenn Sie die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode in einer Instanz eines Nullable-Werttyps aufrufen, wird die Instanz in <xref:System.Object>[geschachtelt](#boxing-and-unboxing). Da das Schachteln einer nicht-NULL-Instanz von einem Nullable-Werttyp dem Schachteln eines Werts des zugrunde liegenden Typs entspricht, gibt <xref:System.Object.GetType%2A> eine <xref:System.Type>-Instanz zurück, die den zugrunde liegenden Typ eines Nullable-Werttyps darstellt:

[!code-csharp-interactive[GetType example](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#GetType)]

Verwenden Sie außerdem nicht den Operator [is](../operators/type-testing-and-cast.md#is-operator), um zu ermitteln, ob eine Instanz einem Nullable-Werttyp entspricht. Wie im folgenden Beispiel veranschaulicht wird, können Sie die Typen einer Instanz eines Nullable-Werttyps und die zugrunde liegende Typinstanz nicht mithilfe des `is`-Operators unterscheiden:

[!code-csharp-interactive[is operator example](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsOperator)]

Sie können den Code verwenden, der im folgenden Beispiel dargestellt wird, um zu ermitteln, ob eine Instanz einen Nullable-Werttyp aufweist:

[!code-csharp-interactive[whether an instance is of a nullable type](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> Die in diesem Abschnitt beschriebenen Methoden sind im Fall von [Nullable-Verweistypen](../../nullable-references.md) nicht anwendbar.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Nullable-Typen](~/_csharplang/spec/types.md#nullable-types)
- [„Lifted“ Operatoren](~/_csharplang/spec/expressions.md#lifted-operators)
- [Implizite Nullable-Konvertierungen](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [Explizite Nullable-Konvertierungen](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [„Lifted“ Konvertierungsoperatoren](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [What exactly does 'lifted' mean?](https://docs.microsoft.com/archive/blogs/ericlippert/what-exactly-does-lifted-mean) (Was bedeutet „Lifted“ genau?)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [Nullwerte zulassende Verweistypen](../../nullable-references.md)
