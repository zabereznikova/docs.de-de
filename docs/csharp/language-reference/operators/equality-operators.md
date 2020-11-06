---
title: Gleichheitsoperatoren – C#-Referenz
description: Erfahren Sie mehr über Gleichheitsvergleichsoperatoren und C#-Typengleichheit.
ms.date: 10/30/2020
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 39461157c33fea0effb5c8808ded1c9981900e17
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063214"
---
# <a name="equality-operators-c-reference"></a>Gleichheitsoperatoren (C#-Referenz)

Die Operatoren [`==` (Gleichheit)](#equality-operator-) und [`!=` (Ungleichheit)](#inequality-operator-) überprüfen, ob die Operanden gleich sind oder nicht.

## <a name="equality-operator-"></a>Gleichheitsoperator ==

Der Gleichheitsoperator `==` gibt `true` zurück, wenn die Operanden gleich sind; andernfalls `false`.

### <a name="value-types-equality"></a>Gleichheit von Werttypen

Operanden der [integrierten Werttypen](../builtin-types/value-types.md#built-in-value-types) sind gleich, wenn ihre Werte gleich sind:

[!code-csharp-interactive[value types equality](snippets/shared/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> Bei den Operatoren `==`, [`<`, `>`, `<=` und `>=`](comparison-operators.md) ist das Ergebnis eines Vorgangs `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>). Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`. Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.

Zwei Operanden desselben [enum](../builtin-types/enum.md)-Typs sind gleich, wenn die entsprechenden Werte des zugrunde liegenden integralen Typs gleich sind.

Benutzerdefinierte [Strukturtypen](../builtin-types/struct.md) unterstützen den `==`-Operator nicht standardmäßig. Eine benutzerdefinierte Struktur muss den `==`-Operator [überladen](operator-overloading.md), damit er unterstützt wird.

Ab C# 7.3 werden die Operatoren `==` und `!=` für [C#-Tupel](../builtin-types/value-tuples.md) unterstützt. Weitere Informationen finden Sie im Abschnitt [Tupelgleichheit](../builtin-types/value-tuples.md#tuple-equality) im Artikel [Tupeltypen](../builtin-types/value-tuples.md).

### <a name="reference-types-equality"></a>Gleichheit von Verweistypen

Standardmäßig sind zwei Verweistypoperanden, die keine Datensätze darstellen, gleich, wenn sie auf dasselbe Objekt verweisen:

[!code-csharp[reference type equality](snippets/shared/EqualityOperators.cs#ReferenceTypesEquality)]

Das Beispiel zeigt, dass benutzerdefinierte Verweistypen den `==`-Operator standardmäßig unterstützen. Ein Verweistyp kann den Operator `==` aber überladen. Wenn ein Verweistyp den `==`-Operator überlädt, verwenden Sie die <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode, um zu überprüfen, ob zwei Verweise dieses Typs auf dasselbe Objekt verweisen.

### <a name="record-types-equality"></a>Gleichheit von Datensatztypen

[Datensatztypen](../../whats-new/csharp-9.md#record-types) sind in C# 9.0 und höher verfügbar und unterstützen die Operatoren `==` und `!=`, die standardmäßig Semantik für Wertgleichheit ausdrücken. Das bedeutet, dass zwei Datensatzoperanden gleich sind, wenn beide gleich `null` oder die entsprechenden Werte aller Felder sowie die automatisch implementierten Eigenschaften gleich sind.

:::code language="csharp" source="snippets/shared/EqualityOperators.cs" id="RecordTypesEquality":::

Wie das vorherige Beispiel zeigt, werden bei Verweistypmembern, die keine Datensätze sind, die Verweiswerte verglichen, nicht die referenzierten Instanzen.

### <a name="string-equality"></a>Zeichenfolgengleichheit

Zwei [Zeichenfolge](../builtin-types/reference-types.md#the-string-type)-Operanden gleich sind, wenn beide gleich `null` sind oder wenn beide Zeichenfolgeninstanzen dieselbe Länge und identische Zeichen in jeder Zeichenposition haben:

[!code-csharp-interactive[string equality](snippets/shared/EqualityOperators.cs#StringEquality)]

Dies ist ein Ordinalvergleich unter Berücksichtigung der Groß-/Kleinschreibung. Weitere Informationen zum Zeichenfolgenvergleich finden Sie unter [Vergleichen von Zeichenfolgen in C#](../../how-to/compare-strings.md).

### <a name="delegate-equality"></a>Delegatengleichheit

Zwei [delegate](../../programming-guide/delegates/index.md)-Operanden mit demselben Laufzeittyp sind gleich, wenn beide `null` lauten oder ihre Aufruflisten die gleiche Länge aufweisen und an jeder Position gleiche Einträge umfassen:

[!code-csharp-interactive[delegate equality](snippets/shared/EqualityOperators.cs#DelegateEquality)]

Weitere Informationen finden Sie im Abschnitt [Operatoren für Delegatengleichheit](~/_csharplang/spec/expressions.md#delegate-equality-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Delegaten, die durch die Auswertung semantisch identischer [Lambdaausdrücke](lambda-expressions.md) erzeugt werden, sind beispielsweise nicht gleich. Dies wird im folgenden Beispiel gezeigt:

[!code-csharp-interactive[from identical lambdas](snippets/shared/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a>Ungleichheitsoperator !=

Der Ungleichheitsoperator `!=` gibt `true` zurück, wenn die Operanden nicht gleich sind; andernfalls `false`. Für die Operanden der [integrierten Typen](../builtin-types/built-in-types.md) führt der Ausdruck `x != y` zum selben Ergebnis wie der Ausdruck `!(x == y)`. Weitere Informationen zur Typengleichheit finden Sie im Abschnitt [Gleichheitsoperator](#equality-operator-).

Im folgenden Beispiel wird die Verwendung des `!=`-Operators veranschaulicht:

[!code-csharp-interactive[non-equality examples](snippets/shared/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann die Operatoren `==` und `!=`[überladen](operator-overloading.md). Wenn ein Typ einen der zwei Operatoren überlädt, muss er auch den anderen Operator überladen.

Ein Datensatztyp kann die Operatoren `==` und `!=` nicht explizit überladen. Wenn Sie das Verhalten der Operatoren `==` und `!=` für den Datensatztyp `T` ändern müssen, implementieren Sie die Methode <xref:System.IEquatable%601.Equals%2A?displayProperty=nameWithType> mit der folgenden Signatur:

```csharp
public virtual bool Equals(T? other);
```

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

Weitere Informationen zur Gleichheit von Datensatztypen finden Sie im Abschnitt [Gleichheitsmember](~/_csharplang/proposals/csharp-9.0/records.md#equality-members) des Artikels [Datensätze](~/_csharplang/proposals/csharp-9.0/records.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Übereinstimmungsvergleiche](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [Vergleichsoperatoren](comparison-operators.md)
