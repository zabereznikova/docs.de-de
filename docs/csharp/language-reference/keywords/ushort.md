---
title: ushort (C#-Referenz)
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords: ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 83fa657303e8392997b04b7d80cdbcdbf39de887
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ushort-c-reference"></a><span data-ttu-id="d2c87-102">ushort (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d2c87-102">ushort (C# Reference)</span></span>

<span data-ttu-id="d2c87-103">Das Schlüsselwort `ushort` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d2c87-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="d2c87-104">Typ</span><span class="sxs-lookup"><span data-stu-id="d2c87-104">Type</span></span>|<span data-ttu-id="d2c87-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="d2c87-105">Range</span></span>|<span data-ttu-id="d2c87-106">Größe</span><span class="sxs-lookup"><span data-stu-id="d2c87-106">Size</span></span>|<span data-ttu-id="d2c87-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="d2c87-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="d2c87-108">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="d2c87-108">0 to 65,535</span></span>|<span data-ttu-id="d2c87-109">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d2c87-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="d2c87-110">Literale</span><span class="sxs-lookup"><span data-stu-id="d2c87-110">Literals</span></span>  

<span data-ttu-id="d2c87-111">Sie können eine `ushort`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d2c87-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="d2c87-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `ushort` befindet (sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d2c87-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="d2c87-113">Im folgenden Beispiel werden Ganzzahlen wie 65.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](../../../csharp/language-reference/keywords/int.md) in `ushort`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d2c87-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> <span data-ttu-id="d2c87-114">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="d2c87-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="d2c87-115">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="d2c87-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d2c87-116">Beginnend mit C#-7, eine Reihe von Features hinzugefügt wurden zur Verbesserung der Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="d2c87-116">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="d2c87-117">C#-7.0 ermöglicht die Verwendung des Zeichens Unterstrich `_`, als Trennzeichen für Ziffern.</span><span class="sxs-lookup"><span data-stu-id="d2c87-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="d2c87-118">7.2 c# ermöglicht `_` als Trennzeichen für ein Literal binäre oder hexadezimale Ziffer nach dem Präfix verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2c87-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="d2c87-119">Ein decimal-Literal ist nicht berechtigt, auf einem führenden Unterstrich.</span><span class="sxs-lookup"><span data-stu-id="d2c87-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="d2c87-120">Einige Beispiele werden unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2c87-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="d2c87-121">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="d2c87-121">Compiler overload resolution</span></span>
  
 <span data-ttu-id="d2c87-122">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d2c87-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="d2c87-123">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `ushort` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="d2c87-123">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="d2c87-124">Die Verwendung der `ushort`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="d2c87-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="d2c87-125">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d2c87-125">Conversions</span></span>  
 <span data-ttu-id="d2c87-126">Es gibt eine vordefinierte implizite Konvertierung von `ushort` in [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="d2c87-126">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="d2c87-127">Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="d2c87-127">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="d2c87-128">Andernfalls muss eine Umwandlung verwendet werden, um eine explizite Konvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d2c87-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="d2c87-129">Betrachten Sie z.B. die folgenden beiden `ushort`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="d2c87-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="d2c87-130">Die folgende Zuweisungsanweisung erzeugt einen Kompilierfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.</span><span class="sxs-lookup"><span data-stu-id="d2c87-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="d2c87-131">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="d2c87-131">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="d2c87-132">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="d2c87-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="d2c87-133">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `ushort` gibt.</span><span class="sxs-lookup"><span data-stu-id="d2c87-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="d2c87-134">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="d2c87-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="d2c87-135">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="d2c87-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="d2c87-136">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="d2c87-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d2c87-137">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d2c87-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2c87-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2c87-138">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="d2c87-139">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d2c87-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d2c87-140">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d2c87-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d2c87-141">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d2c87-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d2c87-142">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="d2c87-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="d2c87-143">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="d2c87-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="d2c87-144">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d2c87-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="d2c87-145">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d2c87-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
