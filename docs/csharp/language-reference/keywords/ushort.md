---
title: ushort-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 934e25576a8a24c176a54ec6af984459b513fe5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614457"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="29437-102">ushort (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="29437-102">ushort (C# Reference)</span></span>

<span data-ttu-id="29437-103">Das Schlüsselwort `ushort` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="29437-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="29437-104">Typ</span><span class="sxs-lookup"><span data-stu-id="29437-104">Type</span></span>|<span data-ttu-id="29437-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="29437-105">Range</span></span>|<span data-ttu-id="29437-106">Größe</span><span class="sxs-lookup"><span data-stu-id="29437-106">Size</span></span>|<span data-ttu-id="29437-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="29437-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`ushort`|<span data-ttu-id="29437-108">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="29437-108">0 to 65,535</span></span>|<span data-ttu-id="29437-109">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="29437-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="29437-110">Literale</span><span class="sxs-lookup"><span data-stu-id="29437-110">Literals</span></span>

<span data-ttu-id="29437-111">Sie können eine `ushort`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="29437-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="29437-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `ushort` befindet (sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="29437-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="29437-113">Im folgenden Beispiel werden Ganzzahlen wie 65.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](int.md) in `ushort`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="29437-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `ushort` values.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]

> [!NOTE]
> <span data-ttu-id="29437-114">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="29437-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="29437-115">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="29437-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="29437-116">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="29437-116">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="29437-117">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="29437-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="29437-118">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="29437-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="29437-119">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="29437-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="29437-120">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="29437-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="29437-121">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="29437-121">Compiler overload resolution</span></span>

<span data-ttu-id="29437-122">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="29437-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="29437-123">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `ushort` und [int](int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="29437-123">Consider, for example, the following overloaded methods that use `ushort` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ushort s) {}
```

<span data-ttu-id="29437-124">Die Verwendung der `ushort`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="29437-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>

```csharp
// Calls the method with the int parameter:
SampleMethod(5);
// Calls the method with the ushort parameter:
SampleMethod((ushort)5);
```

## <a name="conversions"></a><span data-ttu-id="29437-125">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="29437-125">Conversions</span></span>

<span data-ttu-id="29437-126">Es gibt eine vordefinierte implizite Konvertierung von `ushort` in [int](int.md), [uint](uint.md) [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) oder [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="29437-126">There is a predefined implicit conversion from `ushort` to [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="29437-127">Es gibt eine vordefinierte implizite Konvertierung von [byte](byte.md) oder [char](char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="29437-127">There is a predefined implicit conversion from [byte](byte.md) or [char](char.md) to `ushort`.</span></span> <span data-ttu-id="29437-128">Andernfalls muss eine Umwandlung verwendet werden, um eine explizite Konvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="29437-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="29437-129">Betrachten Sie z.B. die folgenden beiden `ushort`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="29437-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>

```csharp
ushort x = 5, y = 12;
```

<span data-ttu-id="29437-130">Die folgende Zuweisungsanweisung erzeugt einen Kompilierfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.</span><span class="sxs-lookup"><span data-stu-id="29437-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>

```csharp
ushort z = x + y;   // Error: conversion from int to ushort
```

<span data-ttu-id="29437-131">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="29437-131">To fix this problem, use a cast:</span></span>

```csharp
ushort z = (ushort)(x + y);   // OK: explicit conversion
```

<span data-ttu-id="29437-132">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="29437-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="29437-133">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `ushort` gibt.</span><span class="sxs-lookup"><span data-stu-id="29437-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="29437-134">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="29437-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
ushort x = 3.0;
// OK -- explicit conversion:
ushort y = (ushort)3.0;
```

<span data-ttu-id="29437-135">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](float.md) und [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="29437-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="29437-136">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="29437-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="29437-137">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="29437-137">C# language specification</span></span>

<span data-ttu-id="29437-138">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="29437-138">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="29437-139">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="29437-139">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="29437-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29437-140">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="29437-141">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="29437-141">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="29437-142">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="29437-142">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="29437-143">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29437-143">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="29437-144">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="29437-144">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="29437-145">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="29437-145">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="29437-146">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="29437-146">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="29437-147">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="29437-147">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
