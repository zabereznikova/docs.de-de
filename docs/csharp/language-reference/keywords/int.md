---
title: int (C#-Referenz)
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: c7d9bb0ee3d59ef3e0cf56d26e73a925fcfb4206
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275290"
---
# <a name="int-c-reference"></a><span data-ttu-id="b366a-102">int (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b366a-102">int (C# Reference)</span></span>

<span data-ttu-id="b366a-103">`int` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b366a-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="b366a-104">Typ</span><span class="sxs-lookup"><span data-stu-id="b366a-104">Type</span></span>|<span data-ttu-id="b366a-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="b366a-105">Range</span></span>|<span data-ttu-id="b366a-106">Größe</span><span class="sxs-lookup"><span data-stu-id="b366a-106">Size</span></span>|<span data-ttu-id="b366a-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="b366a-107">.NET Framework type</span></span>|<span data-ttu-id="b366a-108">Standardwert</span><span class="sxs-lookup"><span data-stu-id="b366a-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="b366a-109">-2,147,483,648 bis 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="b366a-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="b366a-110">Eine 32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b366a-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="b366a-111">0</span><span class="sxs-lookup"><span data-stu-id="b366a-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="b366a-112">Literale</span><span class="sxs-lookup"><span data-stu-id="b366a-112">Literals</span></span>  
 
<span data-ttu-id="b366a-113">Sie können eine `int`-Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal oder (ab C# 7.0) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b366a-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="b366a-114">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `int` befindet (sprich, wenn es kleiner als <xref:System.Int32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int32.MaxValue?displayProperty=nameWithType> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="b366a-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="b366a-115">Im folgenden Beispiel werden Ganzzahlen wie 90.946, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `int`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b366a-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]  

> [!NOTE] 
> <span data-ttu-id="b366a-116">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="b366a-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="b366a-117">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="b366a-117">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="b366a-118">Mit C# 7.0 wurde eine Reihe von Features zur Verbesserung der Lesbarkeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b366a-118">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="b366a-119">C# 7.0 lässt die Verwendung des Unterstrichs (`_`) als Zifferntrennzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="b366a-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="b366a-120">C# 7.2 lässt die Verwendung von `_` als Zifferntrennzeichen nach dem Präfix für ein binäres oder hexadezimales Literal zu.</span><span class="sxs-lookup"><span data-stu-id="b366a-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="b366a-121">Dezimalliterale dürfen keinen vorangestellten Unterstrich aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b366a-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="b366a-122">Im Folgenden werden einige Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b366a-122">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]  
 
 <span data-ttu-id="b366a-123">Ganzzahlliterale können auch ein Suffix enthalten, dass den Typen kennzeichnet, auch wenn es kein Suffix gibt, dass den `int`-Typ kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b366a-123">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="b366a-124">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="b366a-124">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="b366a-125">uint</span><span class="sxs-lookup"><span data-stu-id="b366a-125">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="b366a-126">long</span><span class="sxs-lookup"><span data-stu-id="b366a-126">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="b366a-127">ulong</span><span class="sxs-lookup"><span data-stu-id="b366a-127">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="b366a-128">In diesen Beispielen ist das Literal 90946 vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="b366a-128">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="b366a-129">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b366a-129">Conversions</span></span>  
 <span data-ttu-id="b366a-130">Es gibt eine vordefinierte implizite Konvertierung von `int` in [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="b366a-130">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="b366a-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b366a-131">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="b366a-132">Es gibt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `int`.</span><span class="sxs-lookup"><span data-stu-id="b366a-132">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="b366a-133">Die folgende Anweisung erzeugt z. B. einen Kompilierungsfehler ohne Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="b366a-133">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="b366a-134">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `int` gibt.</span><span class="sxs-lookup"><span data-stu-id="b366a-134">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="b366a-135">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="b366a-135">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="b366a-136">Weitere Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="b366a-136">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b366a-137">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b366a-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b366a-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b366a-138">See Also</span></span>  
 <xref:System.Int32>  
 [<span data-ttu-id="b366a-139">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b366a-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b366a-140">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b366a-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b366a-141">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b366a-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b366a-142">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="b366a-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="b366a-143">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="b366a-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="b366a-144">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b366a-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="b366a-145">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b366a-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
