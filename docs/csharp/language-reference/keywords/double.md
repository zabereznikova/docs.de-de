---
title: double (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- double
- double_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
caps.latest.revision: 26
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
ms.openlocfilehash: d5588f8391157fb56a5e5067bb8e11f9269fe733
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="double-c-reference"></a><span data-ttu-id="e8879-102">double (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e8879-102">double (C# Reference)</span></span>
<span data-ttu-id="e8879-103">Das `double`-Schlüsselwort kennzeichnet einen einfachen Typ, der 64-Bit-Gleitkommawerte speichert.</span><span class="sxs-lookup"><span data-stu-id="e8879-103">The `double` keyword signifies a simple type that stores 64-bit floating-point values.</span></span> <span data-ttu-id="e8879-104">Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `double`-Typ an.</span><span class="sxs-lookup"><span data-stu-id="e8879-104">The following table shows the precision and approximate range for the `double` type.</span></span>  
  
|<span data-ttu-id="e8879-105">Typ</span><span class="sxs-lookup"><span data-stu-id="e8879-105">Type</span></span>|<span data-ttu-id="e8879-106">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="e8879-106">Approximate range</span></span>|<span data-ttu-id="e8879-107">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="e8879-107">Precision</span></span>|<span data-ttu-id="e8879-108">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="e8879-108">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|<span data-ttu-id="e8879-109">±5.0 × 10<sup>−324</sup> zu ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="e8879-109">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="e8879-110">15-16 Ziffern</span><span class="sxs-lookup"><span data-stu-id="e8879-110">15-16 digits</span></span>|<xref:System.Double?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="e8879-111">Literale</span><span class="sxs-lookup"><span data-stu-id="e8879-111">Literals</span></span>  
 <span data-ttu-id="e8879-112">Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als `double` behandelt.</span><span class="sxs-lookup"><span data-stu-id="e8879-112">By default, a real numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="e8879-113">Aber wenn Sie eine ganze Zahl als `double` behandeln möchten, verwenden Sie das Suffix d oder D, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="e8879-113">However, if you want an integer number to be treated as `double`, use the suffix d or D, for example:</span></span>  
  
```  
double x = 3D;  
```  
  
## <a name="conversions"></a><span data-ttu-id="e8879-114">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="e8879-114">Conversions</span></span>  
 <span data-ttu-id="e8879-115">Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e8879-115">You can mix numeric integral types and floating-point types in an expression.</span></span> <span data-ttu-id="e8879-116">In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e8879-116">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="e8879-117">Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="e8879-117">The evaluation of the expression is performed according to the following rules:</span></span>  
  
-   <span data-ttu-id="e8879-118">Wenn einer der Gleitkommatypen `double` ist, ergibt der Ausdruck `double`, oder [bool](../../../csharp/language-reference/keywords/bool.md) in relationalen oder booleschen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="e8879-118">If one of the floating-point types is `double`, the expression evaluates to `double`, or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
-   <span data-ttu-id="e8879-119">Wenn es im Ausdruck keinen `double`-Typ gibt, ergibt der es [float](../../../csharp/language-reference/keywords/float.md), oder [bool](../../../csharp/language-reference/keywords/bool.md) in relationalen oder booleschen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="e8879-119">If there is no `double` type in the expression, it evaluates to [float](../../../csharp/language-reference/keywords/float.md), or [bool](../../../csharp/language-reference/keywords/bool.md) in relational or Boolean expressions.</span></span>  
  
 <span data-ttu-id="e8879-120">Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:</span><span class="sxs-lookup"><span data-stu-id="e8879-120">A floating-point expression can contain the following sets of values:</span></span>  
  
-   <span data-ttu-id="e8879-121">Positive und negative null</span><span class="sxs-lookup"><span data-stu-id="e8879-121">Positive and negative zero.</span></span>  
  
-   <span data-ttu-id="e8879-122">Positive und negative Infinity</span><span class="sxs-lookup"><span data-stu-id="e8879-122">Positive and negative infinity.</span></span>  
  
-   <span data-ttu-id="e8879-123">Not-a-Number-Wert (NaN)</span><span class="sxs-lookup"><span data-stu-id="e8879-123">Not-a-Number value (NaN).</span></span>  
  
-   <span data-ttu-id="e8879-124">Die begrenzte Menge von Werten ungleich Null</span><span class="sxs-lookup"><span data-stu-id="e8879-124">The finite set of nonzero values.</span></span>  
  
 <span data-ttu-id="e8879-125">Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269)-Website.</span><span class="sxs-lookup"><span data-stu-id="e8879-125">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269) Web site.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8879-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8879-126">Example</span></span>  
 <span data-ttu-id="e8879-127">Im folgenden Beispiel werden ein [int](../../../csharp/language-reference/keywords/int.md), ein [short](../../../csharp/language-reference/keywords/short.md),ein [float](../../../csharp/language-reference/keywords/float.md) und ein `double` zusammen addiert, was ein `double`-Ergebnis ergibt.</span><span class="sxs-lookup"><span data-stu-id="e8879-127">In the following example, an [int](../../../csharp/language-reference/keywords/int.md), a [short](../../../csharp/language-reference/keywords/short.md), a [float](../../../csharp/language-reference/keywords/float.md), and a `double` are added together giving a `double` result.</span></span>  
  
 <span data-ttu-id="e8879-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e8879-128">[!code-cs[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e8879-129">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e8879-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8879-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8879-130">See Also</span></span>  
 <span data-ttu-id="e8879-131">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e8879-132">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e8879-133">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="e8879-134">[Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-134">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="e8879-135">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-135">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="e8879-136">[Tabelle für Gleitkommatypen](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-136">[Floating-Point Types Table](../../../csharp/language-reference/keywords/floating-point-types-table.md) </span></span>  
 <span data-ttu-id="e8879-137">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="e8879-137">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="e8879-138">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="e8879-138">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

