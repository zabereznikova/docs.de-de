---
title: Numerische Gleitkommatypen – C#-Referenz
description: Übersicht über die integrierten C#-Gleitkommatypen
ms.date: 10/22/2019
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
ms.openlocfilehash: 23aa33c6887db48a12f995efc5e1e2220d30216c
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552279"
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

- Wenn einer der Gleitkommatypen `double` ist, wird der Ausdruck in `double` oder in [bool](bool.md) in relationalen Vergleichen oder in Vergleichen auf Gleichheit ausgewertet.
- Wenn kein `double`-Typ im Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](bool.md) ausgewertet.

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

Es gibt nur eine implizite Konvertierung zwischen numerischen Gleitkommatypen: von `float` zu `double`. Allerdings können Sie einen Gleitkommatyp mit der [expliziten Umwandlung](../operators/type-testing-and-cast.md#cast-operator-)in beliebige andere Gleitkommatypen konvertieren. Weitere Informationen finden Sie unter [Built-in numeric conversions](numeric-conversions.md) (Integrierte numerische Konvertierungen).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Gleitkommatypen](~/_csharplang/spec/types.md#floating-point-types)
- [Der Dezimaltyp](~/_csharplang/spec/types.md#the-decimal-type)
- [Real-Literale](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Tabelle integrierter Typen](../keywords/built-in-types-table.md)
- [Integrale Typen](integral-numeric-types.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](../keywords/formatting-numeric-results-table.md)
- [Standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md)
- [Numerische Ausdrücke in .NET](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
