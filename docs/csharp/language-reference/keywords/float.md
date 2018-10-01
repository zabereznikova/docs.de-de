---
title: Schlüsselwort „float“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- float
- float_CSharpKeyword
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
ms.openlocfilehash: 98f89ba3d79f7679b69ce10fd875b3caf69c5257
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157703"
---
# <a name="float-c-reference"></a><span data-ttu-id="2ce1d-102">float (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2ce1d-102">float (C# Reference)</span></span>

<span data-ttu-id="2ce1d-103">Das `float`-Schlüsselwort kennzeichnet einen einfachen Typ, der 32-Bit-Gleitkommawerte speichert.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-103">The `float` keyword signifies a simple type that stores 32-bit floating-point values.</span></span> <span data-ttu-id="2ce1d-104">Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `float`-Typ an.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-104">The following table shows the precision and approximate range for the `float` type.</span></span>

|<span data-ttu-id="2ce1d-105">Typ</span><span class="sxs-lookup"><span data-stu-id="2ce1d-105">Type</span></span>|<span data-ttu-id="2ce1d-106">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="2ce1d-106">Approximate range</span></span>|<span data-ttu-id="2ce1d-107">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="2ce1d-107">Precision</span></span>|<span data-ttu-id="2ce1d-108">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="2ce1d-108">.NET type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|<span data-ttu-id="2ce1d-109">±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="2ce1d-109">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="2ce1d-110">7 Stellen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-110">7 digits</span></span>|<xref:System.Single?displayProperty=nameWithType>|  

## <a name="literals"></a><span data-ttu-id="2ce1d-111">Literale</span><span class="sxs-lookup"><span data-stu-id="2ce1d-111">Literals</span></span>

<span data-ttu-id="2ce1d-112">Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als [Double-Datentyp](double.md) behandelt.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-112">By default, a real numeric literal on the right side of the assignment operator is treated as [double](double.md).</span></span> <span data-ttu-id="2ce1d-113">Verwenden Sie daher zum Initialisieren einer Float-Variablen die Suffixe `f` oder `F`, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ce1d-113">Therefore, to initialize a float variable, use the suffix `f` or `F`, as in the following example:</span></span>

```csharp
float x = 3.5F;
```

<span data-ttu-id="2ce1d-114">Wenn Sie das Suffix in der vorherigen Deklaration nicht verwenden, erhalten Sie einen Kompilierungsfehler, da ein [double](double.md)-Wert in einer `float`-Variablen gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-114">If you do not use the suffix in the previous declaration, you will get a compilation error because you are trying to store a [double](double.md) value into a `float` variable.</span></span>

## <a name="conversions"></a><span data-ttu-id="2ce1d-115">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-115">Conversions</span></span>

<span data-ttu-id="2ce1d-116">Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-116">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="2ce1d-117">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-117">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="2ce1d-118">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="2ce1d-118">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="2ce1d-119">Wenn einer der Gleitkommatypen [double](double.md) ist, wertet der Ausdruck in relationalen Vergleichen oder in Vergleichen auf Gleichheit nach [double](double.md) oder [bool](bool.md) aus.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-119">If one of the floating-point types is [double](double.md), the expression evaluates to [double](double.md), or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

- <span data-ttu-id="2ce1d-120">Wenn kein [double](double.md)-Typ in dem Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-120">If there is no [double](double.md) type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="2ce1d-121">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="2ce1d-121">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="2ce1d-122">Positiv und negativ 0 (null)</span><span class="sxs-lookup"><span data-stu-id="2ce1d-122">Positive and negative zero</span></span>

- <span data-ttu-id="2ce1d-123">Positiv und negativ unendlich</span><span class="sxs-lookup"><span data-stu-id="2ce1d-123">Positive and negative infinity</span></span>

- <span data-ttu-id="2ce1d-124">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="2ce1d-124">Not-a-Number value (NaN)</span></span>

- <span data-ttu-id="2ce1d-125">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="2ce1d-125">The finite set of nonzero values</span></span>

<span data-ttu-id="2ce1d-126">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](http://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-126">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://www.ieee.org) website.</span></span>

## <a name="example"></a><span data-ttu-id="2ce1d-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ce1d-127">Example</span></span>

<span data-ttu-id="2ce1d-128">Im folgenden Beispiel werden ein [int](int.md)-, ein [short](short.md) und ein `float`-Datentyp in einem mathematischen Ausdruck verwendet, der ein `float`-Ergebnis aufweist.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-128">In the following example, an [int](int.md), a [short](short.md), and a `float` are included in a mathematical expression giving a `float` result.</span></span> <span data-ttu-id="2ce1d-129">(Beachten Sie, dass `float` ein Alias für den Typ <xref:System.Single?displayProperty=nameWithType> ist.) Beachten Sie auch, dass es in diesem Ausdruck keine [Double-Datentypen](double.md) gibt.</span><span class="sxs-lookup"><span data-stu-id="2ce1d-129">(Remember that `float` is an alias for the <xref:System.Single?displayProperty=nameWithType> type.) Notice that there is no [double](double.md) in the expression.</span></span>

[!code-csharp[csrefKeywordsTypes#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="2ce1d-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2ce1d-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2ce1d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ce1d-131">See also</span></span>

- <xref:System.Single>  
- [<span data-ttu-id="2ce1d-132">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2ce1d-132">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="2ce1d-133">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2ce1d-133">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="2ce1d-134">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-134">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)  
- [<span data-ttu-id="2ce1d-135">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2ce1d-135">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="2ce1d-136">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-136">Integral Types Table</span></span>](integral-types-table.md)  
- [<span data-ttu-id="2ce1d-137">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-137">Built-In Types Table</span></span>](built-in-types-table.md)  
- [<span data-ttu-id="2ce1d-138">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-138">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="2ce1d-139">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="2ce1d-139">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)  