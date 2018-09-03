---
title: Tabelle für implizite numerische Konvertierungen (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 4bbc6086dc5fd3838ef9361762c3068ca44efd0e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43417595"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="210d5-102">Tabelle für implizite numerische Konvertierungen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="210d5-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="210d5-103">Folgende Tabelle veranschaulicht vordefinierte implizite numerische Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="210d5-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="210d5-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="210d5-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="210d5-105">Von</span><span class="sxs-lookup"><span data-stu-id="210d5-105">From</span></span>|<span data-ttu-id="210d5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="210d5-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="210d5-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="210d5-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="210d5-108">`short`, `int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-109">byte</span><span class="sxs-lookup"><span data-stu-id="210d5-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="210d5-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-111">short</span><span class="sxs-lookup"><span data-stu-id="210d5-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="210d5-112">`int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-113">ushort</span><span class="sxs-lookup"><span data-stu-id="210d5-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="210d5-114">`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-115">int</span><span class="sxs-lookup"><span data-stu-id="210d5-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="210d5-116">`long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-117">uint</span><span class="sxs-lookup"><span data-stu-id="210d5-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="210d5-118">`long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-119">long</span><span class="sxs-lookup"><span data-stu-id="210d5-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="210d5-120">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-121">char</span><span class="sxs-lookup"><span data-stu-id="210d5-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="210d5-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="210d5-123">float</span><span class="sxs-lookup"><span data-stu-id="210d5-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="210d5-124">ulong</span><span class="sxs-lookup"><span data-stu-id="210d5-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="210d5-125">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="210d5-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="210d5-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="210d5-126">Remarks</span></span>  
  
-   <span data-ttu-id="210d5-127">Präzision, aber keine Größe, geht möglicherweise bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` verloren.</span><span class="sxs-lookup"><span data-stu-id="210d5-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="210d5-128">Es gibt keine impliziten Konvertierungen für den Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="210d5-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="210d5-129">Es gibt keine impliziten Konvertierungen zwischen Gleitkommatypen und dem Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="210d5-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="210d5-130">Ein konstanter Ausdruck des Typs `int` kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, gesetzt dem Fall der konstante Ausdruck befindet sich im Bereich des Zieltyps.</span><span class="sxs-lookup"><span data-stu-id="210d5-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="210d5-131">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="210d5-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="210d5-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="210d5-132">See Also</span></span>  

- [<span data-ttu-id="210d5-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="210d5-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="210d5-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="210d5-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="210d5-135">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="210d5-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="210d5-136">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="210d5-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="210d5-137">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="210d5-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [<span data-ttu-id="210d5-138">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="210d5-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
