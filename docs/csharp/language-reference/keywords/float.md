---
title: float-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: 4ca256bf7204cdaad7d49ed19c662ab81bb01bf9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242450"
---
# <a name="float-c-reference"></a>float (C#-Referenz)

Das `float`-Schlüsselwort kennzeichnet einen einfachen Typ, der 32-Bit-Gleitkommawerte speichert. Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `float`-Typ an.

|Typ|Ungefährer Bereich|Genauigkeit|.NET-Typ|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup>|~6–9 Stellen|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a>Literale

Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als [Double-Datentyp](double.md) behandelt. Verwenden Sie daher zum Initialisieren einer Float-Variablen die Suffixe `f` oder `F`, wie im folgenden Beispiel:

```csharp
float x = 3.5F;
```

Wenn Sie das Suffix in der vorherigen Deklaration nicht verwenden, erhalten Sie einen Kompilierungsfehler, da ein [double](double.md)-Wert in einer `float`-Variablen gespeichert werden soll.

## <a name="conversions"></a>Konvertierungen

Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren. In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert. Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:

- Wenn einer der Gleitkommatypen [double](double.md) ist, wertet der Ausdruck in relationalen Vergleichen oder in Vergleichen auf Gleichheit nach [double](double.md) oder [bool](bool.md) aus.

- Wenn kein [double](double.md)-Typ in dem Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](bool.md) ausgewertet.

Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:

- Positiv und negativ 0 (null)

- Positiv und negativ unendlich

- Not-a-Number-Wert (NaN)

- Die begrenzte Menge von Werten ungleich Null

Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden ein [int](int.md)-, ein [short](short.md) und ein `float`-Datentyp in einem mathematischen Ausdruck verwendet, der ein `float`-Ergebnis aufweist. (Beachten Sie, dass `float` ein Alias für den Typ <xref:System.Single?displayProperty=nameWithType> ist.) Beachten Sie auch, dass es in diesem Ausdruck keine [Double-Datentypen](double.md) gibt.

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Single>  
- [C#-Referenz](../index.md)  
- [C#-Programmierhandbuch](../../programming-guide/index.md)  
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)  
- [C#-Schlüsselwörter](index.md)  
- [Tabelle ganzzahliger Typen](integral-types-table.md)  
- [Tabelle integrierter Typen](built-in-types-table.md)  
- [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md)  
- [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)  