---
title: Numerische Gleitkommatypen – C#-Referenz
description: Übersicht über die integrierten C#-Gleitkommatypen
ms.date: 10/18/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: fa6cbb869d90113414cc6f8ffe231386c3596b1d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579371"
---
# <a name="floating-point-numeric-types-c-reference"></a>Numerische Gleitkommatypen (C#-Referenz)

Die **Gleitkommatypen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#real-literals) initialisiert werden. Alle Gleitkommatypen sind auch Werttypen. Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison](../operators/comparison-operators.md)- und [equality](../operators/equality-operators.md)-Operatoren.

## <a name="characteristics-of-the-floating-point-types"></a>Merkmale der Gleitkommatypen

C# unterstützt die folgenden vordefinierten Gleitkommatypen:
  
|C#-Typ/Schlüsselwort|Ungefährer Bereich|Genauigkeit|Größe|.NET-Typ|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup>|~6–9 Stellen|4 Bytes|<xref:System.Single?displayProperty=nameWithType>|
|`double`|±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup>|~15–17 Stellen|8 Bytes|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup>|28-29 Stellen|16 Bytes|<xref:System.Decimal?displayProperty=nameWithType>|

In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ. Sie können synonym verwendet werden. In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:

```csharp
double a = 12.3;
System.Double b = 12.3;
```

Der Standardwert jedes Gleitkommatyps ist Null (`0`). Die einzelnen Gleitkommatypen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Endwert des Typs angeben. Die Typen `float` und `double` verfügen auch über Konstanten, die nicht numerische Werte und Unendlichkeitswerte darstellen. Der Typ `double` verfügt beispielsweise über folgende Konstanten: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> und <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.

Da der Typ `decimal` über eine höhere Genauigkeit und einen kleineren Bereich verfügt als `float` und `double`, eignet er sich für Finanz- und Währungskalkulationen.

Sie können [integrale](integral-numeric-types.md) Typen und Gleitkommatypen in einem Ausdruck kombinieren. In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert. Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:

- Wenn einer der Gleitkommatypen `double` ist, wird der Ausdruck in `double` oder in [bool](../keywords/bool.md) in relationalen Vergleichen oder in Vergleichen auf Gleichheit ausgewertet.
- Wenn kein `double`-Typ im Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](../keywords/bool.md) ausgewertet.

Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:

- Positiv und negativ 0 (null)
- Positiv und negativ unendlich
- Not-a-Number-Wert (NaN)
- Die begrenzte Menge von Werten ungleich Null

Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.

Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.

## <a name="real-literals"></a>Real-Literale

Der Typ eines Real-Literals wird wie folgt durch sein Suffix bestimmt:

- Das Literal ohne Suffix oder mit dem Suffix `d` oder `D` ist vom Typ `double`.
- Das Literal mit dem Suffix `f` oder `F` ist vom Typ `float`.
- Das Literal mit dem Suffix `m` oder `M` ist vom Typ `decimal`.

Der folgende Code zeigt ein Beispiel für jeden Typ:

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

Das vorherige Beispiel zeigt auch die Verwendung von `_` als *Zifferntrennzeichen*, das ab C# 7.0 unterstützt wird. Sie können das Zifferntrennzeichen mit allen Arten numerischer Literale verwenden.

Sie können auch die wissenschaftliche Notation verwenden, d.h. einen exponentiellen Teil eines Real-Literals angeben, wie das folgende Beispiel zeigt:

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>Konvertierungen

Es gibt eine implizite Konvertierung (als *erweiternde Konvertierung* bezeichnet) von `float` nach `double`, da der Bereich der `float`-Werte eine korrekte Teilmenge von `double` ist. Es entsteht kein Präzisionsverlust von `float` nach `double`.

Sie müssen eine explizite Umwandlung verwenden, um einen Gleitkommatyp in einen anderen Gleitkommatyp zu konvertieren, wenn keine implizite Konvertierung vom Quelltyp in den Zieltyp definiert ist. Dies wird als *einschränkende Konvertierung* bezeichnet. Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann. Es gibt keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ, da der `decimal`-Typ eine höhere Genauigkeit als `float` oder `double` aufweist.

Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).

Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Gleitkommatypen](~/_csharplang/spec/types.md#floating-point-types)
- [Der Dezimaltyp](~/_csharplang/spec/types.md#the-decimal-type)
- [Real-Literale](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Integrale Typen](integral-numeric-types.md)
- [Tabelle integrierter Typen](../keywords/built-in-types-table.md)
- [Numerische Ausdrücke in .NET](../../../standard/numerics.md)
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [Tabelle zur Formatierung numerischer Ergebnisse](../keywords/formatting-numeric-results-table.md)
- [Standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md)
