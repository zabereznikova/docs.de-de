---
title: byte – C#-Referenz
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: fe2ef272c77b1af3a5b5a7f5bf3efb4836edcf23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691527"
---
# <a name="byte-c-reference"></a><span data-ttu-id="d1afa-102">byte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d1afa-102">byte (C# Reference)</span></span>

<span data-ttu-id="d1afa-103">`byte` kennzeichnet einen ganzzahligen Typ, der Werte anhand der folgenden Tabelle speichert.</span><span class="sxs-lookup"><span data-stu-id="d1afa-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="d1afa-104">Typ</span><span class="sxs-lookup"><span data-stu-id="d1afa-104">Type</span></span>|<span data-ttu-id="d1afa-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="d1afa-105">Range</span></span>|<span data-ttu-id="d1afa-106">Größe</span><span class="sxs-lookup"><span data-stu-id="d1afa-106">Size</span></span>|<span data-ttu-id="d1afa-107">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="d1afa-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="d1afa-108">0 bis 255</span><span class="sxs-lookup"><span data-stu-id="d1afa-108">0 to 255</span></span>|<span data-ttu-id="d1afa-109">8-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d1afa-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="d1afa-110">Literale</span><span class="sxs-lookup"><span data-stu-id="d1afa-110">Literals</span></span>  

 <span data-ttu-id="d1afa-111">Sie können eine `byte`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d1afa-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="d1afa-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `byte` befindet (sprich, wenn es kleiner als <xref:System.Byte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Byte.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d1afa-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="d1afa-113">Im folgenden Beispiel werden ganze Zahlen, die gleich 201 sind und von dezimalen, hexadezimalen und binären Literalen dargestellt werden, implizit von [int](../../../csharp/language-reference/keywords/int.md)- in `byte`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d1afa-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="d1afa-114">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="d1afa-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="d1afa-115">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="d1afa-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d1afa-116">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d1afa-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="d1afa-117">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="d1afa-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="d1afa-118">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="d1afa-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="d1afa-119">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d1afa-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="d1afa-120">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d1afa-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="d1afa-121">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d1afa-121">Conversions</span></span>  
 <span data-ttu-id="d1afa-122">Es gibt eine vordefinierte implizite Konvertierung von `byte` in [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="d1afa-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="d1afa-123">Sie können nicht literale numerische Typen mit einer größeren Speichergröße nicht implizit zu `byte` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d1afa-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="d1afa-124">Weitere Informationen zu Speichergrößen ganzzahliger Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="d1afa-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="d1afa-125">Betrachten Sie z.B. die folgenden beiden `byte`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="d1afa-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="d1afa-126">Die folgende Zuweisungsanweisung erzeugt einen Compilerfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.</span><span class="sxs-lookup"><span data-stu-id="d1afa-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="d1afa-127">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="d1afa-127">To fix this problem, use a cast:</span></span>  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="d1afa-128">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="d1afa-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="d1afa-129">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkommadatentypen in `byte` gibt.</span><span class="sxs-lookup"><span data-stu-id="d1afa-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="d1afa-130">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="d1afa-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="d1afa-131">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d1afa-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="d1afa-132">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `byte` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="d1afa-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="d1afa-133">Die Verwendung der `byte`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="d1afa-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="d1afa-134">Weitere Informationen zu arithmetischen Ausdrücken mit gemischten Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="d1afa-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="d1afa-135">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="d1afa-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d1afa-136">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d1afa-136">C# Language Specification</span></span>  

<span data-ttu-id="d1afa-137">Weitere Informationen finden Sie unter [Intregrale Datentypen](~/_csharplang/spec/types.md#integral-types) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1afa-137">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="d1afa-138">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="d1afa-138">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1afa-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1afa-139">See also</span></span>

- <xref:System.Byte>
- [<span data-ttu-id="d1afa-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d1afa-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d1afa-141">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d1afa-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d1afa-142">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d1afa-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="d1afa-143">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="d1afa-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="d1afa-144">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="d1afa-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="d1afa-145">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d1afa-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="d1afa-146">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d1afa-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
