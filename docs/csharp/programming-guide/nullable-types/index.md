---
title: Werttypen, die Nullwerte zulassen – C#-Programmierhandbuch
ms.custom: seodec18
description: Informationen zu Werttypen, die Nullwerte zulassen, in C# und der Verwendung dieser Typen
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#]
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: b8b52e7fb34adf65d5c76d59811ea6dd0ab16a98
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396220"
---
# <a name="nullable-value-types-c-programming-guide"></a>Werttypen, die Nullwerte zulassen (C#-Programmierhandbuch)

Werttypen, die Nullwerte zulassen, sind Instanzen der <xref:System.Nullable%601?displayProperty=nameWithType>-Struktur. Werttypen, die Nullwerte zulassen, können alle Werte eines zugrunde liegenden `T`-Typs und einen zusätzlichen [NULL](../../language-reference/keywords/null.md)-Wert darstellen. Der zugrunde liegende Typ `T` kann jeder [Werttyp](../../language-reference/keywords/value-types.md) sein, der keine NULL-Werte zulässt. `T` kann kein Referenztyp sein.

> [!NOTE]
> C# 8.0 führt das Feature der Nullverweistypen ein. Weitere Informationen finden Sie unter [Nullverweistypen](../../nullable-references.md). Die Werttypen, die Nullwerte zulassen, sind ab C# 2 verfügbar.

Sie können beispielsweise `null` oder jeden anderen Integerwert von <xref:System.Int32.MinValue?displayProperty=nameWithType> bis <xref:System.Int32.MaxValue?displayProperty=nameWithType> einem `Nullable<int>`-, [TRUE](../../language-reference/keywords/true-literal.md)- und [FALSE](../../language-reference/keywords/false-literal.md)-Wert zuweisen, oder `null` zu `Nullable<bool>`.

Sie verwenden einen Werttyp, der Nullwerte zulässt, wenn Sie den nicht definierten Wert eines zugrunde liegenden Typs darstellen müssen. Eine boolesche Variable darf nur zwei Werte besitzen: `true` und `false`. Es gibt keinen „nicht definierten“ Wert. In den meisten Programmierungsanwendungen – allen voran Datenbankinteraktionen – kann ein Variablenwert in einem nicht definierten Zustand vorkommen oder fehlen. Ein Feld in einer Datenbank kann z.B. die Werte TRUE und FALSE enthalten; ebenso kann es aber auch gar keinen Wert enthalten. In diesem Fall verwenden Sie einen `Nullable<bool>`-Typ.

Werttypen, die Nullwerte zulassen, weisen die folgenden Eigenschaften auf:

- Werttypen, die Nullwerte zulassen, stellen Werttypvariablen dar, denen der `null`-Wert zugewiesen werden kann.

- Die Syntax `T?` ist eine Kurzform für `Nullable<T>`. Die beiden Formen sind austauschbar.

- Sie weisen einem Werttyp, der Nullwerte zulässt, einen Wert genauso zu, wie Sie es für einen zugrunde liegenden Werttyp tun würden: `int? x = 10;` oder `double? d = 4.108;`. Sie können ebenfalls den `null`-Wert zuweisen: `int? x = null;`.

- Verwenden Sie die schreibgeschützten Eigenschaften <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> und <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType>, um auf NULL zu prüfen und den Wert abzurufen, wie im folgenden Beispiel gezeigt: `if (x.HasValue) y = x.Value;`

  - Die Eigenschaft <xref:System.Nullable%601.HasValue%2A> gibt `true` zurück, wenn die Variable einen Wert enthält, oder sie gibt `false` zurück, wenn die Variable `null` ist.

  - Die Eigenschaft <xref:System.Nullable%601.Value%2A> gibt einen Wert zurück, sofern <xref:System.Nullable%601.HasValue%2A> `true` zurückgibt. Andernfalls wird eine <xref:System.InvalidOperationException> ausgelöst.

- Sie können wie im folgenden Beispiel dargestellt auch die Operatoren `==` und `!=` mit einem Werttyp, der Nullwerte zulässt, verwenden: `if (x != null) y = x.Value;`. Wenn `a` und `b` jeweils NULL sind, ergibt `a == b` `true`.

- Ab C# 7.0 können Sie den [Musterabgleich](../../pattern-matching.md#the-is-type-pattern-expression) verwenden, um einen Wert eines Nullable-Typs zu untersuchen und abzurufen: `if (x is int valueOfX) y = valueOfX;`.

- Der Standardwert von `T?` ist eine Instanz, deren <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` zurückgibt.

- Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault>-Methode, um entweder den zugewiesenen Wert oder den [Standardwert](../../language-reference/keywords/default-values-table.md) für den zugrunde liegenden Werttyp zurückzugeben, wenn der Wert des Nullable-Typs `null` ist.

- Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault(%600)>-Methode, um entweder den zugewiesenen Wert oder den bereitgestellten Standardwert zurückzugeben, wenn der Wert des Nullable-Typs `null` ist.

- Verwenden Sie den [NULL-Sammeloperator](../../language-reference/operators/null-coalescing-operator.md) `??`, um einer Variable eines zugrunde liegenden Werttyps einen Wert basierend auf einem Wert zuzuweisen, der Nullwerte zulässt: `int? x = null; int y = x ?? -1;`. Da `x` `null` ist, ist in diesem Beispiel der Ergebniswert von `y` `-1`.

- Wenn eine benutzerdefinierte Konvertierung zwischen zwei Werttypen definiert ist, kann die gleiche Konvertierung auch mit den entsprechenden Nullable-Typen verwendet werden.

- Geschachtelte Werttypen, die Nullwerte zulassen, sind nicht zulässig. Die folgende Zeile wird nicht kompiliert: `Nullable<Nullable<int>> n;`

Weitere Informationen finden Sie unter [Verwenden von Werttypen, die Nullwerte zulassen](using-nullable-types.md) und [Vorgehensweise: Identifizieren eines Werttyps, der Nullwerte zulässt](how-to-identify-a-nullable-type.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [?? Operator](../../language-reference/operators/null-coalescing-operator.md)
- [Auf NULL festlegbare Werttypen (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
