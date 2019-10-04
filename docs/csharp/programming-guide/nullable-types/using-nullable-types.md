---
title: 'Verwenden von Nullable-Werttypen: C#-Programmierleitfaden'
ms.custom: seodec18
description: Erfahren Sie, wie Sie mit Nullable-Werttypen von C# arbeiten können.
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396162"
---
# <a name="using-nullable-value-types-c-programming-guide"></a>Verwenden von Nullable-Werttypen (C#-Programmierleitfaden)

Nullable-Werttypen sind Typen, die alle Werte eines zugrunde liegenden `T`-Werttyps und einen zusätzlichen [NULL](../../language-reference/keywords/null.md)-Wert darstellen. Weitere Informationen finden Sie im Thema [Nullable-Werttypen](index.md).

> [!NOTE]
> C# 8.0 führt das Feature der Nullable-Verweistypen ein. Weitere Informationen finden Sie unter [Nullable-Verweistypen](../../nullable-references.md). Nullable-Werttypen sind ab C# 2 verfügbar.

Sie können auf einen Nullable-Werttyp mit einer der folgenden austauschbaren Formen verweisen: `Nullable<T>` oder `T?`. `T` muss ein Werttyp sein.

## <a name="declaration-and-assignment"></a>Deklaration und Zuweisung

Da ein Werttyp implizit in den entsprechenden Nullable-Werttyp konvertiert werden kann, können Sie dem Nullable-Werttyp auf die gleiche Weise einen Wert zuweisen, wie es auch für dessen zugrunde liegenden Werttyp der Fall ist. Sie können auch den `null`-Wert zuweisen. Beispiel:

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Untersuchen des Nullable-Typwerts

Verwenden Sie die folgenden schreibgeschützten Eigenschaften, um eine Instanz eines Nullable-Werttyps zu untersuchen und einen Wert des zugrunde liegenden Typs abzurufen:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> gibt an, ob eine Instanz des Nullable-Typs über einen Wert des zugrunde liegenden Typs verfügt.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ruft den Wert eines zugrunde liegenden Typs ab, wenn <xref:System.Nullable%601.HasValue%2A> `true` ist. Wenn <xref:System.Nullable%601.HasValue%2A> `false` ist, löst die <xref:System.Nullable%601.Value%2A>-Eigenschaft eine <xref:System.InvalidOperationException> aus.

Im folgenden Beispielcode wird mit der `HasValue`-Eigenschaft überprüft, ob die Variable einen Wert enthält. Erst danach erfolgt die Ausgabe:

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

Sie können eine Variable eines Nullable-Typs auch mit `null` anstelle der `HasValue`-Eigenschaft vergleichen, wie im folgenden Beispiel gezeigt wird:

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

Ab C# 7.0 können Sie [Musterabgleich](../../pattern-matching.md) verwenden, um einen Wert eines Nullable-Werttyps zu untersuchen und abzurufen:

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Konvertieren eines Nullable-Werttyps in einen zugrunde liegenden Typ

Wenn Sie einem Nicht-Nullable-Typ einen Wert eines Nullable-Werttyps zuweisen müssen, verwenden Sie den [NULL-Koaleszenzoperator `??`](../../language-reference/operators/null-coalescing-operator.md), um den zuzuordnenden Wert anzugeben, wenn ein Wert eines Nullable-Werttyps NULL ist (Sie können dazu auch die <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>-Methode verwenden):

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der verwendet werden soll, wenn der Wert des Nullable-Typs `null` ist, der Standardwert des zugrunde liegenden Werttyps sein soll.

Sie können einen Nullable-Werttyp explizit in einen Nicht-Nullable-Typ umwandeln. Beispiel:

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

Wenn der Wert eines Nullable-Typs zur Laufzeit `null` ist, wird durch die explizite Umwandlung eine <xref:System.InvalidOperationException> ausgelöst.

Ein Nicht-Nullable-Werttyp wird implizit in den entsprechenden Nullable-Typ konvertiert.

## <a name="operators"></a>Operatoren

Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von entsprechenden Nullable-Typen verwendet werden. Durch die Operatoren wird ein `null` generiert, wenn mindestens ein Operand `null` ist. Andernfalls verwendet der Operator die enthaltenen Werte zur Berechnung eines Ergebnisses. Beispiel:

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> Für den `bool?`-Typ gelten für die vordefinierten Operatoren `&` und `|` nicht die in diesem Abschnitt beschriebenen Regeln. Die Auswertung eines Operators kann auch dann einen anderen Wert als NULL ergeben, wenn einer der beiden Operanden `null` ist. Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../../language-reference/operators/boolean-logical-operators.md).
  
Wenn bei relationalen Operatoren (`<`, `>`, `<=`, `>=`) mindestens ein Operand `null` ist, ist das Ergebnis `false`. Falsch wäre die Annahme, dass im Fall des Rückgabewerts `false` für einen bestimmten Vergleich (beispielsweise `<=`) der gegenteilige Vergleich (`>`) `true` zurückgibt. Das folgende Beispiel zeigt, dass 10

- weder größer als oder gleich `null`
- noch kleiner als `null` ist.

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

Das Beispiel oben demonstriert außerdem, dass ein Gleichheitsvergleich zweier Nullable-Werttypen, die beide NULL sind, `true` ergibt.

Weitere Informationen finden Sie im Abschnitt [Transformierte Operatoren](~/_csharplang/spec/expressions.md#lifted-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="boxing-and-unboxing"></a>Boxing und Unboxing

Für einen Nullable-Werttyp wird das [Boxing](../types/boxing-and-unboxing.md) entsprechend der folgenden Regeln durchgeführt:

- Wenn <xref:System.Nullable%601.HasValue%2A> `false` zurückgibt, wird der Nullverweis erstellt.
- Wenn <xref:System.Nullable%601.HasValue%2A> `true` zurückgibt, wird nicht für eine Instanz von <xref:System.Nullable%601>, sondern für einen Wert des zugrunde liegenden Werttyps `T` das Boxing durchgeführt.

Sie können den Werttyp, für den das Boxing durchgeführt wurde, mittels Unboxing in den entsprechenden Nullable-Typ umwandeln, wie im folgenden Beispiel gezeigt wird:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](index.md)
- [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was bedeutet „Lifted“ genau?)
