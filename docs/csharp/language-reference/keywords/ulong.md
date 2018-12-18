---
title: ulong-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: 97db22612e900658746f40cd117ff941135027a1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235019"
---
# <a name="ulong-c-reference"></a>ulong (C#-Referenz)

Das `ulong`-Schlüsselwort kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.

|Typ|Bereich|Größe|.NET-Typ|
|----------|-----------|----------|-------------------------|
|`ulong`|0 bis 18.446.744.073.709.551.615|64-Bit-Ganzzahl ohne Vorzeichen|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>Literale

Sie können eine `ulong`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.  Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `ulong` befindet (sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ulong`-Werten zugewiesen.

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals. Dezimale Literale haben kein Präfix.

Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt:

- C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.
- C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu. Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.

Im Folgenden werden einige Beispiele veranschaulicht.

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet. Das Suffix `UL` oder `ul` identifiziert unzweideutig ein numerisches Literal als ein `ulong`-Wert. Das `L`-Suffix kennzeichnet ein `ulong`, wenn der Literalwert <xref:System.Int64.MaxValue?displayProperty=nameWithType> überschreitet. Das `U`- oder `u`-Suffix kennzeichnet ein `ulong`, wenn der Literalwert <xref:System.UInt32.MaxValue?displayProperty=nameWithType> überschreitet. Im folgenden Beispiel wird das `ul`-Suffix verwendet, um eine lange ganze Zahl anzugeben:

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>Überladungsauflösung des Compiler

Das Suffix wird häufig beim Aufrufen überladener Methoden verwendet. Dies ist z.B. in den folgenden überladenen Methoden der Fall, die die Parameter `ulong` und [int](int.md) verwenden:

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

Die Verwendung eines Suffixes mit dem Parameter `ulong` gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a>Konvertierungen

Es gibt eine vordefinierte implizite Konvertierung von `ulong` in [float](float.md), [double](double.md) oder [decimal](decimal.md).

Es gibt keine implizite Konvertierung von `ulong` in ganzzahlige Typen. Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne explizite Umwandlung:

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

Es gibt eine vordefinierte implizite Konvertierung von [byte](byte.md), [ushort](ushort.md), [uint](uint.md) oder [char](char.md) in `ulong`.

Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `ulong` gibt. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](float.md) und [double](double.md).

Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- <xref:System.UInt64>
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Tabelle ganzzahliger Typen](integral-types-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md)
- [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)
