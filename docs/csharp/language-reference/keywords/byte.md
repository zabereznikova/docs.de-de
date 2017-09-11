---
title: byte (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8ef7494e2a8a1463d37cff77d1dacebec8182b66
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="byte-c-reference"></a><span data-ttu-id="3c0f9-102">byte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3c0f9-102">byte (C# Reference)</span></span>

<span data-ttu-id="3c0f9-103">`byte` kennzeichnet einen ganzzahligen Typ, der Werte anhand der folgenden Tabelle speichert.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="3c0f9-104">Typ</span><span class="sxs-lookup"><span data-stu-id="3c0f9-104">Type</span></span>|<span data-ttu-id="3c0f9-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="3c0f9-105">Range</span></span>|<span data-ttu-id="3c0f9-106">Größe</span><span class="sxs-lookup"><span data-stu-id="3c0f9-106">Size</span></span>|<span data-ttu-id="3c0f9-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="3c0f9-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="3c0f9-108">0 bis 255</span><span class="sxs-lookup"><span data-stu-id="3c0f9-108">0 to 255</span></span>|<span data-ttu-id="3c0f9-109">8-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="3c0f9-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="3c0f9-110">Literale</span><span class="sxs-lookup"><span data-stu-id="3c0f9-110">Literals</span></span>  

 <span data-ttu-id="3c0f9-111">Sie können eine `byte`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="3c0f9-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `byte` befindet (sprich, wenn es kleiner als <xref:System.Byte.MinValue?displayProperty=fullName> oder größer als <xref:System.Byte.MaxValue?displayProperty=fullName> ist) tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=fullName> or greater than <xref:System.Byte.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="3c0f9-113">Im folgenden Beispiel werden ganze Zahlen, die gleich 201 sind und von dezimalen, hexadezimalen und binären Literalen dargestellt werden, implizit von [int](../../../csharp/language-reference/keywords/int.md)- in `byte`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
<span data-ttu-id="3c0f9-114">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]</span><span class="sxs-lookup"><span data-stu-id="3c0f9-114">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="3c0f9-115">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="3c0f9-116">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="3c0f9-117">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="3c0f9-118">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]</span><span class="sxs-lookup"><span data-stu-id="3c0f9-118">[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]</span></span>  
 
## <a name="conversions"></a><span data-ttu-id="3c0f9-119">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="3c0f9-119">Conversions</span></span>  
 <span data-ttu-id="3c0f9-120">Es gibt eine vordefinierte implizite Konvertierung von `byte` in [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f9-120">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="3c0f9-121">Sie können nicht literale numerische Typen mit einer größeren Speichergröße nicht implizit zu `byte` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-121">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="3c0f9-122">Weitere Informationen zu Speichergrößen ganzzahliger Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f9-122">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="3c0f9-123">Betrachten Sie z.B. die folgenden beiden `byte`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="3c0f9-123">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="3c0f9-124">Die folgende Zuweisungsanweisung erzeugt einen Compilerfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig `int` ergibt.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-124">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="3c0f9-125">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="3c0f9-125">To fix this problem, use a cast:</span></span>  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="3c0f9-126">Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="3c0f9-126">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="3c0f9-127">Beachten Sie auch, dass es keine implizite Konvertierung von Gleitkommadatentypen in `byte` gibt.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-127">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="3c0f9-128">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="3c0f9-128">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="3c0f9-129">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3c0f9-129">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="3c0f9-130">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `byte` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c0f9-130">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="3c0f9-131">Die Verwendung der `byte`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="3c0f9-131">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="3c0f9-132">Weitere Informationen zu arithmetischen Ausdrücken mit gemischten Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f9-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="3c0f9-133">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f9-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3c0f9-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="3c0f9-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3c0f9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c0f9-135">See Also</span></span>  
 <span data-ttu-id="3c0f9-136"><xref:System.Byte></span><span class="sxs-lookup"><span data-stu-id="3c0f9-136"><xref:System.Byte></span></span>   
 <span data-ttu-id="3c0f9-137">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c0f9-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3c0f9-138">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c0f9-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3c0f9-139">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c0f9-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3c0f9-140">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3c0f9-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="3c0f9-141">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3c0f9-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="3c0f9-142">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="3c0f9-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="3c0f9-143">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="3c0f9-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

