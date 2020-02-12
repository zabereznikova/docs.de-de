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
ms.openlocfilehash: 9c8b11f9337ee9de90f2d4d96b5be162713bfcbd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093213"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="1eb3e-103">Numerische Gleitkommatypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1eb3e-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="1eb3e-104">Die *numerischen Gleitkommatypen* stellen reelle Zahlen dar.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="1eb3e-105">Alle numerischen Gleitkommatypen sind [Werttypen](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="1eb3e-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="1eb3e-106">Sie sind auch [einfache Typen](value-types.md#built-in-value-types) und können mit [Literalen](#real-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="1eb3e-107">Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison](../operators/comparison-operators.md)- und [equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="1eb3e-108">Merkmale der Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="1eb3e-109">C# unterstützt die folgenden vordefinierten Gleitkommatypen:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="1eb3e-110">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="1eb3e-110">C# type/keyword</span></span>|<span data-ttu-id="1eb3e-111">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="1eb3e-111">Approximate range</span></span>|<span data-ttu-id="1eb3e-112">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="1eb3e-112">Precision</span></span>|<span data-ttu-id="1eb3e-113">Größe</span><span class="sxs-lookup"><span data-stu-id="1eb3e-113">Size</span></span>|<span data-ttu-id="1eb3e-114">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="1eb3e-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="1eb3e-115">±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="1eb3e-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="1eb3e-116">~6–9 Stellen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-116">~6-9 digits</span></span>|<span data-ttu-id="1eb3e-117">4 Bytes</span><span class="sxs-lookup"><span data-stu-id="1eb3e-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="1eb3e-118">±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="1eb3e-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="1eb3e-119">~15–17 Stellen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-119">~15-17 digits</span></span>|<span data-ttu-id="1eb3e-120">8 Bytes</span><span class="sxs-lookup"><span data-stu-id="1eb3e-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="1eb3e-121">±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="1eb3e-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="1eb3e-122">28-29 Stellen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-122">28-29 digits</span></span>|<span data-ttu-id="1eb3e-123">16 Bytes</span><span class="sxs-lookup"><span data-stu-id="1eb3e-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="1eb3e-124">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="1eb3e-125">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-125">They are interchangeable.</span></span> <span data-ttu-id="1eb3e-126">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="1eb3e-127">Der Standardwert jedes Gleitkommatyps ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="1eb3e-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="1eb3e-128">Die einzelnen Gleitkommatypen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Endwert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="1eb3e-129">Die Typen `float` und `double` verfügen auch über Konstanten, die nicht numerische Werte und Unendlichkeitswerte darstellen.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="1eb3e-130">Der Typ `double` verfügt beispielsweise über folgende Konstanten: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> und <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1eb3e-131">Da der Typ `decimal` über eine höhere Genauigkeit und einen kleineren Bereich verfügt als `float` und `double`, eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="1eb3e-132">Sie können [integrale](integral-numeric-types.md) Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-132">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="1eb3e-133">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-133">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="1eb3e-134">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-134">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="1eb3e-135">Wenn einer der Gleitkommatypen `double` ist, wird der Ausdruck in `double` oder in [bool](bool.md) in relationalen Vergleichen oder in Vergleichen auf Gleichheit ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-135">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="1eb3e-136">Wenn kein `double`-Typ im Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [bool](bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="1eb3e-137">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-137">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="1eb3e-138">Positiv und negativ 0 (null)</span><span class="sxs-lookup"><span data-stu-id="1eb3e-138">Positive and negative zero</span></span>
- <span data-ttu-id="1eb3e-139">Positiv und negativ unendlich</span><span class="sxs-lookup"><span data-stu-id="1eb3e-139">Positive and negative infinity</span></span>
- <span data-ttu-id="1eb3e-140">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="1eb3e-140">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="1eb3e-141">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="1eb3e-141">The finite set of nonzero values</span></span>

<span data-ttu-id="1eb3e-142">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-142">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="1eb3e-143">Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-143">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="1eb3e-144">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="1eb3e-144">Real literals</span></span>

<span data-ttu-id="1eb3e-145">Der Typ eines Real-Literals wird wie folgt durch sein Suffix bestimmt:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-145">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="1eb3e-146">Das Literal ohne Suffix oder mit dem Suffix `d` oder `D` ist vom Typ `double`.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-146">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="1eb3e-147">Das Literal mit dem Suffix `f` oder `F` ist vom Typ `float`.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-147">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="1eb3e-148">Das Literal mit dem Suffix `m` oder `M` ist vom Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-148">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="1eb3e-149">Der folgende Code zeigt ein Beispiel für jeden Typ:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-149">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="1eb3e-150">Das vorherige Beispiel zeigt auch die Verwendung von `_` als *Zifferntrennzeichen*, das ab C# 7.0 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-150">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="1eb3e-151">Sie können das Zifferntrennzeichen mit allen Arten numerischer Literale verwenden.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-151">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="1eb3e-152">Sie können auch die wissenschaftliche Notation verwenden, d.h. einen exponentiellen Teil eines Real-Literals angeben, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1eb3e-152">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="1eb3e-153">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-153">Conversions</span></span>

<span data-ttu-id="1eb3e-154">Es gibt nur eine implizite Konvertierung zwischen numerischen Gleitkommatypen: von `float` zu `double`.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-154">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="1eb3e-155">Allerdings können Sie einen Gleitkommatyp mit der [expliziten Umwandlung](../operators/type-testing-and-cast.md#cast-operator-)in beliebige andere Gleitkommatypen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1eb3e-155">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="1eb3e-156">Weitere Informationen finden Sie unter [Integrierte numerische Konvertierungen (C#-Referenz)](numeric-conversions.md) (Integrierte numerische Konvertierungen).</span><span class="sxs-lookup"><span data-stu-id="1eb3e-156">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1eb3e-157">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1eb3e-157">C# language specification</span></span>

<span data-ttu-id="1eb3e-158">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="1eb3e-158">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1eb3e-159">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-159">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="1eb3e-160">Der Dezimaltyp</span><span class="sxs-lookup"><span data-stu-id="1eb3e-160">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="1eb3e-161">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="1eb3e-161">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="1eb3e-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb3e-162">See also</span></span>

- [<span data-ttu-id="1eb3e-163">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1eb3e-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1eb3e-164">Werttypen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-164">Value types</span></span>](value-types.md)
- [<span data-ttu-id="1eb3e-165">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-165">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="1eb3e-166">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1eb3e-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="1eb3e-167">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="1eb3e-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
