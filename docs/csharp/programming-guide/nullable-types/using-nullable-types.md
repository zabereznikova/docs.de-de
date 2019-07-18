---
title: Verwenden von Nullable-Typen – C#-Programmierhandbuch
ms.custom: seodec18
description: Erfahren Sie, wie Sie mit Nullable-Typen in C# arbeiten.
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: ef7c9c18d303131b5a1c0156be820e1d475e7ec1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306650"
---
# <a name="using-nullable-types-c-programming-guide"></a>Verwenden von Nullable-Typen (C#-Programmierleitfaden)

Nullable-Typen sind Typen, die alle Werte eines zugrunde liegenden `T`-Werttyps und einen zusätzlichen [NULL](../../language-reference/keywords/null.md)-Wert darstellen. Weitere Informationen finden Sie im Artikel [Nullable-Typen](index.md).

Sie können mit `Nullable<T>` oder `T?` auf einen Nullable-Typ verweisen. Die beiden Formen sind austauschbar.  
  
## <a name="declaration-and-assignment"></a>Deklaration und Zuweisung

Da ein Werttyp implizit in den entsprechenden Nullable-Typ konvertiert werden kann, können Sie dem Nullable-Typ genauso einen Wert zuweisen, wie Sie es auch für dessen zugrunde liegenden Werttyp tun würden. Sie können auch den `null`-Wert zuweisen.  Beispiel:
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Untersuchen des Nullable-Typwerts

Verwenden Sie die folgenden schreibgeschützten Eigenschaften, um eine Instanz eines Nullable-Typs für NULL zu untersuchen und einen Wert des zugrunde liegenden Typs abzurufen:  
  
- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> gibt an, ob eine Instanz des Nullable-Typs über einen Wert des zugrunde liegenden Typs verfügt.
  
- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> ruft den Wert eines zugrunde liegenden Typs ab, wenn <xref:System.Nullable%601.HasValue%2A> `true` ist. Wenn <xref:System.Nullable%601.HasValue%2A> `false` ist, löst die <xref:System.Nullable%601.Value%2A>-Eigenschaft eine <xref:System.InvalidOperationException> aus.
  
Im folgenden Beispielcode wird mit der `HasValue`-Eigenschaft überprüft, ob die Variable einen Wert enthält. Erst danach erfolgt die Ausgabe:
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
Sie können eine Variable eines Nullable-Typs auch mit `null` anstelle der `HasValue`-Eigenschaft vergleichen, wie im folgenden Beispiel gezeigt wird:  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

Ab C# 7.0 können Sie den [Musterabgleich](../../pattern-matching.md) verwenden, um einen Wert eines Nullable-Typs zu untersuchen und abzurufen:

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a>Konvertieren eines Nullable-Typs in einen zugrunde liegenden Typ

Wenn Sie einem Nicht-Nullable-Typ den Wert eines Nullable-Typs zuweisen müssen, verwenden Sie den [NULL-Sammeloperator`??`](../../language-reference/operators/null-coalescing-operator.md), um den Wert anzugeben, der zugewiesen werden soll, wenn ein Nullable-Typwert NULL ist (hierzu können Sie auch die <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>-Methode verwenden):
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>-Methode, wenn der Wert, der im Fall eines NULL-Werts des Nullable-Typs verwendet werden soll, der Standardwert des zugrunde liegenden Werttyps sein soll.
  
Sie können einen Nullable-Typ explizit in einen Nicht-Nullable-Typ umwandeln. Beispiel:  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

Wenn der Wert eines Nullable-Typs zur Laufzeit NULL ist, wird durch die explizite Umwandlung eine <xref:System.InvalidOperationException> ausgelöst.

Ein Nicht-Nullable-Werttyp wird implizit in den entsprechenden Nullable-Typ konvertiert.
  
## <a name="operators"></a>Operatoren

Die vordefinierten unären und binären Operatoren und alle benutzerdefinierten Operatoren für Werttypen können auch von auf NULL festlegbaren Typen verwende werden. Durch die Operatoren wird ein NULL-Wert erzeugt, wenn ein oder beide Operanden NULL sind. Andernfalls verwenden die Operatoren die enthaltenen Werte zur Berechnung eines Ergebnisses. Beispiel:  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> Für den `bool?`-Typ gelten für die vordefinierten Operatoren `&` und `|` nicht die in diesem Abschnitt beschriebenen Regeln. Die Auswertung eines Operators kann auch dann einen anderen Wert als NULL ergeben, wenn einer der beiden Operanden NULL ist. Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../../language-reference/operators/boolean-logical-operators.md).
  
Wenn bei relationalen Operatoren (`<`, `>`, `<=`, `>=`) ein oder beide Operanden NULL sind, ist das Ergebnis `false`. Falsch wäre die Annahme, dass im Fall des Rückgabewerts `false` für einen bestimmten Vergleich (beispielsweise `<=`) der gegenteilige Vergleich (`>`) `true` zurückgibt. Das folgende Beispiel zeigt, dass 10

- weder größer als oder gleich NULL
- noch kleiner als NULL ist.
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
Das obige Beispiel demonstriert außerdem, dass ein Gleichheitsvergleich zweier Nullable-Typen, die beide NULL sind, `true` ergibt.

Weitere Informationen finden Sie im Abschnitt [Transformierte Operatoren](~/_csharplang/spec/expressions.md#lifted-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="boxing-and-unboxing"></a>Boxing und Unboxing

Für einen Nullable-Werttyp wird das [Boxing](../types/boxing-and-unboxing.md) entsprechend der folgenden Regeln durchgeführt:

- Wenn <xref:System.Nullable%601.HasValue%2A> `false` zurückgibt, wird der Nullverweis erstellt.  
- Wenn <xref:System.Nullable%601.HasValue%2A> `true` zurückgibt, wird nicht für eine Instanz von <xref:System.Nullable%601>, sondern für einen Wert des zugrunde liegenden Werttyps `T` das Boxing durchgeführt.

Sie können den Werttyp, für den das Boxing durchgeführt wurde, mittels Unboxing in den entsprechenden Nullable-Typ umwandeln, wie im folgenden Beispiel gezeigt wird:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a>Siehe auch

- [Nullable-Typen](index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was bedeutet „Lifted“ genau?)
