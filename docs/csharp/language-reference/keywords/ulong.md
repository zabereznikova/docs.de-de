---
title: ulong (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c2da253e4da7a5d6cfa71116e4fcba7816441e92
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ulong-c-reference"></a><span data-ttu-id="d3c37-102">ulong (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d3c37-102">ulong (C# Reference)</span></span>

<span data-ttu-id="d3c37-103">Das Schlüsselwort `ulong` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d3c37-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="d3c37-104">Typ</span><span class="sxs-lookup"><span data-stu-id="d3c37-104">Type</span></span>|<span data-ttu-id="d3c37-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="d3c37-105">Range</span></span>|<span data-ttu-id="d3c37-106">Größe</span><span class="sxs-lookup"><span data-stu-id="d3c37-106">Size</span></span>|<span data-ttu-id="d3c37-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="d3c37-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="d3c37-108">0 bis 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="d3c37-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="d3c37-109">64-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d3c37-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="d3c37-110">Literale</span><span class="sxs-lookup"><span data-stu-id="d3c37-110">Literals</span></span>  

<span data-ttu-id="d3c37-111">Sie können eine `ulong`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d3c37-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="d3c37-112">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ulong` befindet (d.h., wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=fullName> oder größer als <xref:System.UInt64.MaxValue?displayProperty=fullName> ist), tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="d3c37-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=fullName> or greater than <xref:System.UInt64.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="d3c37-113">Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ulong`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d3c37-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
<span data-ttu-id="d3c37-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span><span class="sxs-lookup"><span data-stu-id="d3c37-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="d3c37-115">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="d3c37-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="d3c37-116">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="d3c37-116">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="d3c37-117">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d3c37-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="d3c37-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="d3c37-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="d3c37-119">Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d3c37-119">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="d3c37-120">Das Suffix `UL` oder `ul` identifiziert unzweideutig ein numerisches Literal als ein `ulong`-Wert.</span><span class="sxs-lookup"><span data-stu-id="d3c37-120">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="d3c37-121">Das `L`-Suffix kennzeichnet ein `ulong`, wenn der Literalwert <xref:System.Int64.MaxValue?displayProperty=fullName> überschreitet.</span><span class="sxs-lookup"><span data-stu-id="d3c37-121">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="d3c37-122">Das `U`- oder `u`-Suffix kennzeichnet ein `ulong`, wenn der Literalwert <xref:System.UInt32.MaxValue?displayProperty=fullName> überschreitet.</span><span class="sxs-lookup"><span data-stu-id="d3c37-122">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="d3c37-123">Im folgenden Beispiel wird das `ul`-Suffix verwendet, um eine lange ganze Zahl anzugeben:</span><span class="sxs-lookup"><span data-stu-id="d3c37-123">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
<span data-ttu-id="d3c37-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="d3c37-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span></span>

<span data-ttu-id="d3c37-125">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste der folgenden Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="d3c37-125">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="d3c37-126">int</span><span class="sxs-lookup"><span data-stu-id="d3c37-126">int</span></span>](int.md)
2. [<span data-ttu-id="d3c37-127">uint</span><span class="sxs-lookup"><span data-stu-id="d3c37-127">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="d3c37-128">long</span><span class="sxs-lookup"><span data-stu-id="d3c37-128">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="d3c37-129">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="d3c37-129">Compiler overload resolution</span></span>
  
 <span data-ttu-id="d3c37-130">Das Suffix wird häufig beim Aufrufen überladener Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3c37-130">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="d3c37-131">Dies ist z.B. in den folgenden überladenen Methoden der Fall, die die Parameter `ulong` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="d3c37-131">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="d3c37-132">Die Verwendung eines Suffixes mit dem Parameter `ulong` gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="d3c37-132">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="d3c37-133">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d3c37-133">Conversions</span></span>  
 <span data-ttu-id="d3c37-134">Es gibt eine vordefinierte implizite Konvertierung von `ulong` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="d3c37-134">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="d3c37-135">Es gibt keine implizite Konvertierung von `ulong` in ganzzahlige Typen.</span><span class="sxs-lookup"><span data-stu-id="d3c37-135">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="d3c37-136">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne explizite Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="d3c37-136">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="d3c37-137">Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `ulong`.</span><span class="sxs-lookup"><span data-stu-id="d3c37-137">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="d3c37-138">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `ulong` gibt.</span><span class="sxs-lookup"><span data-stu-id="d3c37-138">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="d3c37-139">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="d3c37-139">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="d3c37-140">Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="d3c37-140">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="d3c37-141">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="d3c37-141">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d3c37-142">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d3c37-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d3c37-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3c37-143">See Also</span></span>  
 <span data-ttu-id="d3c37-144"><xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="d3c37-144"><xref:System.UInt64></span></span>   
 <span data-ttu-id="d3c37-145">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d3c37-145">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d3c37-146">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d3c37-146">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d3c37-147">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d3c37-147">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d3c37-148">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="d3c37-148">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="d3c37-149">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="d3c37-149">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="d3c37-150">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="d3c37-150">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="d3c37-151">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d3c37-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

