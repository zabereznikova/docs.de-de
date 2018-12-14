---
title: uint-Schlüsselwort (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 86cbb216bd960251ebd78916fae7865aa10aa5fc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149691"
---
# <a name="uint-c-reference"></a>uint (C#-Referenz)

Das Schlüsselwort `uint` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.

|Typ|Bereich|Größe|.NET-Typ|
|----------|-----------|----------|-------------------------|
|`uint`|0 bis 4.294.967.295|32-Bit Ganzzahl ohne Vorzeichen|<xref:System.UInt32?displayProperty=nameWithType>|

**Hinweis** Der Typ `uint` ist nicht CLS-kompatibel. Verwenden Sie nach Möglichkeit `int`.

## <a name="literals"></a>Literale

Sie können eine `uint`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen. Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `uint` befindet (sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `uint`-Werten zugewiesen.

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals. Dezimale Literale haben kein Präfix.

Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt:

- C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.
- C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu. Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.

Im Folgenden werden einige Beispiele veranschaulicht.

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet. Das Suffix `U` oder „u“ gibt entweder ein `uint` oder `ulong` an, abhängig vom numerischen Wert des Literals. Im folgenden Beispiel wird das `u`-Suffix verwendet, um eine ganze Zahl ohne Vorzeichen von beiden Typen zu kennzeichnen. Beachten Sie, dass das erste Literal ein `uint` ist, weil sein Wert kleiner als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist, während das zweite ein `ulong` ist, weil sein Wert größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist.

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:

1. [int](int.md)
2. `uint`
3. [long](long.md)
4. [ulong](ulong.md)

## <a name="conversions"></a>Konvertierungen

Es gibt eine vordefinierte implizite Konvertierung von `uint` in [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) oder [decimal](decimal.md). Beispiel:

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

Es gibt eine vordefinierte implizite Konvertierung von [byte](byte.md), [ushort](ushort.md) oder [char](char.md) in `uint`. Andernfalls müssen Sie eine Umwandlung verwenden. Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne Umwandlung:

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `uint` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](float.md) und [double](double.md).

Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- <xref:System.UInt32>
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Tabelle ganzzahliger Typen](integral-types-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md)
- [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)