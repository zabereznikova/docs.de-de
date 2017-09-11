---
title: long (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
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
ms.openlocfilehash: 5f7d2d6a3d5781b4e120b8399c7206d4429dd98e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="long-c-reference"></a><span data-ttu-id="b9e9b-102">long (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b9e9b-102">long (C# Reference)</span></span>

<span data-ttu-id="b9e9b-103">`long` kennzeichnet einen Ganzzahltyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="b9e9b-104">Typ</span><span class="sxs-lookup"><span data-stu-id="b9e9b-104">Type</span></span>|<span data-ttu-id="b9e9b-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="b9e9b-105">Range</span></span>|<span data-ttu-id="b9e9b-106">Größe</span><span class="sxs-lookup"><span data-stu-id="b9e9b-106">Size</span></span>|<span data-ttu-id="b9e9b-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="b9e9b-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="b9e9b-108">-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="b9e9b-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="b9e9b-109">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b9e9b-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="b9e9b-110">Literale</span><span class="sxs-lookup"><span data-stu-id="b9e9b-110">Literals</span></span> 

<span data-ttu-id="b9e9b-111">Sie können eine `long`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="b9e9b-112">Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `long`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
<span data-ttu-id="b9e9b-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span><span class="sxs-lookup"><span data-stu-id="b9e9b-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="b9e9b-114">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="b9e9b-115">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="b9e9b-116">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="b9e9b-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="b9e9b-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="b9e9b-118">Ganzzahlliterale können auch ein Suffix enthalten, das den Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-118">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="b9e9b-119">Das Suffix `L` kennzeichnet ein `long`.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-119">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="b9e9b-120">Im folgenden Beispiel wird das `L`-Suffix verwendet, um eine lange ganze Zahl anzugeben:</span><span class="sxs-lookup"><span data-stu-id="b9e9b-120">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="b9e9b-121">Sie können auch Kleinbuchstabe „l“ als Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-121">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="b9e9b-122">Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-122">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="b9e9b-123">Verwenden Sie aus Gründen der Klarheit „L“.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-123">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="b9e9b-124">Wenn Sie das Suffix `L` verwenden, wird der Typ des Ganzzahlliterals entweder als `long` oder [ulong](../../../csharp/language-reference/keywords/ulong.md) bestimmt, abhängig von seiner Größe.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-124">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="b9e9b-125">In diesem Fall ist er `long`, weil er kleiner als der Bereich von [ulong](../../../csharp/language-reference/keywords/ulong.md) ist.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-125">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="b9e9b-126">Das Suffix wird häufig zum Aufrufen überladener Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-126">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="b9e9b-127">Die folgenden überladenen Methoden z.B. verfügen über Parameter des Typs `long` und [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="b9e9b-127">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="b9e9b-128">Das `L`-Suffix gewährleistet, dass die richtige Überladung aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="b9e9b-128">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="b9e9b-129">Wenn ein Ganzzahlliteral kein Suffix besitzt, ist sein Typ der erste der folgenden Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="b9e9b-129">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="b9e9b-130">int</span><span class="sxs-lookup"><span data-stu-id="b9e9b-130">int</span></span>](int.md)
2. [<span data-ttu-id="b9e9b-131">uint</span><span class="sxs-lookup"><span data-stu-id="b9e9b-131">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="b9e9b-132">ulong</span><span class="sxs-lookup"><span data-stu-id="b9e9b-132">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="b9e9b-133">Das Literal 4294967296 im vorhergehenden Beispiel ist vom Typ `long`, da er den Bereich von [uint](../../../csharp/language-reference/keywords/uint.md) überschreitet (Speichergrößen von ganzzahligen Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)).</span><span class="sxs-lookup"><span data-stu-id="b9e9b-133">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="b9e9b-134">Wenn Sie den `long`-Typ mit anderen ganzzahligen Typen im selben Ausdruck verwenden, wird der Ausdruck als `long` ausgewertet (oder [bool](../../../csharp/language-reference/keywords/bool.md) im Fall von relationalen oder booleschen Ausdrücken).</span><span class="sxs-lookup"><span data-stu-id="b9e9b-134">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="b9e9b-135">Der folgende Ausdruck wird z.B. als `long` ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="b9e9b-135">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="b9e9b-136">Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="b9e9b-136">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="b9e9b-137">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b9e9b-137">Conversions</span></span>  
 <span data-ttu-id="b9e9b-138">Es gibt eine vordefinierte implizite Konvertierung von `long` in [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="b9e9b-138">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="b9e9b-139">Ansonsten muss eine Umwandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-139">Otherwise a cast must be used.</span></span> <span data-ttu-id="b9e9b-140">Die folgende Anweisung erzeugt z.B. einen Kompilierungsfehler ohne explizite Umwandlung:</span><span class="sxs-lookup"><span data-stu-id="b9e9b-140">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="b9e9b-141">Es gibt eine vordefinierte implizite Konvertierung von [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `long`.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-141">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="b9e9b-142">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen in `long` gibt.</span><span class="sxs-lookup"><span data-stu-id="b9e9b-142">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="b9e9b-143">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="b9e9b-143">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="b9e9b-144">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b9e9b-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b9e9b-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9e9b-145">See Also</span></span>  
 <span data-ttu-id="b9e9b-146"><xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="b9e9b-146"><xref:System.Int64></span></span>   
 <span data-ttu-id="b9e9b-147">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b9e9b-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b9e9b-148">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b9e9b-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b9e9b-149">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b9e9b-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b9e9b-150">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b9e9b-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="b9e9b-151">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b9e9b-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="b9e9b-152">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="b9e9b-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="b9e9b-153">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b9e9b-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

