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
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="0f37d-103">Numerische Gleitkommatypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0f37d-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="0f37d-104">Die **Gleitkommatypen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#real-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0f37d-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="0f37d-105">Alle Gleitkommatypen sind auch Werttypen.</span><span class="sxs-lookup"><span data-stu-id="0f37d-105">All floating-point types are also value types.</span></span> <span data-ttu-id="0f37d-106">Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison](../operators/comparison-operators.md)- und [equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="0f37d-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="0f37d-107">Merkmale der Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="0f37d-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="0f37d-108">C# unterstützt die folgenden vordefinierten Gleitkommatypen:</span><span class="sxs-lookup"><span data-stu-id="0f37d-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="0f37d-109">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="0f37d-109">C# type/keyword</span></span>|<span data-ttu-id="0f37d-110">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="0f37d-110">Approximate range</span></span>|<span data-ttu-id="0f37d-111">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="0f37d-111">Precision</span></span>|<span data-ttu-id="0f37d-112">Größe</span><span class="sxs-lookup"><span data-stu-id="0f37d-112">Size</span></span>|<span data-ttu-id="0f37d-113">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="0f37d-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="0f37d-114">±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="0f37d-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="0f37d-115">~6–9 Stellen</span><span class="sxs-lookup"><span data-stu-id="0f37d-115">~6-9 digits</span></span>|<span data-ttu-id="0f37d-116">4 Bytes</span><span class="sxs-lookup"><span data-stu-id="0f37d-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="0f37d-117">±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="0f37d-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="0f37d-118">~15–17 Stellen</span><span class="sxs-lookup"><span data-stu-id="0f37d-118">~15-17 digits</span></span>|<span data-ttu-id="0f37d-119">8 Bytes</span><span class="sxs-lookup"><span data-stu-id="0f37d-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="0f37d-120">±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="0f37d-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="0f37d-121">28-29 Stellen</span><span class="sxs-lookup"><span data-stu-id="0f37d-121">28-29 digits</span></span>|<span data-ttu-id="0f37d-122">16 Bytes</span><span class="sxs-lookup"><span data-stu-id="0f37d-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="0f37d-123">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="0f37d-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="0f37d-124">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f37d-124">They are interchangeable.</span></span> <span data-ttu-id="0f37d-125">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="0f37d-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="0f37d-126">Der Standardwert jedes Gleitkommatyps ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="0f37d-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="0f37d-127">Die einzelnen Gleitkommatypen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Endwert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="0f37d-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="0f37d-128">Die Typen `float` und `double` verfügen auch über Konstanten, die nicht numerische Werte und Unendlichkeitswerte darstellen.</span><span class="sxs-lookup"><span data-stu-id="0f37d-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="0f37d-129">Der Typ `double` verfügt beispielsweise über folgende Konstanten: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> und <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f37d-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0f37d-130">Da der Typ `decimal` über eine höhere Genauigkeit und einen kleineren Bereich verfügt als `float` und `double`, eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="0f37d-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="0f37d-131">Sie können [integrale](integral-numeric-types.md) Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="0f37d-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="0f37d-132">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0f37d-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="0f37d-133">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="0f37d-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="0f37d-134">Wenn einer der Gleitkommatypen `double` ist, wird der Ausdruck in `double` oder in [bool](../keywords/bool.md) in relationalen Vergleichen oder in Vergleichen auf Gleichheit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0f37d-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="0f37d-135">Wenn kein `double`-Typ im Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](../keywords/bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="0f37d-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="0f37d-136">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="0f37d-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="0f37d-137">Positiv und negativ 0 (null)</span><span class="sxs-lookup"><span data-stu-id="0f37d-137">Positive and negative zero</span></span>
- <span data-ttu-id="0f37d-138">Positiv und negativ unendlich</span><span class="sxs-lookup"><span data-stu-id="0f37d-138">Positive and negative infinity</span></span>
- <span data-ttu-id="0f37d-139">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="0f37d-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="0f37d-140">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="0f37d-140">The finite set of nonzero values</span></span>

<span data-ttu-id="0f37d-141">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="0f37d-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="0f37d-142">Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f37d-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="0f37d-143">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="0f37d-143">Real literals</span></span>

<span data-ttu-id="0f37d-144">Der Typ eines Real-Literals wird wie folgt durch sein Suffix bestimmt:</span><span class="sxs-lookup"><span data-stu-id="0f37d-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="0f37d-145">Das Literal ohne Suffix oder mit dem Suffix `d` oder `D` ist vom Typ `double`.</span><span class="sxs-lookup"><span data-stu-id="0f37d-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="0f37d-146">Das Literal mit dem Suffix `f` oder `F` ist vom Typ `float`.</span><span class="sxs-lookup"><span data-stu-id="0f37d-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="0f37d-147">Das Literal mit dem Suffix `m` oder `M` ist vom Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="0f37d-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="0f37d-148">Der folgende Code zeigt ein Beispiel für jeden Typ:</span><span class="sxs-lookup"><span data-stu-id="0f37d-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="0f37d-149">Das vorherige Beispiel zeigt auch die Verwendung von `_` als *Zifferntrennzeichen*, das ab C# 7.0 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0f37d-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="0f37d-150">Sie können das Zifferntrennzeichen mit allen Arten numerischer Literale verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f37d-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="0f37d-151">Sie können auch die wissenschaftliche Notation verwenden, d.h. einen exponentiellen Teil eines Real-Literals angeben, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="0f37d-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="0f37d-152">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0f37d-152">Conversions</span></span>

<span data-ttu-id="0f37d-153">Es gibt eine implizite Konvertierung (als *erweiternde Konvertierung* bezeichnet) von `float` nach `double`, da der Bereich der `float`-Werte eine korrekte Teilmenge von `double` ist. Es entsteht kein Präzisionsverlust von `float` nach `double`.</span><span class="sxs-lookup"><span data-stu-id="0f37d-153">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="0f37d-154">Sie müssen eine explizite Umwandlung verwenden, um einen Gleitkommatyp in einen anderen Gleitkommatyp zu konvertieren, wenn keine implizite Konvertierung vom Quelltyp in den Zieltyp definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0f37d-154">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="0f37d-155">Dies wird als *einschränkende Konvertierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0f37d-155">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="0f37d-156">Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.</span><span class="sxs-lookup"><span data-stu-id="0f37d-156">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="0f37d-157">Es gibt keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ, da der `decimal`-Typ eine höhere Genauigkeit als `float` oder `double` aufweist.</span><span class="sxs-lookup"><span data-stu-id="0f37d-157">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="0f37d-158">Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="0f37d-158">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="0f37d-159">Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="0f37d-159">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0f37d-160">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="0f37d-160">C# language specification</span></span>

<span data-ttu-id="0f37d-161">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0f37d-161">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0f37d-162">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="0f37d-162">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="0f37d-163">Der Dezimaltyp</span><span class="sxs-lookup"><span data-stu-id="0f37d-163">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="0f37d-164">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="0f37d-164">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="0f37d-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f37d-165">See also</span></span>

- [<span data-ttu-id="0f37d-166">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0f37d-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0f37d-167">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="0f37d-167">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="0f37d-168">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="0f37d-168">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="0f37d-169">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="0f37d-169">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="0f37d-170">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="0f37d-170">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="0f37d-171">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="0f37d-171">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="0f37d-172">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="0f37d-172">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
