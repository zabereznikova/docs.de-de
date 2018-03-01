---
title: double (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 232dd97e152f943137604074f24b5de779168e59
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="double-c-reference"></a><span data-ttu-id="46727-102">double (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="46727-102">double (C# Reference)</span></span>
<span data-ttu-id="46727-103">Das `double`-Schlüsselwort kennzeichnet einen einfachen Typ, der 64-Bit-Gleitkommawerte speichert.</span><span class="sxs-lookup"><span data-stu-id="46727-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="46727-104">Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `double`-Typ an.</span><span class="sxs-lookup"><span data-stu-id="46727-104">The following table shows the precision and approximate range for the `double` type.</span></span>  
  
|<span data-ttu-id="46727-105">Typ</span><span class="sxs-lookup"><span data-stu-id="46727-105">Type</span></span>|<span data-ttu-id="46727-106">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="46727-106">Approximate range</span></span>|<span data-ttu-id="46727-107">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="46727-107">Precision</span></span>|<span data-ttu-id="46727-108">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="46727-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|<span data-ttu-id="46727-109">±5.0 × 10<sup>−324</sup> zu ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="46727-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="46727-110">15-16 Ziffern</span><span class="sxs-lookup"><span data-stu-id="46727-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="46727-111">Literale</span><span class="sxs-lookup"><span data-stu-id="46727-111">Literals</span></span>  
 <span data-ttu-id="46727-112">Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt.</span><span class="sxs-lookup"><span data-stu-id="46727-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="46727-113">Aber wenn Sie eine ganze Zahl als `double` behandeln möchten, verwenden Sie das Suffix d oder D, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="46727-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a><span data-ttu-id="46727-114">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="46727-114">Conversions</span></span>  
 <span data-ttu-id="46727-115">Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="46727-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="46727-116">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="46727-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="46727-117">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="46727-117">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="46727-118">Wenn einer der Gleitkommatypen `double` ist, ergibt der Ausdruck `double`, oder [bool](../../../csharp/language-reference/keywords/bool.md) in relationalen oder booleschen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="46727-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="46727-119">Wenn es im Ausdruck keinen `double`-Typ gibt, ergibt der es [float](../../../csharp/language-reference/keywords/float.md), oder [bool](../../../csharp/language-reference/keywords/bool.md) in relationalen oder booleschen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="46727-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="46727-120">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="46727-120">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="46727-121">Positive und negative null</span><span class="sxs-lookup"><span data-stu-id="46727-121">Positive and negative zero.</span></span>  
  
-   <span data-ttu-id="46727-122">Positive und negative Infinity</span><span class="sxs-lookup"><span data-stu-id="46727-122">Positive and negative infinity.</span></span>  
  
-   <span data-ttu-id="46727-123">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="46727-123">Not-a-Number value (NaN).</span></span>  
  
-   <span data-ttu-id="46727-124">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="46727-124">The finite set of nonzero values.</span></span>  
  
 <span data-ttu-id="46727-125">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](http://www.ieee.org)-Website.</span><span class="sxs-lookup"><span data-stu-id="46727-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://www.ieee.org) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46727-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46727-126">Example</span></span>  
 <span data-ttu-id="46727-127">Im folgenden Beispiel werden ein [int](../../../csharp/language-reference/keywords/int.md), ein [short](../../../csharp/language-reference/keywords/short.md),ein [float](../../../csharp/language-reference/keywords/float.md) und ein `double` zusammen addiert, was ein `double`-Ergebnis ergibt.</span><span class="sxs-lookup"><span data-stu-id="46727-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="46727-128">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="46727-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46727-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46727-129">See Also</span></span>  
 [<span data-ttu-id="46727-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="46727-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="46727-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="46727-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="46727-132">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="46727-132">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="46727-133">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="46727-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="46727-134">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="46727-134">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="46727-135">Tabelle für Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="46727-135">Floating-Point Types Table</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
 [<span data-ttu-id="46727-136">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="46727-136">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="46727-137">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="46727-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
