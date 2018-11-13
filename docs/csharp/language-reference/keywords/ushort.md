---
title: ushort (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: fa7f80f8f0fd6efa92242949ef16963213d0a28e
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "50744482"
---
# <a name="ushort-c-reference"></a><span data-ttu-id="89c52-102">ushort (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="89c52-102">ushort (C# Reference)</span></span>

<span data-ttu-id="89c52-103">Das Schlüsselwort `ushort` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="89c52-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="89c52-104">Typ</span><span class="sxs-lookup"><span data-stu-id="89c52-104">Type</span></span>|<span data-ttu-id="89c52-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="89c52-105">Range</span></span>|<span data-ttu-id="89c52-106">Größe</span><span class="sxs-lookup"><span data-stu-id="89c52-106">Size</span></span>|<span data-ttu-id="89c52-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="89c52-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="89c52-108">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="89c52-108">0 to 65,535</span></span>|<span data-ttu-id="89c52-109">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="89c52-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="89c52-110">Literale</span><span class="sxs-lookup"><span data-stu-id="89c52-110">Literals</span></span>  

<span data-ttu-id="89c52-111">Sie können eine `ushort`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="89c52-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="89c52-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `ushort` befindet (sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="89c52-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="89c52-113">Im folgenden Beispiel werden Ganzzahlen wie 65.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](../../../csharp/language-reference/keywords/int.md) in `ushort`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="89c52-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> <span data-ttu-id="89c52-114">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="89c52-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="89c52-115">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="89c52-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="89c52-116">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="89c52-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="89c52-117">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="89c52-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="89c52-118">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="89c52-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="89c52-119">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="89c52-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="89c52-120">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="89c52-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="89c52-121">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="89c52-121">Compiler overload resolution</span></span>
  
 <span data-ttu-id="89c52-122">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="89c52-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="89c52-123">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `ushort` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="89c52-123">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="89c52-124">Die Verwendung der `ushort`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="89c52-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="89c52-125">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="89c52-125">Conversions</span></span>  
 <span data-ttu-id="89c52-126">Es gibt eine vordefinierte implizite Konvertierung von `ushort` in [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="89c52-126">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="89c52-127">Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="89c52-127">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="89c52-128">Andernfalls muss eine Umwandlung verwendet werden, um eine explizite Konvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="89c52-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="89c52-129">Betrachten Sie z.B. die folgenden beiden `ushort`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="89c52-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="89c52-130">Die folgende Zuweisungsanweisung erzeugt einen Kompilierfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.</span><span class="sxs-lookup"><span data-stu-id="89c52-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="89c52-131">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="89c52-131">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="89c52-132">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="89c52-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="89c52-133">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `ushort` gibt.</span><span class="sxs-lookup"><span data-stu-id="89c52-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="89c52-134">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="89c52-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="89c52-135">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="89c52-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="89c52-136">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="89c52-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="89c52-137">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="89c52-137">C# Language Specification</span></span>  

<span data-ttu-id="89c52-138">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="89c52-138">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="89c52-139">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="89c52-139">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="89c52-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89c52-140">See Also</span></span>

- <xref:System.UInt16>  
- [<span data-ttu-id="89c52-141">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="89c52-141">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="89c52-142">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="89c52-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="89c52-143">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="89c52-143">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="89c52-144">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="89c52-144">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="89c52-145">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="89c52-145">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="89c52-146">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="89c52-146">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="89c52-147">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="89c52-147">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
