---
title: Tabelle für implizite numerische Konvertierungen (C#-Referenz)
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: c3c0153a0ae3e07839822c8bb978b1a09277bd53
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188702"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="995c6-102">Tabelle für implizite numerische Konvertierungen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="995c6-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="995c6-103">Folgende Tabelle veranschaulicht vordefinierte implizite Konvertierungen zwischen numerischen .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="995c6-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="995c6-104">Von</span><span class="sxs-lookup"><span data-stu-id="995c6-104">From</span></span>|<span data-ttu-id="995c6-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="995c6-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="995c6-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="995c6-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="995c6-107">`short`, `int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-108">byte</span><span class="sxs-lookup"><span data-stu-id="995c6-108">byte</span></span>](byte.md)|<span data-ttu-id="995c6-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-110">short</span><span class="sxs-lookup"><span data-stu-id="995c6-110">short</span></span>](short.md)|<span data-ttu-id="995c6-111">`int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-111">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-112">ushort</span><span class="sxs-lookup"><span data-stu-id="995c6-112">ushort</span></span>](ushort.md)|<span data-ttu-id="995c6-113">`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-113">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-114">int</span><span class="sxs-lookup"><span data-stu-id="995c6-114">int</span></span>](int.md)|<span data-ttu-id="995c6-115">`long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-115">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-116">uint</span><span class="sxs-lookup"><span data-stu-id="995c6-116">uint</span></span>](uint.md)|<span data-ttu-id="995c6-117">`long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-117">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-118">long</span><span class="sxs-lookup"><span data-stu-id="995c6-118">long</span></span>](long.md)|<span data-ttu-id="995c6-119">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-119">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-120">char</span><span class="sxs-lookup"><span data-stu-id="995c6-120">char</span></span>](char.md)|<span data-ttu-id="995c6-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="995c6-122">float</span><span class="sxs-lookup"><span data-stu-id="995c6-122">float</span></span>](float.md)|`double`|  
|[<span data-ttu-id="995c6-123">ulong</span><span class="sxs-lookup"><span data-stu-id="995c6-123">ulong</span></span>](ulong.md)|<span data-ttu-id="995c6-124">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="995c6-124">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="995c6-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="995c6-125">Remarks</span></span>  

- <span data-ttu-id="995c6-126">Jeder [integrale Typ](integral-types-table.md) kann implizit in einen beliebigen [Gleitkommatyp](floating-point-types-table.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="995c6-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="995c6-127">Bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` kann Präzision verloren gehen, aber keine Größe.</span><span class="sxs-lookup"><span data-stu-id="995c6-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="995c6-128">Es gibt keine impliziten Konvertierungen für den Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="995c6-128">There are no implicit conversions to the `char` type.</span></span>  
  
- <span data-ttu-id="995c6-129">Es gibt keine impliziten Konvertierungen zwischen den Typen `float` und `double` und dem Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="995c6-129">There are no implicit conversions between the `float` and `double` types and the `decimal` type.</span></span>  
  
- <span data-ttu-id="995c6-130">Ein Wert eines konstanten Ausdrucks vom Typ `int` (z.B. ein Wert, der von einem integralen Literal dargestellt wird) kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, solange er sich innerhalb des Bereichs des Zieltyps befindet:</span><span class="sxs-lookup"><span data-stu-id="995c6-130">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="995c6-131">Weitere Informationen über implizite Konvertierungen finden Sie im Abschnitt [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="995c6-131">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="995c6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="995c6-132">See also</span></span>

- [<span data-ttu-id="995c6-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="995c6-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="995c6-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="995c6-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="995c6-135">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="995c6-135">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="995c6-136">Tabelle für Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="995c6-136">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="995c6-137">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="995c6-137">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="995c6-138">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="995c6-138">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="995c6-139">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="995c6-139">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
