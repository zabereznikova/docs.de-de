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
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 17ae154780679dd1f42f43f1ec345cdc722815d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002194"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="df9ff-103">Numerische Gleitkommatypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="df9ff-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="df9ff-104">Die **Gleitkommatypen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#floating-point-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="df9ff-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="df9ff-105">Alle Gleitkommatypen sind auch Werttypen.</span><span class="sxs-lookup"><span data-stu-id="df9ff-105">All floating-point types are also value types.</span></span> <span data-ttu-id="df9ff-106">Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison- und equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="df9ff-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="df9ff-107">Merkmale der Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="df9ff-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="df9ff-108">C# unterstützt die folgenden vordefinierten Gleitkommatypen:</span><span class="sxs-lookup"><span data-stu-id="df9ff-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="df9ff-109">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="df9ff-109">C# type/keyword</span></span>|<span data-ttu-id="df9ff-110">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="df9ff-110">Approximate range</span></span>|<span data-ttu-id="df9ff-111">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="df9ff-111">Precision</span></span>|<span data-ttu-id="df9ff-112">Größe</span><span class="sxs-lookup"><span data-stu-id="df9ff-112">Size</span></span>|<span data-ttu-id="df9ff-113">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="df9ff-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="df9ff-114">±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="df9ff-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="df9ff-115">~6–9 Stellen</span><span class="sxs-lookup"><span data-stu-id="df9ff-115">~6-9 digits</span></span>|<span data-ttu-id="df9ff-116">4 Bytes</span><span class="sxs-lookup"><span data-stu-id="df9ff-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="df9ff-117">±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="df9ff-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="df9ff-118">~15–17 Stellen</span><span class="sxs-lookup"><span data-stu-id="df9ff-118">~15-17 digits</span></span>|<span data-ttu-id="df9ff-119">8 Bytes</span><span class="sxs-lookup"><span data-stu-id="df9ff-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="df9ff-120">±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="df9ff-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="df9ff-121">28-29 Stellen</span><span class="sxs-lookup"><span data-stu-id="df9ff-121">28-29 digits</span></span>|<span data-ttu-id="df9ff-122">16 Bytes</span><span class="sxs-lookup"><span data-stu-id="df9ff-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="df9ff-123">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="df9ff-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="df9ff-124">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df9ff-124">They are interchangeable.</span></span> <span data-ttu-id="df9ff-125">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="df9ff-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="df9ff-126">Der Standardwert jedes Gleitkommatyps ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="df9ff-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="df9ff-127">Die einzelnen Gleitkommatypen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Endwert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="df9ff-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="df9ff-128">Die Typen `float` und `double` verfügen auch über Konstanten, die nicht numerische Werte und Unendlichkeitswerte darstellen.</span><span class="sxs-lookup"><span data-stu-id="df9ff-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="df9ff-129">Der Typ `double` verfügt beispielsweise über folgende Konstanten: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> und <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df9ff-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="df9ff-130">Da der Typ `decimal` über eine höhere Genauigkeit und einen kleineren Bereich verfügt als `float` und `double`, eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="df9ff-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="df9ff-131">Sie können [integrale](integral-numeric-types.md) Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="df9ff-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="df9ff-132">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="df9ff-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="df9ff-133">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="df9ff-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="df9ff-134">Wenn einer der Gleitkommatypen `double` ist, wertet der Ausdruck in relationalen Vergleichen oder in Vergleichen auf Gleichheit nach `double` oder [bool](../keywords/bool.md) aus.</span><span class="sxs-lookup"><span data-stu-id="df9ff-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="df9ff-135">Wenn kein `double`-Typ in dem Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](../keywords/bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="df9ff-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="df9ff-136">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="df9ff-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="df9ff-137">Positiv und negativ 0 (null)</span><span class="sxs-lookup"><span data-stu-id="df9ff-137">Positive and negative zero</span></span>
- <span data-ttu-id="df9ff-138">Positiv und negativ unendlich</span><span class="sxs-lookup"><span data-stu-id="df9ff-138">Positive and negative infinity</span></span>
- <span data-ttu-id="df9ff-139">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="df9ff-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="df9ff-140">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="df9ff-140">The finite set of nonzero values</span></span>

<span data-ttu-id="df9ff-141">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="df9ff-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="df9ff-142">Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="df9ff-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="df9ff-143">Gleitkommaliterale</span><span class="sxs-lookup"><span data-stu-id="df9ff-143">Floating-point literals</span></span>

<span data-ttu-id="df9ff-144">Ein numerisches Gleitkommaliteral auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt.</span><span class="sxs-lookup"><span data-stu-id="df9ff-144">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="df9ff-145">Sie können Suffixe verwenden, um ein Gleitkommaliteral oder ein integrales Literal in einen bestimmten Typ zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="df9ff-145">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="df9ff-146">Mit dem `d`- oder `D`-Suffix wird ein Literal in ein `double` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="df9ff-146">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="df9ff-147">Mit dem `f`- oder `F`-Suffix wird ein Literal in ein `float` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="df9ff-147">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="df9ff-148">Mit dem `m`- oder `M`-Suffix wird ein Literal in ein `decimal` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="df9ff-148">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="df9ff-149">In den folgenden Beispielen werden die einzelnen Suffixe dargestellt:</span><span class="sxs-lookup"><span data-stu-id="df9ff-149">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="df9ff-150">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="df9ff-150">Conversions</span></span>

<span data-ttu-id="df9ff-151">Es gibt eine implizite Konvertierung (als *erweiternde Konvertierung* bezeichnet) von `float` nach `double`, da der Bereich der `float`-Werte eine korrekte Teilmenge von `double` ist. Es entsteht kein Präzisionsverlust von `float` nach `double`.</span><span class="sxs-lookup"><span data-stu-id="df9ff-151">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="df9ff-152">Sie müssen eine explizite Umwandlung verwenden, um einen Gleitkommatyp in einen anderen Gleitkommatyp zu konvertieren, wenn keine implizite Konvertierung vom Quelltyp in den Zieltyp definiert ist.</span><span class="sxs-lookup"><span data-stu-id="df9ff-152">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="df9ff-153">Dies wird als *einschränkende Konvertierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="df9ff-153">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="df9ff-154">Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.</span><span class="sxs-lookup"><span data-stu-id="df9ff-154">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="df9ff-155">Es gibt keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ, da der `decimal`-Typ eine höhere Genauigkeit als `float` oder `double` aufweist.</span><span class="sxs-lookup"><span data-stu-id="df9ff-155">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="df9ff-156">Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="df9ff-156">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="df9ff-157">Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="df9ff-157">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df9ff-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df9ff-158">See also</span></span>

- [<span data-ttu-id="df9ff-159">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="df9ff-159">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="df9ff-160">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="df9ff-160">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="df9ff-161">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="df9ff-161">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="df9ff-162">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="df9ff-162">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="df9ff-163">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="df9ff-163">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="df9ff-164">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="df9ff-164">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="df9ff-165">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="df9ff-165">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="df9ff-166">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="df9ff-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="df9ff-167">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="df9ff-167">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
