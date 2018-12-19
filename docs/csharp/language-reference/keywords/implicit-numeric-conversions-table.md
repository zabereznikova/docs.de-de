---
title: Tabelle für implizite numerische Konvertierungen – C#-Referenz
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 98774a0f7ad86e43178c6d0216e29e7b4767f3f2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235253"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="1c76a-102">Tabelle für implizite numerische Konvertierungen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1c76a-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="1c76a-103">Folgende Tabelle veranschaulicht vordefinierte implizite Konvertierungen zwischen numerischen .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="1c76a-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="1c76a-104">Von</span><span class="sxs-lookup"><span data-stu-id="1c76a-104">From</span></span>|<span data-ttu-id="1c76a-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c76a-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="1c76a-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="1c76a-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="1c76a-107">`short`, `int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-108">byte</span><span class="sxs-lookup"><span data-stu-id="1c76a-108">byte</span></span>](byte.md)|<span data-ttu-id="1c76a-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-110">short</span><span class="sxs-lookup"><span data-stu-id="1c76a-110">short</span></span>](short.md)|<span data-ttu-id="1c76a-111">`int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-111">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-112">ushort</span><span class="sxs-lookup"><span data-stu-id="1c76a-112">ushort</span></span>](ushort.md)|<span data-ttu-id="1c76a-113">`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-113">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-114">int</span><span class="sxs-lookup"><span data-stu-id="1c76a-114">int</span></span>](int.md)|<span data-ttu-id="1c76a-115">`long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-115">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-116">uint</span><span class="sxs-lookup"><span data-stu-id="1c76a-116">uint</span></span>](uint.md)|<span data-ttu-id="1c76a-117">`long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-117">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-118">long</span><span class="sxs-lookup"><span data-stu-id="1c76a-118">long</span></span>](long.md)|<span data-ttu-id="1c76a-119">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-119">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-120">char</span><span class="sxs-lookup"><span data-stu-id="1c76a-120">char</span></span>](char.md)|<span data-ttu-id="1c76a-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="1c76a-122">float</span><span class="sxs-lookup"><span data-stu-id="1c76a-122">float</span></span>](float.md)|`double`|  
|[<span data-ttu-id="1c76a-123">ulong</span><span class="sxs-lookup"><span data-stu-id="1c76a-123">ulong</span></span>](ulong.md)|<span data-ttu-id="1c76a-124">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="1c76a-124">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c76a-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c76a-125">Remarks</span></span>  

- <span data-ttu-id="1c76a-126">Jeder [integrale Typ](integral-types-table.md) kann implizit in einen beliebigen [Gleitkommatyp](floating-point-types-table.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1c76a-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="1c76a-127">Bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` kann Präzision verloren gehen, aber keine Größe.</span><span class="sxs-lookup"><span data-stu-id="1c76a-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="1c76a-128">Es gibt keine impliziten Konvertierungen für den Typ `char`.</span><span class="sxs-lookup"><span data-stu-id="1c76a-128">There are no implicit conversions to the `char` type.</span></span>  
  
- <span data-ttu-id="1c76a-129">Es gibt keine impliziten Konvertierungen zwischen den Typen `float` und `double` und dem Typ `decimal`.</span><span class="sxs-lookup"><span data-stu-id="1c76a-129">There are no implicit conversions between the `float` and `double` types and the `decimal` type.</span></span>  
  
- <span data-ttu-id="1c76a-130">Ein Wert eines konstanten Ausdrucks vom Typ `int` (z.B. ein Wert, der von einem integralen Literal dargestellt wird) kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, solange er sich innerhalb des Bereichs des Zieltyps befindet:</span><span class="sxs-lookup"><span data-stu-id="1c76a-130">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="1c76a-131">Weitere Informationen über implizite Konvertierungen finden Sie im Abschnitt [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="1c76a-131">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c76a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c76a-132">See also</span></span>

- [<span data-ttu-id="1c76a-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1c76a-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1c76a-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1c76a-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1c76a-135">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="1c76a-135">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="1c76a-136">Tabelle für Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="1c76a-136">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="1c76a-137">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="1c76a-137">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="1c76a-138">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1c76a-138">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="1c76a-139">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="1c76a-139">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
