---
title: int (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
dev_langs:
- CSharp
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
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
ms.sourcegitcommit: 935428cc9442a3e1d15eeb8942176c237bff4e22
ms.openlocfilehash: 6e87893bcd9800b61297e71b782028fec5116479
ms.contentlocale: de-de
ms.lasthandoff: 08/22/2017

---
# <a name="int-c-reference"></a><span data-ttu-id="ec287-102">int (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ec287-102">int (C# Reference)</span></span>

<span data-ttu-id="ec287-103">`int` kennzeichnet einen ganzzahligen Typ, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ec287-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="ec287-104">Typ</span><span class="sxs-lookup"><span data-stu-id="ec287-104">Type</span></span>|<span data-ttu-id="ec287-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="ec287-105">Range</span></span>|<span data-ttu-id="ec287-106">Größe</span><span class="sxs-lookup"><span data-stu-id="ec287-106">Size</span></span>|<span data-ttu-id="ec287-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="ec287-107">.NET Framework type</span></span>|<span data-ttu-id="ec287-108">Standardwert</span><span class="sxs-lookup"><span data-stu-id="ec287-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="ec287-109">-2,147,483,648 bis 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="ec287-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="ec287-110">Eine 32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ec287-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=fullName>|<span data-ttu-id="ec287-111">0</span><span class="sxs-lookup"><span data-stu-id="ec287-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="ec287-112">Literale</span><span class="sxs-lookup"><span data-stu-id="ec287-112">Literals</span></span>  
 
<span data-ttu-id="ec287-113">Sie können eine `int`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec287-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="ec287-114">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `int` befindet (sprich, wenn es kleiner als <xref:System.Int32.MinValue?displayProperty=fullName> oder größer als <xref:System.Int32.MaxValue?displayProperty=fullName> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="ec287-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=fullName> or greater than <xref:System.Int32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="ec287-115">Im folgenden Beispiel werden Ganzzahlen wie 90.946, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `int`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ec287-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
<span data-ttu-id="ec287-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span><span class="sxs-lookup"><span data-stu-id="ec287-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="ec287-117">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="ec287-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="ec287-118">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="ec287-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="ec287-119">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ec287-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="ec287-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span><span class="sxs-lookup"><span data-stu-id="ec287-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span></span>  
 
 <span data-ttu-id="ec287-121">Ganzzahlliterale können auch ein Suffix enthalten, dass den Typen kennzeichnet, auch wenn es kein Suffix gibt, dass den `int`-Typ kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ec287-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="ec287-122">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="ec287-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="ec287-123">uint</span><span class="sxs-lookup"><span data-stu-id="ec287-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="ec287-124">long</span><span class="sxs-lookup"><span data-stu-id="ec287-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="ec287-125">ulong</span><span class="sxs-lookup"><span data-stu-id="ec287-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="ec287-126">In diesen Beispielen ist das Literal 90946 vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="ec287-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="ec287-127">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ec287-127">Conversions</span></span>  
 <span data-ttu-id="ec287-128">Es gibt eine vordefinierte implizite Konvertierung von `int` in [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="ec287-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="ec287-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ec287-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="ec287-130">Es gibt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `int`.</span><span class="sxs-lookup"><span data-stu-id="ec287-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="ec287-131">Die folgende Anweisung erzeugt z. B. einen Kompilierungsfehler ohne Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="ec287-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="ec287-132">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `int` gibt.</span><span class="sxs-lookup"><span data-stu-id="ec287-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="ec287-133">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="ec287-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="ec287-134">Weitere Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="ec287-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ec287-135">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ec287-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec287-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec287-136">See Also</span></span>  
 <span data-ttu-id="ec287-137"><xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="ec287-137"><xref:System.Int32></span></span>   
 <span data-ttu-id="ec287-138">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec287-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ec287-139">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec287-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ec287-140">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec287-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ec287-141">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="ec287-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="ec287-142">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="ec287-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="ec287-143">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="ec287-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="ec287-144">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ec287-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

