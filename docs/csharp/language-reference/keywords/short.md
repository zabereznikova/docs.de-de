---
title: short (C#-Referenz)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
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
ms.openlocfilehash: ab3ccfdeb8d8a67b5fcd60b1ad6eee4dcafc9691
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="short-c-reference"></a><span data-ttu-id="f9309-102">short (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f9309-102">short (C# Reference)</span></span>

<span data-ttu-id="f9309-103">`short` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f9309-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="f9309-104">Typ</span><span class="sxs-lookup"><span data-stu-id="f9309-104">Type</span></span>|<span data-ttu-id="f9309-105">Bereich</span><span class="sxs-lookup"><span data-stu-id="f9309-105">Range</span></span>|<span data-ttu-id="f9309-106">Größe</span><span class="sxs-lookup"><span data-stu-id="f9309-106">Size</span></span>|<span data-ttu-id="f9309-107">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="f9309-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="f9309-108">–32.768 bis 32.767</span><span class="sxs-lookup"><span data-stu-id="f9309-108">-32,768 to 32,767</span></span>|<span data-ttu-id="f9309-109">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f9309-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="f9309-110">Literale</span><span class="sxs-lookup"><span data-stu-id="f9309-110">Literals</span></span>  

<span data-ttu-id="f9309-111">Sie können eine `short`-Variable deklarieren und initialisieren, indem Sie ihr ein dezimales Literal, ein hexadezimales Literal oder (beginnend mit C# 7) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f9309-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="f9309-112">Wenn sich das Ganzzahlliteral außerhalb des Bereichs von `short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=fullName> oder größer als <xref:System.Int16.MaxValue?displayProperty=fullName> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="f9309-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=fullName> or greater than <xref:System.Int16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="f9309-113">Im folgenden Beispiel werden Ganzzahlen wie 1.034, die als dezimale, hexadezimale und binäre Literale dargestellt werden, implizit aus [int](../../../csharp/language-reference/keywords/int.md) in `short`-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f9309-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
<span data-ttu-id="f9309-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span><span class="sxs-lookup"><span data-stu-id="f9309-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="f9309-115">Verwenden Sie das Präfix `0x` oder `0X` zum Kennzeichnen eines hexadezimalen Literals und das Präfix `0b` oder `0B` zum Kennzeichnen eines binären Literals.</span><span class="sxs-lookup"><span data-stu-id="f9309-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="f9309-116">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="f9309-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="f9309-117">Ab C# 7 können Sie auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f9309-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="f9309-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span><span class="sxs-lookup"><span data-stu-id="f9309-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="f9309-119">Überladungsauflösung des Compiler</span><span class="sxs-lookup"><span data-stu-id="f9309-119">Compiler overload resolution</span></span>

 <span data-ttu-id="f9309-120">Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f9309-120">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="f9309-121">Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `short` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:</span><span class="sxs-lookup"><span data-stu-id="f9309-121">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="f9309-122">Die Verwendung der `short`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="f9309-122">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="f9309-123">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f9309-123">Conversions</span></span>  

 <span data-ttu-id="f9309-124">Es gibt eine vordefinierte implizite Konvertierung von `short` in [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="f9309-124">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="f9309-125">Sie können numerische nonliteral-Typen einer größeren Speichergröße nicht implizit in `short` konvertieren (siehe [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) für die Speichergrößen ganzzahliger Typen).</span><span class="sxs-lookup"><span data-stu-id="f9309-125">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="f9309-126">Betrachten Sie z.B. die folgenden beiden `short`-Variablen `x` und `y`:</span><span class="sxs-lookup"><span data-stu-id="f9309-126">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="f9309-127">Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig [int](../../../csharp/language-reference/keywords/int.md) ergibt.</span><span class="sxs-lookup"><span data-stu-id="f9309-127">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="f9309-128">Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:</span><span class="sxs-lookup"><span data-stu-id="f9309-128">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="f9309-129">Es ist jedoch auch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:</span><span class="sxs-lookup"><span data-stu-id="f9309-129">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="f9309-130">Es gibt keine implizite Konvertierung von Gleitkommadatentypen zu `short`.</span><span class="sxs-lookup"><span data-stu-id="f9309-130">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="f9309-131">Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:</span><span class="sxs-lookup"><span data-stu-id="f9309-131">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="f9309-132">Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und Ganzzahltypen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="f9309-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="f9309-133">Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie in der [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="f9309-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f9309-134">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f9309-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9309-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9309-135">See Also</span></span>  
 <span data-ttu-id="f9309-136"><xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="f9309-136"><xref:System.Int16></span></span>   
 <span data-ttu-id="f9309-137">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9309-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f9309-138">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9309-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f9309-139">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9309-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f9309-140">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="f9309-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="f9309-141">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="f9309-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="f9309-142">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="f9309-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="f9309-143">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f9309-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

