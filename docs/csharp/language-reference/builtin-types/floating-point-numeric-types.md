---
title: Numerische Gleitkommatypen – C#-Referenz
description: Übersicht über die integrierten C#-Gleitkommatypen
ms.date: 06/30/2019
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
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664190"
---
# <a name="floating-point-numeric-types-c-reference"></a>Numerische Gleitkommatypen (C#-Referenz)

Die **Gleitkommatypen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#floating-point-literals) initialisiert werden. Alle Gleitkommatypen sind auch Werttypen. Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison- und equality](../operators/equality-operators.md)-Operatoren.

Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für die Gleitkommatypen:
  
|Typ|Ungefährer Bereich|Genauigkeit|  
|----------|-----------------------|---------------|  
|`float`|±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup>|~6–9 Stellen|  
|`double`|±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup>|~15–17 Stellen|  
|`decimal`|±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup>|28-29 Stellen|  

Der Standardwert für alle Gleitkommatypen lautet `0`. Jeder der Gleitkommatypen hat Konstanten mit den Namen `MinValue` und `MaxValue` für den minimalen und maximalen Wert für diesen Typ. Die Typen `float` und `double` weisen zusätzliche Konstanten für `PositiveInfinity`, `NegativeInfinity` und `NaN` (für „Not a Number“ (keine Zahl)) auf. Der Typ `decimal` enthält Konstanten für `Zero`, `One` und `MinusOne`.

Der `decimal`-Typ verfügt über höhere Genauigkeit und einen kleineren Wertebereich als `float` und `double`. Dadurch eignet er sich für Finanz- und Währungskalkulationen.

Sie können ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren. In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert. Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:

- Wenn einer der Gleitkommatypen `double` ist, wertet der Ausdruck in relationalen Vergleichen oder in Vergleichen auf Gleichheit nach `double` oder [bool](../keywords/bool.md) aus.
- Wenn kein `double`-Typ in dem Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](../keywords/bool.md) ausgewertet.

Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:

- Positiv und negativ 0 (null)
- Positiv und negativ unendlich
- Not-a-Number-Wert (NaN)
- Die begrenzte Menge von Werten ungleich Null

Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.

Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.

## <a name="floating-point-literals"></a>Gleitkommaliterale

Ein numerisches Gleitkommaliteral auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt. Sie können Suffixe verwenden, um ein Gleitkommaliteral oder ein integrales Literal in einen bestimmten Typ zu konvertieren:

- Mit dem `d`- oder `D`-Suffix wird ein Literal in ein `double` konvertiert.
- Mit dem `f`- oder `F`-Suffix wird ein Literal in ein `float` konvertiert.
- Mit dem `m`- oder `M`-Suffix wird ein Literal in ein `decimal` konvertiert.

In den folgenden Beispielen werden die einzelnen Suffixe dargestellt:

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a>Konvertierungen

Es gibt eine implizite Konvertierung (als *erweiternde Konvertierung* bezeichnet) von `float` nach `double`, da der Bereich der `float`-Werte eine korrekte Teilmenge von `double` ist. Es entsteht kein Präzisionsverlust von `float` nach `double`. 

Sie müssen eine explizite Umwandlung verwenden, um einen Gleitkommatyp in einen anderen Gleitkommatyp zu konvertieren, wenn keine implizite Konvertierung vom Quelltyp in den Zieltyp definiert ist. Dies wird als *einschränkende Konvertierung* bezeichnet. Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann. Es gibt keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ, da der `decimal`-Typ eine höhere Genauigkeit als `float` oder `double` aufweist.

Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).

Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Integrale Typen](integral-numeric-types.md)
- [Tabelle für Standardwerte](../keywords/default-values-table.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](../keywords/formatting-numeric-results-table.md)
- [Tabelle integrierter Typen](../keywords/built-in-types-table.md)
- [Numerische Ausdrücke in .NET](../../../standard/numerics.md)
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)
- [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md)
- [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
