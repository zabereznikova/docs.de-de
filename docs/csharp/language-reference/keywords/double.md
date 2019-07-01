---
title: double-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: f4d6bb4eb698e4afbda6571ba382e828a5f836a4
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424260"
---
# <a name="double-c-reference"></a><span data-ttu-id="86d5a-102">double (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="86d5a-102">double (C# Reference)</span></span>

<span data-ttu-id="86d5a-103">Das `double`-Schlüsselwort kennzeichnet einen einfachen Typ, der 64-Bit-Gleitkommawerte speichert.</span><span class="sxs-lookup"><span data-stu-id="86d5a-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="86d5a-104">Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `double`-Typ an.</span><span class="sxs-lookup"><span data-stu-id="86d5a-104">The following table shows the precision and approximate range for the `double` type.</span></span>

|<span data-ttu-id="86d5a-105">Typ</span><span class="sxs-lookup"><span data-stu-id="86d5a-105">Type</span></span>|<span data-ttu-id="86d5a-106">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="86d5a-106">Approximate range</span></span>|<span data-ttu-id="86d5a-107">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="86d5a-107">Precision</span></span>|<span data-ttu-id="86d5a-108">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="86d5a-108">.NET type</span></span>|
|----------|-----------------------|---------------|-------------------------|
|`double`|<span data-ttu-id="86d5a-109">±5,0 × 10<sup>−324</sup> bis ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="86d5a-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="86d5a-110">~15–17 Stellen</span><span class="sxs-lookup"><span data-stu-id="86d5a-110">~15-17 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="86d5a-111">Literale</span><span class="sxs-lookup"><span data-stu-id="86d5a-111">Literals</span></span>

<span data-ttu-id="86d5a-112">Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt.</span><span class="sxs-lookup"><span data-stu-id="86d5a-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="86d5a-113">Aber wenn Sie eine ganze Zahl als `double` behandeln möchten, verwenden Sie das Suffix d oder D, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="86d5a-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>

```csharp
double x = 3D;
```

## <a name="conversions"></a><span data-ttu-id="86d5a-114">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="86d5a-114">Conversions</span></span>

<span data-ttu-id="86d5a-115">Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="86d5a-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="86d5a-116">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="86d5a-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="86d5a-117">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="86d5a-117">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="86d5a-118">Wenn einer der Gleitkommatypen `double` ist, wertet der Ausdruck in relationalen Vergleichen und in Vergleichen auf Gleichheit nach `double` oder [bool](../../../csharp/language-reference/keywords/bool.md) aus.</span><span class="sxs-lookup"><span data-stu-id="86d5a-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

- <span data-ttu-id="86d5a-119">Wenn in dem Ausdruck kein `double`-Typ vorhanden ist, wird der Ausdruck in relationalen Vergleichen und Vergleichen auf Gleichheit in [float](../../../csharp/language-reference/keywords/float.md) oder [bool](../../../csharp/language-reference/keywords/bool.md) ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="86d5a-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or to [bool](../../../csharp/language-reference/keywords/bool.md) in relational comparisons and comparisons for equality.</span></span>

 <span data-ttu-id="86d5a-120">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="86d5a-120">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="86d5a-121">Positive und negative null</span><span class="sxs-lookup"><span data-stu-id="86d5a-121">Positive and negative zero.</span></span>

- <span data-ttu-id="86d5a-122">Positive und negative Infinity</span><span class="sxs-lookup"><span data-stu-id="86d5a-122">Positive and negative infinity.</span></span>

- <span data-ttu-id="86d5a-123">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="86d5a-123">Not-a-Number value (NaN).</span></span>

- <span data-ttu-id="86d5a-124">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="86d5a-124">The finite set of nonzero values.</span></span>

<span data-ttu-id="86d5a-125">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](https://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="86d5a-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) Web site.</span></span>

## <a name="example"></a><span data-ttu-id="86d5a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86d5a-126">Example</span></span>

<span data-ttu-id="86d5a-127">Im folgenden Beispiel werden ein [int](../builtin-types/integral-numeric-types.md), ein [short](../../../csharp/language-reference/builtin-types/integral-numeric-types.md),ein [float](../../../csharp/language-reference/keywords/float.md) und ein `double` zusammen addiert, was ein `double`-Ergebnis ergibt.</span><span class="sxs-lookup"><span data-stu-id="86d5a-127">In the following example, an [int](../builtin-types/integral-numeric-types.md), a [short](../../../csharp/language-reference/builtin-types/integral-numeric-types.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>

[!code-csharp[csrefKeywordsTypes#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="86d5a-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="86d5a-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="86d5a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86d5a-129">See also</span></span>

- [<span data-ttu-id="86d5a-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="86d5a-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="86d5a-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="86d5a-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="86d5a-132">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="86d5a-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="86d5a-133">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="86d5a-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)
- [<span data-ttu-id="86d5a-134">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="86d5a-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="86d5a-135">Tabelle für Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="86d5a-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)
- [<span data-ttu-id="86d5a-136">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="86d5a-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="86d5a-137">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="86d5a-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
