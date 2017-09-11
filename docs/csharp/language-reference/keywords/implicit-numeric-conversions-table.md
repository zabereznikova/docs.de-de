---
title: "Tabelle für implizite numerische Konvertierungen (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: 12
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
ms.openlocfilehash: 4c7aa29f9bdeb5f30918e6d7b990c5197e7fe1a1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="4e1ab-102">Tabelle für implizite numerische Konvertierungen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4e1ab-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="4e1ab-103">Folgende Tabelle veranschaulicht vordefinierte implizite numerische Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="4e1ab-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="4e1ab-105">Von</span><span class="sxs-lookup"><span data-stu-id="4e1ab-105">From</span></span>|<span data-ttu-id="4e1ab-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e1ab-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="4e1ab-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="4e1ab-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="4e1ab-108">`short`, `int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-109">byte</span><span class="sxs-lookup"><span data-stu-id="4e1ab-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="4e1ab-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-111">short</span><span class="sxs-lookup"><span data-stu-id="4e1ab-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="4e1ab-112">`int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-113">ushort</span><span class="sxs-lookup"><span data-stu-id="4e1ab-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="4e1ab-114">`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-115">int</span><span class="sxs-lookup"><span data-stu-id="4e1ab-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="4e1ab-116">`long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-117">uint</span><span class="sxs-lookup"><span data-stu-id="4e1ab-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="4e1ab-118">`long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-119">long</span><span class="sxs-lookup"><span data-stu-id="4e1ab-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="4e1ab-120">`float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-121">char</span><span class="sxs-lookup"><span data-stu-id="4e1ab-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="4e1ab-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="4e1ab-123">float</span><span class="sxs-lookup"><span data-stu-id="4e1ab-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="4e1ab-124">ulong</span><span class="sxs-lookup"><span data-stu-id="4e1ab-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="4e1ab-125">`float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="4e1ab-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e1ab-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e1ab-126">Remarks</span></span>  
  
-   <span data-ttu-id="4e1ab-127">Präzision, aber keine Größe, geht möglicherweise bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` verloren.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="4e1ab-128">Es gibt keine impliziten Konvertierungen für den Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="4e1ab-129">Es gibt keine impliziten Konvertierungen zwischen Gleitkommatypen und dem Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="4e1ab-130">Ein konstanter Ausdruck des Typs `int` kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, gesetzt dem Fall der konstante Ausdruck befindet sich im Bereich des Zieltyps.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4e1ab-131">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4e1ab-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e1ab-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e1ab-132">See Also</span></span>  
 <span data-ttu-id="4e1ab-133">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e1ab-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4e1ab-134">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e1ab-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4e1ab-135">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e1ab-135">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="4e1ab-136">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e1ab-136">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="4e1ab-137">[Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e1ab-137">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="4e1ab-138">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="4e1ab-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

