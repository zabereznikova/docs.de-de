---
title: Schlüsselwort „double“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 4c11065d9354d44c1da8354c6f7b4f52d7b84c10
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594027"
---
# <a name="double-c-reference"></a>double (C#-Referenz)

Das `double`-Schlüsselwort kennzeichnet einen einfachen Typ, der 64-Bit-Gleitkommawerte speichert. Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `double`-Typ an.

|Typ|Ungefährer Bereich|Genauigkeit|.NET-Typ|
|----------|-----------------------|---------------|-------------------------|
|`double`|±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup>|15-16 Ziffern|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a>Literale

Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt. Aber wenn Sie eine ganze Zahl als `double` behandeln möchten, verwenden Sie das Suffix d oder D, beispielsweise:

```csharp
double x = 3D;
```

## <a name="conversions"></a>Konvertierungen

Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren. In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert. Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:

- Wenn einer der Gleitkommatypen `double` ist, wertet der Ausdruck in relationalen Vergleichen und in Vergleichen auf Gleichheit nach `double` oder [bool](../../../csharp/language-reference/keywords/bool.md) aus.

- Wenn in dem Ausdruck kein `double`-Typ vorhanden ist, wird der Ausdruck in relationalen Vergleichen und Vergleichen auf Gleichheit in [float](../../../csharp/language-reference/keywords/float.md) oder [bool](../../../csharp/language-reference/keywords/bool.md) ausgewertet.

 Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:

- Positive und negative null

- Positive und negative Infinity

- Not-a-Number-Wert (NaN)

- Die begrenzte Menge von Werten ungleich Null

Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden ein [int](../../../csharp/language-reference/keywords/int.md), ein [short](../../../csharp/language-reference/keywords/short.md),ein [float](../../../csharp/language-reference/keywords/float.md) und ein `double` zusammen addiert, was ein `double`-Ergebnis ergibt.

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md)  
- [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Tabelle für Gleitkommatypen](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
- [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
