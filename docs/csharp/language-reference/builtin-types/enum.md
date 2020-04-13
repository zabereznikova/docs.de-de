---
title: 'Enumerationstypen: C#-Referenz'
description: Weitere Informationen zu C#-Enumerationstypen, die eine Auswahl oder eine Kombination aus Auswahlmöglichkeiten darstellen
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 15f5e9ccb1396277229ba935381812700f63ece8
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121157"
---
# <a name="enumeration-types-c-reference"></a>Enumerationstypen (C#-Referenz)

Ein *Enumerationstyp* (oder *enum-Typ*) ist ein [Werttyp](value-types.md), der durch eine Reihe benannter Konstanten des zugrunde liegenden [integralen numerischen](integral-numeric-types.md) Typs definiert wird. Um einen Enumerationstyp zu definieren, verwenden Sie das `enum`-Schlüsselwort und geben die Namen von *Enumerationsmembern* an:

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

Standardmäßig sind die zugeordneten Konstantenwerte von Enumerationsmembern vom Typ `int`. Sie beginnen mit null und erhöhen sich um eins gemäß der Definitionstextreihenfolge. Sie können einen beliebigen anderen [integralen numerischen](integral-numeric-types.md) Typ als zugrunde liegenden Typ eines Enumerationstyps explizit angeben. Sie können auch explizit die zugeordneten Konstantenwerte angeben, wie im folgenden Beispiel gezeigt:

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

In der Definition eines Enumerationstyps kann keine Methode definiert werden. Zum Hinzufügen von Funktionen zu einem Enumerationstyp erstellen Sie eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md).

Der Standardwert eines Enumerationstyps `E` ist der Wert, der vom Ausdruck `(E)0` generiert wird, auch wenn NULL nicht über den entsprechenden Enumerationsmember verfügt.

Sie verwenden einen Enumerationstyp, um eine Auswahl aus einer Reihe von sich gegenseitig ausschließenden Werten oder eine Kombination aus Auswahlmöglichkeiten darzustellen. Um eine Kombination aus Auswahlmöglichkeiten darzustellen, definieren Sie einen Enumerationstyp als Bitflags.

## <a name="enumeration-types-as-bit-flags"></a>Enumerationstypen als Bitflags

Wenn ein Enumerationstyp eine Kombination aus Auswahlmöglichkeiten darstellen soll, definieren Sie Enumerationsmember für diese Auswahlmöglichkeiten, sodass eine einzelne Auswahl ein Bitfeld ist. Das heißt, die zugeordneten Werte dieser Enumerationsmember sollten Zweierpotenzen sein. Anschließend können Sie die [bitweisen logischen Operatoren `|` oder `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) verwenden, um Auswahlmöglichkeiten bzw. Schnittmengen von Auswahlmöglichkeiten zu kombinieren. Um anzugeben, dass ein Enumerationstyp Bitfelder deklariert, wenden Sie das Attribut [Flags](xref:System.FlagsAttribute) darauf an. Wie im folgenden Beispiel gezeigt, können Sie auch einige typische Kombinationen in die Definition eines Enumerationstyps einschließen.

[!code-csharp[enum flags](snippets/EnumType.cs#Flags)]

Weitere Informationen und Beispiele finden Sie auf der Referenzseite zur <xref:System.FlagsAttribute?displayProperty=nameWithType>-API und im Abschnitt [Nicht exklusive Member und das Flags-Attribut](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) der Referenzseite zur <xref:System.Enum?displayProperty=nameWithType>-API.

## <a name="the-systemenum-type-and-enum-constraint"></a>Der System.Enum-Typ und die enum-Einschränkung

Der <xref:System.Enum?displayProperty=nameWithType>-Typ ist die abstrakte Basisklasse aller Enumerationstypen. Er bietet eine Reihe von Methoden, um Informationen zu einem Enumerationstyp und seinen Werten abzurufen. Weitere Informationen und Beispiele finden Sie auf der Referenzseite zur <xref:System.Enum?displayProperty=nameWithType>-API.

Ab C# 7.3 können Sie `System.Enum` in einer Basisklasseneinschränkung (die als [enum-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints) bezeichnet wird) verwenden, um anzugeben, dass ein Typparameter ein Enumerationstyp ist.

## <a name="conversions"></a>Konvertierungen

Für jeden Enumerationstyp gibt es explizite Konvertierungen zwischen dem Enumerationstyp und dem zugrunde liegenden integralen Typ. Wenn Sie einen Enumerationswert in den zugrunde liegenden Typ [umwandeln](../operators/type-testing-and-cast.md#cast-expression), ist das Ergebnis der zugeordnete integrale Wert eines Enumerationsmembers.

[!code-csharp[enum conversions](snippets/EnumType.cs#Conversions)]

Verwenden Sie die <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>-Methode, um zu ermitteln, ob ein Enumerationstyp einen Enumerationsmember mit dem bestimmten zugeordneten Wert enthält.

Für jeden Enumerationstyp gibt es [Boxing- und Unboxing](../../programming-guide/types/boxing-and-unboxing.md)-Konvertierungen in bzw. aus dem <xref:System.Enum?displayProperty=nameWithType>-Typ.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Enumerationen](~/_csharplang/spec/enums.md)
- [Enum values and operations (Enumerationswerte und -vorgänge)](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [Logische Enumerationsoperatoren](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [Enumerationsvergleichsoperatoren](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [Explizite Enumerationskonvertierungen](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [Implizite Enumerationskonvertierungen](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [Enumerationsformatzeichenfolgen](../../../standard/base-types/enumeration-format-strings.md)
- [Entwurfsrichtlinien: Enumerationsentwurf](../../../standard/design-guidelines/enum.md)
- [Entwurfsrichtlinien: Namenskonventionen für Enumerationen](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [switch-Anweisung](../keywords/switch.md)
