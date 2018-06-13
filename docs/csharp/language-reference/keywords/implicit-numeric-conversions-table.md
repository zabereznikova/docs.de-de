---
title: Tabelle für implizite numerische Konvertierungen (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 2d417a2020656f300de0517526742679388f262e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33217193"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="f0d3c-102">Tabelle für implizite numerische Konvertierungen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f0d3c-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="f0d3c-103">Folgende Tabelle veranschaulicht vordefinierte implizite numerische Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="f0d3c-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="f0d3c-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="f0d3c-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="f0d3c-105">Von</span><span class="sxs-lookup"><span data-stu-id="f0d3c-105">From</span></span>|<span data-ttu-id="f0d3c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0d3c-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="f0d3c-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="f0d3c-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="f0d3c-108">`short`, `int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-109">byte</span><span class="sxs-lookup"><span data-stu-id="f0d3c-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="f0d3c-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-111">short</span><span class="sxs-lookup"><span data-stu-id="f0d3c-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="f0d3c-112">`int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-113">ushort</span><span class="sxs-lookup"><span data-stu-id="f0d3c-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="f0d3c-114">`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-115">int</span><span class="sxs-lookup"><span data-stu-id="f0d3c-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="f0d3c-116">`long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-117">uint</span><span class="sxs-lookup"><span data-stu-id="f0d3c-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="f0d3c-118">`long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-119">long</span><span class="sxs-lookup"><span data-stu-id="f0d3c-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="f0d3c-120">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-121">char</span><span class="sxs-lookup"><span data-stu-id="f0d3c-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="f0d3c-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="f0d3c-123">float</span><span class="sxs-lookup"><span data-stu-id="f0d3c-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="f0d3c-124">ulong</span><span class="sxs-lookup"><span data-stu-id="f0d3c-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="f0d3c-125">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="f0d3c-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0d3c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0d3c-126">Remarks</span></span>  
  
-   <span data-ttu-id="f0d3c-127">Präzision, aber keine Größe, geht möglicherweise bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` verloren.</span><span class="sxs-lookup"><span data-stu-id="f0d3c-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="f0d3c-128">Es gibt keine impliziten Konvertierungen für den Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="f0d3c-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="f0d3c-129">Es gibt keine impliziten Konvertierungen zwischen Gleitkommatypen und dem Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="f0d3c-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="f0d3c-130">Ein konstanter Ausdruck des Typs `int` kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, gesetzt dem Fall der konstante Ausdruck befindet sich im Bereich des Zieltyps.</span><span class="sxs-lookup"><span data-stu-id="f0d3c-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f0d3c-131">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f0d3c-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0d3c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0d3c-132">See Also</span></span>  
 [<span data-ttu-id="f0d3c-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f0d3c-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f0d3c-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f0d3c-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f0d3c-135">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="f0d3c-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="f0d3c-136">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="f0d3c-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="f0d3c-137">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="f0d3c-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="f0d3c-138">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="f0d3c-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
