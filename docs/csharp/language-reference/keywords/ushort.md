---
title: ushort (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
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
ms.openlocfilehash: 2b067a2ffd0fbffe06dc5c9f2a9910c9563eec4b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="ushort-c-reference"></a><span data-ttu-id="b8a5d-102">ushort (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b8a5d-102">ushort (C# Reference)</span></span>

<span data-ttu-id="b8a5d-103">Das Schlüsselwort `ushort` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="b8a5d-104">Typ</span><span class="sxs-lookup"><span data-stu-id="b8a5d-104">Type</span></span>|<span data-ttu-id="b8a5d-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="b8a5d-105">Range</span></span>|<span data-ttu-id="b8a5d-106">Größe</span><span class="sxs-lookup"><span data-stu-id="b8a5d-106">Size</span></span>|<span data-ttu-id="b8a5d-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="b8a5d-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="b8a5d-108">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="b8a5d-108">0 to 65,535</span></span>|<span data-ttu-id="b8a5d-109">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b8a5d-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="b8a5d-110">Literale</span><span class="sxs-lookup"><span data-stu-id="b8a5d-110">Literals</span></span>  

<span data-ttu-id="b8a5d-111">Sie können eine `ushort`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="b8a5d-112">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ushort` befindet (das bedeutet wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=fullName> oder größer als <xref:System.UInt16.MaxValue?displayProperty=fullName> ist), tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=fullName> or greater than <xref:System.UInt16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="b8a5d-113">Im folgenden Beispiel werden Ganzzahlen wie 65.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](../../../csharp/language-reference/keywords/int.md) in `ushort`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
<span data-ttu-id="b8a5d-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span><span class="sxs-lookup"><span data-stu-id="b8a5d-114">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="b8a5d-115">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="b8a5d-116">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b8a5d-117">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="b8a5d-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span><span class="sxs-lookup"><span data-stu-id="b8a5d-118">[!code-cs[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="b8a5d-119">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="b8a5d-119">Compiler overload resolution</span></span>
  
 <span data-ttu-id="b8a5d-120">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-120">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="b8a5d-121">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `ushort` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="b8a5d-121">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="b8a5d-122">Die Verwendung der `ushort`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="b8a5d-122">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="b8a5d-123">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b8a5d-123">Conversions</span></span>  
 <span data-ttu-id="b8a5d-124">Es gibt eine vordefinierte implizite Konvertierung von `ushort` in [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="b8a5d-124">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="b8a5d-125">Es gibt eine vordefinierte implizite Konvertierung von [byte](../../../csharp/language-reference/keywords/byte.md) oder [char](../../../csharp/language-reference/keywords/char.md) in `ushort`.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-125">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="b8a5d-126">Andernfalls muss eine Umwandlung verwendet werden, um eine explizite Konvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-126">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="b8a5d-127">Betrachten Sie z.B. die folgenden beiden `ushort`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="b8a5d-127">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="b8a5d-128">Die folgende Zuweisungsanweisung erzeugt einen Kompilierfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-128">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="b8a5d-129">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="b8a5d-129">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="b8a5d-130">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="b8a5d-130">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="b8a5d-131">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkomma-Datentypen zu `ushort` gibt.</span><span class="sxs-lookup"><span data-stu-id="b8a5d-131">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="b8a5d-132">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="b8a5d-132">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="b8a5d-133">Informationen zu arithmetischen Ausdrücken mit ganzzahligen und Gleitkommatypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="b8a5d-133">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="b8a5d-134">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="b8a5d-134">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b8a5d-135">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b8a5d-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a5d-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8a5d-136">See Also</span></span>  
 <span data-ttu-id="b8a5d-137"><xref:System.UInt16></span><span class="sxs-lookup"><span data-stu-id="b8a5d-137"><xref:System.UInt16></span></span>   
 <span data-ttu-id="b8a5d-138">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8a5d-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b8a5d-139">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8a5d-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b8a5d-140">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8a5d-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b8a5d-141">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b8a5d-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="b8a5d-142">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="b8a5d-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="b8a5d-143">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="b8a5d-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="b8a5d-144">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="b8a5d-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

