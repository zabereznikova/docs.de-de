---
title: sbyte (C#-Referenz)
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
helpviewer_keywords: sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 010ac98f523eca5929100f7c51b8b6ef5d11de30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-c-reference"></a><span data-ttu-id="c71c4-102">sbyte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c71c4-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="c71c4-103">`sbyte` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="c71c4-104">Typ</span><span class="sxs-lookup"><span data-stu-id="c71c4-104">Type</span></span>|<span data-ttu-id="c71c4-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="c71c4-105">Range</span></span>|<span data-ttu-id="c71c4-106">Größe</span><span class="sxs-lookup"><span data-stu-id="c71c4-106">Size</span></span>|<span data-ttu-id="c71c4-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="c71c4-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`sbyte`|<span data-ttu-id="c71c4-108">–128 bis 127</span><span class="sxs-lookup"><span data-stu-id="c71c4-108">-128 to 127</span></span>|<span data-ttu-id="c71c4-109">Ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="c71c4-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="c71c4-110">Literale</span><span class="sxs-lookup"><span data-stu-id="c71c4-110">Literals</span></span>  

<span data-ttu-id="c71c4-111">Sie können eine `sbyte`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c71c4-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="c71c4-112">Im folgenden Beispiel werden Ganzzahlen wie -102, die als dezimale, hexadezimale und binäre Literale dargestellt werden, aus [int](../../../csharp/language-reference/keywords/int.md) in `sbyte`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c71c4-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>    
  
[!code-csharp[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]  

> [!NOTE] 
> <span data-ttu-id="c71c4-113">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="c71c4-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c71c4-114">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="c71c4-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c71c4-115">Beginnend mit C#-7, eine Reihe von Features hinzugefügt wurden zur Verbesserung der Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="c71c4-115">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="c71c4-116">C#-7.0 ermöglicht die Verwendung des Zeichens Unterstrich `_`, als Trennzeichen für Ziffern.</span><span class="sxs-lookup"><span data-stu-id="c71c4-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="c71c4-117">7.2 c# ermöglicht `_` als Trennzeichen für ein Literal binäre oder hexadezimale Ziffer nach dem Präfix verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c71c4-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="c71c4-118">Ein decimal-Literal ist nicht berechtigt, auf einem führenden Unterstrich.</span><span class="sxs-lookup"><span data-stu-id="c71c4-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

 <span data-ttu-id="c71c4-119">Einige Beispiele werden unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c71c4-119">Some examples are shown below.</span></span>

[!code-csharp[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]  

<span data-ttu-id="c71c4-120">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `sbyte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="c71c4-120">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="c71c4-121">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span><span class="sxs-lookup"><span data-stu-id="c71c4-121">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="c71c4-122">Dies bedeutet, dass in diesem Beispiel die numerischen Literale `0x9A` und `0b10011010` als 32-Bit Ganzzahlen mit Vorzeichen mit einem Wert von 156 interpretiert werden, was <xref:System.SByte.MaxValue?displayProperty=nameWithType> übersteigt.</span><span class="sxs-lookup"><span data-stu-id="c71c4-122">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c71c4-123">Aus diesem Grund wird der Umwandlungsoperator benötigt, und die Zuordnung muss in einem [unchecked](unchecked.md) Kontext erfolgen.</span><span class="sxs-lookup"><span data-stu-id="c71c4-123">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span> 

## <a name="compiler-overload-resolution"></a><span data-ttu-id="c71c4-124">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="c71c4-124">Compiler overload resolution</span></span>

 <span data-ttu-id="c71c4-125">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c71c4-125">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="c71c4-126">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `sbyte` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="c71c4-126">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 <span data-ttu-id="c71c4-127">Die Verwendung der `sbyte`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="c71c4-127">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp 
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## <a name="conversions"></a><span data-ttu-id="c71c4-128">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="c71c4-128">Conversions</span></span>  
 <span data-ttu-id="c71c4-129">Es gibt eine vordefinierte implizite Konvertierung von `sbyte` in [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="c71c4-129">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="c71c4-130">Sie können numerische nonliteral-Typen einer größeren Speichergröße nicht implizit zu `sbyte` konvertieren (siehe [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) für die Speichergrößen ganzzahliger Typen).</span><span class="sxs-lookup"><span data-stu-id="c71c4-130">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="c71c4-131">Betrachten Sie z.B. die folgenden beiden `sbyte`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="c71c4-131">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>  
  
```csharp  
sbyte x = 10, y = 20;  
```  
  
 <span data-ttu-id="c71c4-132">Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig [int](../../../csharp/language-reference/keywords/int.md) ergibt.</span><span class="sxs-lookup"><span data-stu-id="c71c4-132">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 <span data-ttu-id="c71c4-133">Wandeln Sie den Ausdruck wie im folgenden Beispiel um, um das Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="c71c4-133">To fix this problem, cast the expression as in the following example:</span></span>  
  
```csharp  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 <span data-ttu-id="c71c4-134">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="c71c4-134">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="c71c4-135">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `sbyte` gibt.</span><span class="sxs-lookup"><span data-stu-id="c71c4-135">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="c71c4-136">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="c71c4-136">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 <span data-ttu-id="c71c4-137">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="c71c4-137">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="c71c4-138">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="c71c4-138">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c71c4-139">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c71c4-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c71c4-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c71c4-140">See Also</span></span>  
 <xref:System.SByte>  
 [<span data-ttu-id="c71c4-141">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c71c4-141">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c71c4-142">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c71c4-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c71c4-143">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c71c4-143">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c71c4-144">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="c71c4-144">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="c71c4-145">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="c71c4-145">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="c71c4-146">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="c71c4-146">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="c71c4-147">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="c71c4-147">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
