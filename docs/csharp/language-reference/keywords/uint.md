---
title: uint (C#-Referenz)
ms.date: 03/14/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d32f7146d1f9e13d8cf0f275f4fd78b693b09d31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="uint-c-reference"></a><span data-ttu-id="988a9-102">uint (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="988a9-102">uint (C# Reference)</span></span>

<span data-ttu-id="988a9-103">Das Schlüsselwort `uint` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="988a9-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="988a9-104">Typ</span><span class="sxs-lookup"><span data-stu-id="988a9-104">Type</span></span>|<span data-ttu-id="988a9-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="988a9-105">Range</span></span>|<span data-ttu-id="988a9-106">Größe</span><span class="sxs-lookup"><span data-stu-id="988a9-106">Size</span></span>|<span data-ttu-id="988a9-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="988a9-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="988a9-108">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="988a9-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="988a9-109">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="988a9-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
  
 <span data-ttu-id="988a9-110">**Hinweis** Der Typ `uint` ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="988a9-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="988a9-111">Verwenden Sie nach Möglichkeit `int`.</span><span class="sxs-lookup"><span data-stu-id="988a9-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="988a9-112">Literale</span><span class="sxs-lookup"><span data-stu-id="988a9-112">Literals</span></span>  

<span data-ttu-id="988a9-113">Sie können eine `uint`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="988a9-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="988a9-114">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `uint` befindet (sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="988a9-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="988a9-115">Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `uint`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="988a9-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]  

> [!NOTE] 
> <span data-ttu-id="988a9-116">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="988a9-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="988a9-117">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="988a9-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="988a9-118">Beginnend mit C#-7, eine Reihe von Features hinzugefügt wurden zur Verbesserung der Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="988a9-118">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="988a9-119">C#-7.0 ermöglicht die Verwendung des Zeichens Unterstrich `_`, als Trennzeichen für Ziffern.</span><span class="sxs-lookup"><span data-stu-id="988a9-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="988a9-120">7.2 c# ermöglicht `_` als Trennzeichen für ein Literal binäre oder hexadezimale Ziffer nach dem Präfix verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="988a9-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="988a9-121">Ein decimal-Literal ist nicht berechtigt, auf einem führenden Unterstrich.</span><span class="sxs-lookup"><span data-stu-id="988a9-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="988a9-122">Einige Beispiele werden unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="988a9-122">Some examples are shown below.</span></span>

[!code-csharp[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]  
 
 <span data-ttu-id="988a9-123">Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="988a9-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="988a9-124">Das Suffix `U` oder „u“ gibt entweder ein `uint` oder `ulong` an, abhängig vom numerischen Wert des Literals.</span><span class="sxs-lookup"><span data-stu-id="988a9-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="988a9-125">Im folgenden Beispiel wird das `u`-Suffix verwendet, um eine ganze Zahl ohne Vorzeichen von beiden Typen zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="988a9-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="988a9-126">Beachten Sie, dass das erste Literal ein `uint` ist, weil sein Wert kleiner als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist, während das zweite ein `ulong` ist, weil sein Wert größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="988a9-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]  
 
<span data-ttu-id="988a9-127">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="988a9-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="988a9-128">int</span><span class="sxs-lookup"><span data-stu-id="988a9-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="988a9-129">long</span><span class="sxs-lookup"><span data-stu-id="988a9-129">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="988a9-130">ulong</span><span class="sxs-lookup"><span data-stu-id="988a9-130">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="988a9-131">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="988a9-131">Conversions</span></span>  
 <span data-ttu-id="988a9-132">Es gibt eine vordefinierte implizite Konvertierung von `uint` in [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="988a9-132">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="988a9-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="988a9-133">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="988a9-134">Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `uint`.</span><span class="sxs-lookup"><span data-stu-id="988a9-134">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="988a9-135">Andernfalls müssen Sie eine Umwandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="988a9-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="988a9-136">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="988a9-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="988a9-137">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `uint` gibt.</span><span class="sxs-lookup"><span data-stu-id="988a9-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="988a9-138">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="988a9-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="988a9-139">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="988a9-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="988a9-140">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="988a9-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="988a9-141">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="988a9-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="988a9-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="988a9-142">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="988a9-143">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="988a9-143">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="988a9-144">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="988a9-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="988a9-145">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="988a9-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="988a9-146">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="988a9-146">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="988a9-147">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="988a9-147">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="988a9-148">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="988a9-148">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="988a9-149">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="988a9-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
