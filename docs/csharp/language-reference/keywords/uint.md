---
title: uint-Schlüsselwort (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 86cbb216bd960251ebd78916fae7865aa10aa5fc
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149691"
---
# <a name="uint-c-reference"></a><span data-ttu-id="52813-102">uint (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="52813-102">uint (C# Reference)</span></span>

<span data-ttu-id="52813-103">Das Schlüsselwort `uint` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="52813-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="52813-104">Typ</span><span class="sxs-lookup"><span data-stu-id="52813-104">Type</span></span>|<span data-ttu-id="52813-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="52813-105">Range</span></span>|<span data-ttu-id="52813-106">Größe</span><span class="sxs-lookup"><span data-stu-id="52813-106">Size</span></span>|<span data-ttu-id="52813-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="52813-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`uint`|<span data-ttu-id="52813-108">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="52813-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="52813-109">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="52813-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|

<span data-ttu-id="52813-110">**Hinweis** Der Typ `uint` ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="52813-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="52813-111">Verwenden Sie nach Möglichkeit `int`.</span><span class="sxs-lookup"><span data-stu-id="52813-111">Use `int` whenever possible.</span></span>

## <a name="literals"></a><span data-ttu-id="52813-112">Literale</span><span class="sxs-lookup"><span data-stu-id="52813-112">Literals</span></span>

<span data-ttu-id="52813-113">Sie können eine `uint`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="52813-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="52813-114">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `uint` befindet (sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="52813-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="52813-115">Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `uint`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="52813-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> <span data-ttu-id="52813-116">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="52813-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="52813-117">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="52813-117">Decimal literals have no prefix.</span></span>

<span data-ttu-id="52813-118">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="52813-118">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="52813-119">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="52813-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="52813-120">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="52813-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="52813-121">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="52813-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="52813-122">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="52813-122">Some examples are shown below.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

<span data-ttu-id="52813-123">Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="52813-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="52813-124">Das Suffix `U` oder „u“ gibt entweder ein `uint` oder `ulong` an, abhängig vom numerischen Wert des Literals.</span><span class="sxs-lookup"><span data-stu-id="52813-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="52813-125">Im folgenden Beispiel wird das `u`-Suffix verwendet, um eine ganze Zahl ohne Vorzeichen von beiden Typen zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="52813-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="52813-126">Beachten Sie, dass das erste Literal ein `uint` ist, weil sein Wert kleiner als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist, während das zweite ein `ulong` ist, weil sein Wert größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="52813-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

<span data-ttu-id="52813-127">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="52813-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="52813-128">int</span><span class="sxs-lookup"><span data-stu-id="52813-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="52813-129">long</span><span class="sxs-lookup"><span data-stu-id="52813-129">long</span></span>](long.md)
4. [<span data-ttu-id="52813-130">ulong</span><span class="sxs-lookup"><span data-stu-id="52813-130">ulong</span></span>](ulong.md)

## <a name="conversions"></a><span data-ttu-id="52813-131">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="52813-131">Conversions</span></span>

<span data-ttu-id="52813-132">Es gibt eine vordefinierte implizite Konvertierung von `uint` in [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) oder [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="52813-132">There is a predefined implicit conversion from `uint` to [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span> <span data-ttu-id="52813-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="52813-133">For example:</span></span>

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

<span data-ttu-id="52813-134">Es gibt eine vordefinierte implizite Konvertierung von [byte](byte.md), [ushort](ushort.md) oder [char](char.md) in `uint`.</span><span class="sxs-lookup"><span data-stu-id="52813-134">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), or [char](char.md) to `uint`.</span></span> <span data-ttu-id="52813-135">Andernfalls müssen Sie eine Umwandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="52813-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="52813-136">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="52813-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

<span data-ttu-id="52813-137">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `uint` gibt.</span><span class="sxs-lookup"><span data-stu-id="52813-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="52813-138">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="52813-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

<span data-ttu-id="52813-139">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](float.md) und [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="52813-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="52813-140">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="52813-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="52813-141">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="52813-141">C# language specification</span></span>

<span data-ttu-id="52813-142">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="52813-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="52813-143">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="52813-143">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="52813-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52813-144">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="52813-145">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="52813-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="52813-146">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="52813-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="52813-147">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="52813-147">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="52813-148">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="52813-148">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="52813-149">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="52813-149">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="52813-150">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="52813-150">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="52813-151">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="52813-151">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)