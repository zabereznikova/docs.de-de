---
title: uint (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: 4342c08ab536f45a2e3b5fa6fe94839436600a4a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="uint-c-reference"></a><span data-ttu-id="75526-102">uint (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="75526-102">uint (C# Reference)</span></span>

<span data-ttu-id="75526-103">Das Schlüsselwort `uint` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75526-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="75526-104">Typ</span><span class="sxs-lookup"><span data-stu-id="75526-104">Type</span></span>|<span data-ttu-id="75526-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="75526-105">Range</span></span>|<span data-ttu-id="75526-106">Größe</span><span class="sxs-lookup"><span data-stu-id="75526-106">Size</span></span>|<span data-ttu-id="75526-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="75526-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="75526-108">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="75526-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="75526-109">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="75526-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=fullName>|  
  
 <span data-ttu-id="75526-110">**Hinweis** Der Typ `uint` ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="75526-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="75526-111">Verwenden Sie nach Möglichkeit `int`.</span><span class="sxs-lookup"><span data-stu-id="75526-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="75526-112">Literale</span><span class="sxs-lookup"><span data-stu-id="75526-112">Literals</span></span>  

<span data-ttu-id="75526-113">Sie können eine `uint`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="75526-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="75526-114">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `uint` befindet (d.h., wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=fullName> oder größer als <xref:System.UInt32.MaxValue?displayProperty=fullName> ist), tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="75526-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=fullName> or greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="75526-115">Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `uint`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="75526-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
<span data-ttu-id="75526-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span><span class="sxs-lookup"><span data-stu-id="75526-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="75526-117">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="75526-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="75526-118">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="75526-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="75526-119">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="75526-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="75526-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span><span class="sxs-lookup"><span data-stu-id="75526-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span></span>  
 
 <span data-ttu-id="75526-121">Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="75526-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="75526-122">Das Suffix `U` oder „u“ gibt entweder ein `uint` oder `ulong` an, abhängig vom numerischen Wert des Literals.</span><span class="sxs-lookup"><span data-stu-id="75526-122">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="75526-123">Im folgenden Beispiel wird das `u`-Suffix verwendet, um eine ganze Zahl ohne Vorzeichen von beiden Typen zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="75526-123">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="75526-124">Beachten Sie, dass das erste Literal ein `uint` ist, weil sein Wert kleiner als <xref:System.UInt32.MaxValue?displayProperty=fullName> ist, während das zweite ein `ulong` ist, weil sein Wert größer als <xref:System.UInt32.MaxValue?displayProperty=fullName> ist.</span><span class="sxs-lookup"><span data-stu-id="75526-124">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=fullName>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span>

<span data-ttu-id="75526-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="75526-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span></span>  
 
<span data-ttu-id="75526-126">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste der folgenden Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="75526-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="75526-127">int</span><span class="sxs-lookup"><span data-stu-id="75526-127">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="75526-128">long</span><span class="sxs-lookup"><span data-stu-id="75526-128">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="75526-129">ulong</span><span class="sxs-lookup"><span data-stu-id="75526-129">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="75526-130">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="75526-130">Conversions</span></span>  
 <span data-ttu-id="75526-131">Es gibt eine vordefinierte implizite Konvertierung von `uint` in [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="75526-131">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="75526-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="75526-132">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="75526-133">Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `uint`.</span><span class="sxs-lookup"><span data-stu-id="75526-133">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="75526-134">Andernfalls müssen Sie eine Umwandlung verwenden.</span><span class="sxs-lookup"><span data-stu-id="75526-134">Otherwise you must use a cast.</span></span> <span data-ttu-id="75526-135">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="75526-135">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="75526-136">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `uint` gibt.</span><span class="sxs-lookup"><span data-stu-id="75526-136">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="75526-137">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="75526-137">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="75526-138">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="75526-138">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="75526-139">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="75526-139">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="75526-140">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="75526-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75526-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75526-141">See Also</span></span>  
 <span data-ttu-id="75526-142"><xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="75526-142"><xref:System.UInt32></span></span>   
 <span data-ttu-id="75526-143">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="75526-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="75526-144">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="75526-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="75526-145">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="75526-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="75526-146">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="75526-146">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="75526-147">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="75526-147">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="75526-148">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="75526-148">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="75526-149">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="75526-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

