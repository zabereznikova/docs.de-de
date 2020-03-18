---
title: 'Vergleichsoperatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Vergleichsoperatoren, mit denen Sie die Reihenfolge numerischer Werte überprüfen können.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 68502205193a1fc8ab7410053e13274560ffffb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398052"
---
# <a name="comparison-operators-c-reference"></a>Vergleichsoperatoren (C#-Referenz)

Die Vergleichsoperatoren [`<` (kleiner als)](#less-than-operator-), [`>` (größer als)](#greater-than-operator-), [`<=` (kleiner als oder gleich)](#less-than-or-equal-operator-) und [`>=` (größer als oder gleich)](#greater-than-or-equal-operator-) – auch bekannt als relationale Operatoren – vergleichen ihre Operanden. Diese Operatoren werden alle von numerischen [Ganzzahl](../builtin-types/integral-numeric-types.md)- und [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) unterstützt.

> [!NOTE]
> Bei den Operatoren `==`, `<`, `>`, `<=` und `>=` ist das Ergebnis eines Vorgangs gleich <xref:System.Double.NaN?displayProperty=nameWithType>, wenn einer der Operanden keine Zahl ist (<xref:System.Single.NaN?displayProperty=nameWithType> oder `false`). Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`. Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.

Enumerationstypen unterstützen auch Vergleichsoperatoren. Für Operanden desselben [enum](../builtin-types/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.

Die Operatoren [`==` und `!=`](equality-operators.md) überprüfen, ob die Operanden gleich sind oder nicht.

## <a name="less-than-operator-"></a>„Kleiner als“-Operator \<

Der `<`-Operator gibt `true` zurück, wenn sein linker Operand kleiner ist als sein rechter Operand, andernfalls `false`:

[!code-csharp-interactive[less than example](snippets/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>„Größer als“-Operator >

Der `>`-Operator gibt `true` zurück, wenn sein linker Operand größer ist als sein rechter Operand, andernfalls `false`:

[!code-csharp-interactive[greater than example](snippets/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>„Kleiner oder gleich“-Operator \<=

Der `<=`-Operator gibt `true` zurück, wenn sein linker Operand kleiner ist als der rechte Operand oder diesem entspricht, andernfalls `false`:

[!code-csharp-interactive[less than or equal example](snippets/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>„Größer oder gleich“-Operator >=

Der `>=`-Operator gibt `true` zurück, wenn sein linker Operand größer ist als der rechte Operand oder diesem entspricht, andernfalls `false`:

[!code-csharp-interactive[greater than or equal example](snippets/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann die Operatoren [, ](operator-overloading.md), `<` und `>``<=`überladen`>=`.

Wenn ein Typ einen der `<`- oder `>`-Operatoren überlädt, muss er sowohl `<` als auch `>` überladen. Wenn ein Typ einen der `<=`- oder `>=`-Operatoren überlädt, muss er sowohl `<=` als auch `>=` überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Gleichheitsoperatoren](equality-operators.md)
