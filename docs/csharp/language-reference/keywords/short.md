---
title: short – C#-Referenz
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: 0b02e72e0588f1c1a0343a391430b5878b96b5f5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633989"
---
# <a name="short-c-reference"></a><span data-ttu-id="20a5c-102">short (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="20a5c-102">short (C# Reference)</span></span>

<span data-ttu-id="20a5c-103">`short` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="20a5c-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="20a5c-104">Typ</span><span class="sxs-lookup"><span data-stu-id="20a5c-104">Type</span></span>|<span data-ttu-id="20a5c-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="20a5c-105">Range</span></span>|<span data-ttu-id="20a5c-106">Größe</span><span class="sxs-lookup"><span data-stu-id="20a5c-106">Size</span></span>|<span data-ttu-id="20a5c-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="20a5c-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`short`|<span data-ttu-id="20a5c-108">–32.768 bis 32.767</span><span class="sxs-lookup"><span data-stu-id="20a5c-108">-32,768 to 32,767</span></span>|<span data-ttu-id="20a5c-109">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="20a5c-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="20a5c-110">Literale</span><span class="sxs-lookup"><span data-stu-id="20a5c-110">Literals</span></span>

<span data-ttu-id="20a5c-111">Sie können eine `short`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="20a5c-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="20a5c-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `short` befindet (sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="20a5c-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="20a5c-113">Im folgenden Beispiel werden Ganzzahlen wie 1.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](int.md) in `short`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="20a5c-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](int.md) to `short` values.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]

> [!NOTE]
> <span data-ttu-id="20a5c-114">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="20a5c-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="20a5c-115">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="20a5c-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="20a5c-116">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20a5c-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>

- <span data-ttu-id="20a5c-117">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="20a5c-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="20a5c-118">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="20a5c-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="20a5c-119">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="20a5c-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="20a5c-120">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="20a5c-120">Some examples are shown below.</span></span>

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]

## <a name="compiler-overload-resolution"></a><span data-ttu-id="20a5c-121">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="20a5c-121">Compiler overload resolution</span></span>

<span data-ttu-id="20a5c-122">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="20a5c-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="20a5c-123">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `short` und [int](int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="20a5c-123">Consider, for example, the following overloaded methods that use `short` and [int](int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(short s) {}
```

<span data-ttu-id="20a5c-124">Die Verwendung der `short`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="20a5c-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>

```csharp
SampleMethod(5);         // Calling the method with the int parameter
SampleMethod((short)5);  // Calling the method with the short parameter
```

## <a name="conversions"></a><span data-ttu-id="20a5c-125">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="20a5c-125">Conversions</span></span>

<span data-ttu-id="20a5c-126">Es gibt eine vordefinierte implizite Konvertierung von `short` in [int](int.md), [long](long.md), [float](float.md), [double](double.md) oder [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="20a5c-126">There is a predefined implicit conversion from `short` to [int](int.md), [long](long.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span>

<span data-ttu-id="20a5c-127">Sie können numerische nonliteral-Typen einer größeren Speichergröße nicht implizit in `short` konvertieren (siehe [Tabelle ganzzahliger Typen](integral-types-table.md) für die Speichergrößen ganzzahliger Typen).</span><span class="sxs-lookup"><span data-stu-id="20a5c-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="20a5c-128">Betrachten Sie z.B. die folgenden beiden `short`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="20a5c-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>

```csharp
short x = 5, y = 12;
```

<span data-ttu-id="20a5c-129">Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig [int](int.md) ergibt.</span><span class="sxs-lookup"><span data-stu-id="20a5c-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](int.md) by default.</span></span>

```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

<span data-ttu-id="20a5c-130">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="20a5c-130">To fix this problem, use a cast:</span></span>

```csharp
short z  = (short)(x + y);   // Explicit conversion
```

<span data-ttu-id="20a5c-131">Es ist jedoch auch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="20a5c-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
int m = x + y;
long n = x + y;
```

<span data-ttu-id="20a5c-132">Es gibt keine implizite Konvertierung von Gleitkommadatentypen zu `short`.</span><span class="sxs-lookup"><span data-stu-id="20a5c-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="20a5c-133">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="20a5c-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
short x = 3.0;          // Error: no implicit conversion from double
short y = (short)3.0;   // OK: explicit conversion
```

<span data-ttu-id="20a5c-134">Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](float.md) und [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="20a5c-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="20a5c-135">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="20a5c-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="20a5c-136">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="20a5c-136">C# language specification</span></span>

<span data-ttu-id="20a5c-137">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="20a5c-137">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="20a5c-138">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="20a5c-138">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="20a5c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20a5c-139">See also</span></span>

- <xref:System.Int16>
- [<span data-ttu-id="20a5c-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="20a5c-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="20a5c-141">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="20a5c-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="20a5c-142">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="20a5c-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="20a5c-143">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="20a5c-143">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="20a5c-144">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="20a5c-144">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="20a5c-145">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="20a5c-145">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="20a5c-146">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="20a5c-146">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
