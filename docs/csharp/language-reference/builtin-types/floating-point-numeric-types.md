---
title: Numerische Gleitkommatypen – C#-Referenz
description: 'Informationen zu den integrierten C#-Gleitkommatypen: float, double und decimal'
ms.date: 02/10/2020
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
ms.openlocfilehash: 95b7f266654bbbcdcd0f81e3aa11cfc94af9f0e5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215240"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="983f9-103">Numerische Gleitkommatypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="983f9-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="983f9-104">Die *numerischen Gleitkommatypen* stellen reelle Zahlen dar.</span><span class="sxs-lookup"><span data-stu-id="983f9-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="983f9-105">Alle numerischen Gleitkommatypen sind [Werttypen](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="983f9-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="983f9-106">Sie sind auch [einfache Typen](value-types.md#built-in-value-types) und können mit [Literalen](#real-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="983f9-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="983f9-107">Alle numerischen Gleitkommatypen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [comparison](../operators/comparison-operators.md)- und [equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="983f9-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="983f9-108">Merkmale der Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="983f9-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="983f9-109">C# unterstützt die folgenden vordefinierten Gleitkommatypen:</span><span class="sxs-lookup"><span data-stu-id="983f9-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="983f9-110">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="983f9-110">C# type/keyword</span></span>|<span data-ttu-id="983f9-111">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="983f9-111">Approximate range</span></span>|<span data-ttu-id="983f9-112">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="983f9-112">Precision</span></span>|<span data-ttu-id="983f9-113">Größe</span><span class="sxs-lookup"><span data-stu-id="983f9-113">Size</span></span>|<span data-ttu-id="983f9-114">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="983f9-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="983f9-115">±1.5 × 10<sup>−45</sup> zu ±3.4 × 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="983f9-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="983f9-116">~6–9 Stellen</span><span class="sxs-lookup"><span data-stu-id="983f9-116">~6-9 digits</span></span>|<span data-ttu-id="983f9-117">4 Bytes</span><span class="sxs-lookup"><span data-stu-id="983f9-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="983f9-118">±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="983f9-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="983f9-119">~15–17 Stellen</span><span class="sxs-lookup"><span data-stu-id="983f9-119">~15-17 digits</span></span>|<span data-ttu-id="983f9-120">8 Bytes</span><span class="sxs-lookup"><span data-stu-id="983f9-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="983f9-121">±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="983f9-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="983f9-122">28-29 Stellen</span><span class="sxs-lookup"><span data-stu-id="983f9-122">28-29 digits</span></span>|<span data-ttu-id="983f9-123">16 Bytes</span><span class="sxs-lookup"><span data-stu-id="983f9-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="983f9-124">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="983f9-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="983f9-125">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="983f9-125">They are interchangeable.</span></span> <span data-ttu-id="983f9-126">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="983f9-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="983f9-127">Der Standardwert jedes Gleitkommatyps ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="983f9-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="983f9-128">Die einzelnen Gleitkommatypen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Endwert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="983f9-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="983f9-129">Die Typen `float` und `double` verfügen auch über Konstanten, die nicht numerische Werte und Unendlichkeitswerte darstellen.</span><span class="sxs-lookup"><span data-stu-id="983f9-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="983f9-130">Der Typ `double` verfügt beispielsweise über folgende Konstanten: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> und <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="983f9-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="983f9-131">Da der Typ `decimal` über eine höhere Genauigkeit und einen kleineren Bereich verfügt als `float` und `double`, eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="983f9-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="983f9-132">Sie können [integrale](integral-numeric-types.md) Typen sowie die Typen `float` und `double` in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="983f9-132">You can mix [integral](integral-numeric-types.md) types and the `float` and `double` types in an expression.</span></span> <span data-ttu-id="983f9-133">In diesem Fall werden integrale Typen implizit in einen der Gleitkommatypen konvertiert. Bei Bedarf wird der `float`-Typ implizit in `double` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="983f9-133">In this case, integral types are implicitly converted to one of the floating-point types and, if necessary, the `float` type is implicitly converted to `double`.</span></span> <span data-ttu-id="983f9-134">Der Ausdruck wird wie folgt ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="983f9-134">The expression is evaluated as follows:</span></span>

- <span data-ttu-id="983f9-135">Wenn der `double`-Typ im Ausdruck vorhanden ist, wird der Ausdruck in `double` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in [`bool`](bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="983f9-135">If there is `double` type in the expression, the expression evaluates to `double`, or to [`bool`](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="983f9-136">Wenn der `double`-Typ im Ausdruck vorhanden ist, wird der Ausdruck in `float` oder in relationalen Vergleichen oder Vergleichen auf Gleichheit in `bool` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="983f9-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="983f9-137">Sie können integrale Typen und den `decimal`-Typ auch in einem Ausdruck miteinander kombinieren.</span><span class="sxs-lookup"><span data-stu-id="983f9-137">You can also mix integral types and the `decimal` type in an expression.</span></span> <span data-ttu-id="983f9-138">In diesem Fall werden integrale Typen implizit in den `decimal`-Typ konvertiert, und der Ausdruck wird als `decimal` oder `bool` in relationalen Vergleichen und Gleichheitsvergleichen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="983f9-138">In this case, integral types are implicitly converted to the `decimal` type and the expression evaluates to `decimal`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="983f9-139">In einem Ausdruck können Sie den `decimal`-Typ nicht mit den Typen `float` und `double` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="983f9-139">You cannot mix the `decimal` type with the `float` and `double` types in an expression.</span></span> <span data-ttu-id="983f9-140">Wenn Sie aber einen arithmetischen Vorgang, einen Vergleich oder einen Gleichheitsvorgang durchführen möchten, müssen Sie, wie nachfolgend dargestellt, in diesem Fall die Operanden explizit aus dem oder in den `decimal`-Typ konvertieren</span><span class="sxs-lookup"><span data-stu-id="983f9-140">In this case, if you want to perform arithmetic, comparison, or equality operations, you must explicitly convert the operands either from or to the `decimal` type, as the following example shows:</span></span>

```csharp-interactive
double a = 1.0;
decimal b = 2.1m;
Console.WriteLine(a + (double)b);
Console.WriteLine((decimal)a + b);
```

<span data-ttu-id="983f9-141">Zum Formatieren eines Gleitkommawerts können Sie [standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md) oder [benutzerdefinierte Zahlenformatzeichenfolgen](../../../standard/base-types/custom-numeric-format-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="983f9-141">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="983f9-142">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="983f9-142">Real literals</span></span>

<span data-ttu-id="983f9-143">Der Typ eines Real-Literals wird wie folgt durch sein Suffix bestimmt:</span><span class="sxs-lookup"><span data-stu-id="983f9-143">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="983f9-144">Das Literal ohne Suffix oder mit dem Suffix `d` oder `D` ist vom Typ `double`.</span><span class="sxs-lookup"><span data-stu-id="983f9-144">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="983f9-145">Das Literal mit dem Suffix `f` oder `F` ist vom Typ `float`.</span><span class="sxs-lookup"><span data-stu-id="983f9-145">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="983f9-146">Das Literal mit dem Suffix `m` oder `M` ist vom Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="983f9-146">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="983f9-147">Der folgende Code zeigt ein Beispiel für jeden Typ:</span><span class="sxs-lookup"><span data-stu-id="983f9-147">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="983f9-148">Das vorherige Beispiel zeigt auch die Verwendung von `_` als *Zifferntrennzeichen*, das ab C# 7.0 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="983f9-148">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="983f9-149">Sie können das Zifferntrennzeichen mit allen Arten numerischer Literale verwenden.</span><span class="sxs-lookup"><span data-stu-id="983f9-149">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="983f9-150">Sie können auch die wissenschaftliche Notation verwenden, d.h. einen exponentiellen Teil eines Real-Literals angeben, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="983f9-150">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="983f9-151">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="983f9-151">Conversions</span></span>

<span data-ttu-id="983f9-152">Es gibt nur eine implizite Konvertierung zwischen numerischen Gleitkommatypen: von `float` zu `double`.</span><span class="sxs-lookup"><span data-stu-id="983f9-152">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="983f9-153">Allerdings können Sie einen Gleitkommatyp mit der [expliziten Umwandlung](../operators/type-testing-and-cast.md#cast-operator-)in beliebige andere Gleitkommatypen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="983f9-153">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="983f9-154">Weitere Informationen finden Sie unter [Integrierte numerische Konvertierungen (C#-Referenz)](numeric-conversions.md) (Integrierte numerische Konvertierungen).</span><span class="sxs-lookup"><span data-stu-id="983f9-154">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="983f9-155">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="983f9-155">C# language specification</span></span>

<span data-ttu-id="983f9-156">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="983f9-156">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="983f9-157">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="983f9-157">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="983f9-158">Der Dezimaltyp</span><span class="sxs-lookup"><span data-stu-id="983f9-158">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="983f9-159">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="983f9-159">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="983f9-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="983f9-160">See also</span></span>

- [<span data-ttu-id="983f9-161">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="983f9-161">C# reference</span></span>](../index.md)
- [<span data-ttu-id="983f9-162">Werttypen</span><span class="sxs-lookup"><span data-stu-id="983f9-162">Value types</span></span>](value-types.md)
- [<span data-ttu-id="983f9-163">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="983f9-163">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="983f9-164">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="983f9-164">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="983f9-165">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="983f9-165">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
