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
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="549a7-103">Numerische Gleitkommatypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="549a7-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="549a7-104">Die **Gleitkommatypen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#floating-point-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="549a7-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="549a7-105">Alle Gleitkommatypen sind auch Werttypen.</span><span class="sxs-lookup"><span data-stu-id="549a7-105">All floating-point types are also value types.</span></span> <span data-ttu-id="549a7-106">Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison- und equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="549a7-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md) [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

<span data-ttu-id="549a7-107">Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für die Gleitkommatypen:</span><span class="sxs-lookup"><span data-stu-id="549a7-107">The following table shows the precision and approximate ranges for the floating-point types:</span></span>
  
|<span data-ttu-id="549a7-108">Typ</span><span class="sxs-lookup"><span data-stu-id="549a7-108">Type</span></span>|<span data-ttu-id="549a7-109">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="549a7-109">Approximate range</span></span>|<span data-ttu-id="549a7-110">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="549a7-110">Precision</span></span>|  
|----------|-----------------------|---------------|  
|`float`|<span data-ttu-id="549a7-111">±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="549a7-111">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="549a7-112">~6–9 Stellen</span><span class="sxs-lookup"><span data-stu-id="549a7-112">~6-9 digits</span></span>|  
|`double`|<span data-ttu-id="549a7-113">±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="549a7-113">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="549a7-114">~15–17 Stellen</span><span class="sxs-lookup"><span data-stu-id="549a7-114">~15-17 digits</span></span>|  
|`decimal`|<span data-ttu-id="549a7-115">±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="549a7-115">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="549a7-116">28-29 Stellen</span><span class="sxs-lookup"><span data-stu-id="549a7-116">28-29 digits</span></span>|  

<span data-ttu-id="549a7-117">Der Standardwert für alle Gleitkommatypen lautet `0`.</span><span class="sxs-lookup"><span data-stu-id="549a7-117">The default value for all floating-point types is `0`.</span></span> <span data-ttu-id="549a7-118">Jeder der Gleitkommatypen hat Konstanten mit den Namen `MinValue` und `MaxValue` für den minimalen und maximalen Wert für diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="549a7-118">Each of the floating-point types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span> <span data-ttu-id="549a7-119">Die Typen `float` und `double` weisen zusätzliche Konstanten für `PositiveInfinity`, `NegativeInfinity` und `NaN` (für „Not a Number“ (keine Zahl)) auf.</span><span class="sxs-lookup"><span data-stu-id="549a7-119">The `float` and `double` types have additional constants for `PositiveInfinity`, `NegativeInfinity`, and `NaN` (for "Not a Number").</span></span> <span data-ttu-id="549a7-120">Der Typ `decimal` enthält Konstanten für `Zero`, `One` und `MinusOne`.</span><span class="sxs-lookup"><span data-stu-id="549a7-120">The `decimal` type includes constants for `Zero`, `One`, and `MinusOne`.</span></span>

<span data-ttu-id="549a7-121">Der `decimal`-Typ verfügt über höhere Genauigkeit und einen kleineren Wertebereich als `float` und `double`. Dadurch eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="549a7-121">The `decimal` type has more precision and a smaller range than both `float` and `double`, which makes it appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="549a7-122">Sie können ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="549a7-122">You can mix integral types and floating-point types in an expression.</span></span> <span data-ttu-id="549a7-123">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="549a7-123">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="549a7-124">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="549a7-124">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="549a7-125">Wenn einer der Gleitkommatypen `double` ist, wertet der Ausdruck in relationalen Vergleichen oder in Vergleichen auf Gleichheit nach `double` oder [bool](../keywords/bool.md) aus.</span><span class="sxs-lookup"><span data-stu-id="549a7-125">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="549a7-126">Wenn kein `double`-Typ in dem Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](../keywords/bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="549a7-126">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="549a7-127">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="549a7-127">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="549a7-128">Positiv und negativ 0 (null)</span><span class="sxs-lookup"><span data-stu-id="549a7-128">Positive and negative zero</span></span>
- <span data-ttu-id="549a7-129">Positiv und negativ unendlich</span><span class="sxs-lookup"><span data-stu-id="549a7-129">Positive and negative infinity</span></span>
- <span data-ttu-id="549a7-130">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="549a7-130">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="549a7-131">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="549a7-131">The finite set of nonzero values</span></span>

<span data-ttu-id="549a7-132">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="549a7-132">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="549a7-133">Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="549a7-133">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="549a7-134">Gleitkommaliterale</span><span class="sxs-lookup"><span data-stu-id="549a7-134">Floating-point literals</span></span>

<span data-ttu-id="549a7-135">Ein numerisches Gleitkommaliteral auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt.</span><span class="sxs-lookup"><span data-stu-id="549a7-135">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="549a7-136">Sie können Suffixe verwenden, um ein Gleitkommaliteral oder ein integrales Literal in einen bestimmten Typ zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="549a7-136">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="549a7-137">Mit dem `d`- oder `D`-Suffix wird ein Literal in ein `double` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="549a7-137">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="549a7-138">Mit dem `f`- oder `F`-Suffix wird ein Literal in ein `float` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="549a7-138">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="549a7-139">Mit dem `m`- oder `M`-Suffix wird ein Literal in ein `decimal` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="549a7-139">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="549a7-140">In den folgenden Beispielen werden die einzelnen Suffixe dargestellt:</span><span class="sxs-lookup"><span data-stu-id="549a7-140">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="549a7-141">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="549a7-141">Conversions</span></span>

<span data-ttu-id="549a7-142">Es gibt eine implizite Konvertierung (als *erweiternde Konvertierung* bezeichnet) von `float` nach `double`, da der Bereich der `float`-Werte eine korrekte Teilmenge von `double` ist. Es entsteht kein Präzisionsverlust von `float` nach `double`.</span><span class="sxs-lookup"><span data-stu-id="549a7-142">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span> 

<span data-ttu-id="549a7-143">Sie müssen eine explizite Umwandlung verwenden, um einen Gleitkommatyp in einen anderen Gleitkommatyp zu konvertieren, wenn keine implizite Konvertierung vom Quelltyp in den Zieltyp definiert ist.</span><span class="sxs-lookup"><span data-stu-id="549a7-143">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="549a7-144">Dies wird als *einschränkende Konvertierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="549a7-144">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="549a7-145">Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.</span><span class="sxs-lookup"><span data-stu-id="549a7-145">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="549a7-146">Es gibt keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ, da der `decimal`-Typ eine höhere Genauigkeit als `float` oder `double` aufweist.</span><span class="sxs-lookup"><span data-stu-id="549a7-146">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="549a7-147">Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="549a7-147">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="549a7-148">Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="549a7-148">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="549a7-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="549a7-149">See also</span></span>

- [<span data-ttu-id="549a7-150">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="549a7-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="549a7-151">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="549a7-151">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="549a7-152">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="549a7-152">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="549a7-153">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="549a7-153">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="549a7-154">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="549a7-154">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="549a7-155">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="549a7-155">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="549a7-156">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="549a7-156">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="549a7-157">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="549a7-157">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="549a7-158">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="549a7-158">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="549a7-159">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="549a7-159">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
