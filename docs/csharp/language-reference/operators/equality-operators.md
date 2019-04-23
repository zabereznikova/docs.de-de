---
title: Gleichheitsoperatoren – C#-Referenz
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 297285ccb9aba7eae1d70a7d28a62241646a023c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334158"
---
# <a name="equality-operators-c-reference"></a>Gleichheitsoperatoren (C#-Referenz)

Die Operatoren [`==` (Gleichheit)](#equality-operator-) und [`!=` (Ungleichheit)](#inequality-operator-) überprüfen, ob die Operanden gleich sind oder nicht.

## <a name="equality-operator-"></a>Gleichheitsoperator ==

Der Gleichheitsoperator `==` gibt `true` zurück, wenn die Operanden gleich sind; andernfalls `false`.

### <a name="value-types-equality"></a>Gleichheit von Werttypen

Operanden der [integrierten Werttypen](../keywords/value-types-table.md) sind gleich, wenn ihre Werte gleich sind:

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> Für die Gleichheits- und relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>). Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`. Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.

Zwei Operanden desselben [enum](../keywords/enum.md)-Typs sind gleich, wenn die entsprechenden Werte des zugrunde liegenden integralen Typs gleich sind.

Benutzerdefinierte [Strukturtypen](../keywords/struct.md) unterstützen den `==`-Operator nicht standardmäßig. Eine benutzerdefinierte Struktur muss den `==`-Operator [überladen](#operator-overloadability), damit er unterstützt wird.

Ab C# 7.3 werden die Operatoren `==` und `!=` für [C#-Tupel](../../tuples.md) unterstützt. Weitere Informationen finden Sie im Abschnitt [Gleichheit und Tupel](../../tuples.md#equality-and-tuples) im Artikel [C#-Tupeltypen](../../tuples.md).

### <a name="string-equality"></a>Zeichenfolgengleichheit

Zwei [Zeichenfolge](../keywords/string.md)-Operanden gleich sind, wenn beide gleich `null` sind oder wenn beide Zeichenfolgeninstanzen dieselbe Länge und identische Zeichen in jeder Zeichenposition haben:

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

Dies ist ein Ordinalvergleich mit Berücksichtigung der Groß-/Kleinschreibung. Weitere Informationen zum Zeichenfolgenvergleich finden Sie unter [Vergleichen von Zeichenfolgen in C#](../../how-to/compare-strings.md).

### <a name="reference-types-equality"></a>Gleichheit von Verweistypen

Zwei Verweistypoperanden ungleich `string` sind gleich, wenn sie auf dasselbe Objekt verweisen:

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

Das Beispiel zeigt, dass benutzerdefinierte Verweistypen den `==`-Operator standardmäßig unterstützen. Ein benutzerdefinierter Verweistyp kann den `==`-Operator aber überladen. Wenn ein Verweistyp den `==`-Operator überlädt, verwenden Sie die <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode, um zu überprüfen, ob zwei Verweise dieses Typs auf dasselbe Objekt verweisen.

## <a name="inequality-operator-"></a>Ungleichheitsoperator !=

Der Ungleichheitsoperator `!=` gibt `true` zurück, wenn die Operanden nicht gleich sind; andernfalls `false`. Für die Operanden der [integrierten Typen](../keywords/built-in-types-table.md) führt der Ausdruck `x != y` zum selben Ergebnis wie der Ausdruck `!(x == y)`. Weitere Informationen zur Typengleichheit finden Sie im Abschnitt [Gleichheitsoperator](#equality-operator-).

Im folgenden Beispiel wird die Verwendung des `!=`-Operators veranschaulicht:

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann die Operatoren `==` und `!=` [überladen](../keywords/operator.md). Wenn ein Typ einen der beiden Operatoren überlädt, muss er auch den anderen Operator überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Übereinstimmungsvergleiche](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
