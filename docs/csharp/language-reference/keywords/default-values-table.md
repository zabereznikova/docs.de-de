---
title: Tabelle für Standardwerte (C#-Referenz)
description: In diesem Artikel lernen Sie die Standardwerte von Werttypen kennen, die von den Standardkonstruktoren zurückgegeben werden.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218789"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="67ab9-103">Tabelle für Standardwerte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="67ab9-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="67ab9-104">In der folgenden Tabelle werden die Standardwerte von Werttypen gezeigt, die von den Standardkonstruktoren zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="67ab9-104">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="67ab9-105">Standardkonstruktoren werden mit dem `new`-Operator wie folgt aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="67ab9-105">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="67ab9-106">Die vorherige Anweisung hat den gleichen Effekt wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="67ab9-106">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="67ab9-107">Denken Sie daran, dass die Verwendung von nicht initialisierten Variablen in C# nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="67ab9-107">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="67ab9-108">Werttyp</span><span class="sxs-lookup"><span data-stu-id="67ab9-108">Value type</span></span>|<span data-ttu-id="67ab9-109">Standardwert</span><span class="sxs-lookup"><span data-stu-id="67ab9-109">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="67ab9-110">bool</span><span class="sxs-lookup"><span data-stu-id="67ab9-110">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="67ab9-111">byte</span><span class="sxs-lookup"><span data-stu-id="67ab9-111">byte</span></span>](byte.md)|<span data-ttu-id="67ab9-112">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-112">0</span></span>|
|[<span data-ttu-id="67ab9-113">char</span><span class="sxs-lookup"><span data-stu-id="67ab9-113">char</span></span>](char.md)|<span data-ttu-id="67ab9-114">'\0'</span><span class="sxs-lookup"><span data-stu-id="67ab9-114">'\0'</span></span>|
|[<span data-ttu-id="67ab9-115">decimal</span><span class="sxs-lookup"><span data-stu-id="67ab9-115">decimal</span></span>](decimal.md)|<span data-ttu-id="67ab9-116">0M</span><span class="sxs-lookup"><span data-stu-id="67ab9-116">0M</span></span>|
|[<span data-ttu-id="67ab9-117">double</span><span class="sxs-lookup"><span data-stu-id="67ab9-117">double</span></span>](double.md)|<span data-ttu-id="67ab9-118">0.0D</span><span class="sxs-lookup"><span data-stu-id="67ab9-118">0.0D</span></span>|
|[<span data-ttu-id="67ab9-119">enum</span><span class="sxs-lookup"><span data-stu-id="67ab9-119">enum</span></span>](enum.md)|<span data-ttu-id="67ab9-120">Der Wert, der vom Ausdruck (E)0 erzeugt wird, bei dem E der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="67ab9-120">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="67ab9-121">float</span><span class="sxs-lookup"><span data-stu-id="67ab9-121">float</span></span>](float.md)|<span data-ttu-id="67ab9-122">0.0F</span><span class="sxs-lookup"><span data-stu-id="67ab9-122">0.0F</span></span>|
|[<span data-ttu-id="67ab9-123">int</span><span class="sxs-lookup"><span data-stu-id="67ab9-123">int</span></span>](int.md)|<span data-ttu-id="67ab9-124">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-124">0</span></span>|
|[<span data-ttu-id="67ab9-125">long</span><span class="sxs-lookup"><span data-stu-id="67ab9-125">long</span></span>](long.md)|<span data-ttu-id="67ab9-126">0L</span><span class="sxs-lookup"><span data-stu-id="67ab9-126">0L</span></span>|
|[<span data-ttu-id="67ab9-127">sbyte</span><span class="sxs-lookup"><span data-stu-id="67ab9-127">sbyte</span></span>](sbyte.md)|<span data-ttu-id="67ab9-128">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-128">0</span></span>|
|[<span data-ttu-id="67ab9-129">short</span><span class="sxs-lookup"><span data-stu-id="67ab9-129">short</span></span>](short.md)|<span data-ttu-id="67ab9-130">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-130">0</span></span>|
|[<span data-ttu-id="67ab9-131">struct</span><span class="sxs-lookup"><span data-stu-id="67ab9-131">struct</span></span>](struct.md)|<span data-ttu-id="67ab9-132">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.</span><span class="sxs-lookup"><span data-stu-id="67ab9-132">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="67ab9-133">uint</span><span class="sxs-lookup"><span data-stu-id="67ab9-133">uint</span></span>](uint.md)|<span data-ttu-id="67ab9-134">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-134">0</span></span>|
|[<span data-ttu-id="67ab9-135">ulong</span><span class="sxs-lookup"><span data-stu-id="67ab9-135">ulong</span></span>](ulong.md)|<span data-ttu-id="67ab9-136">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-136">0</span></span>|
|[<span data-ttu-id="67ab9-137">ushort</span><span class="sxs-lookup"><span data-stu-id="67ab9-137">ushort</span></span>](ushort.md)|<span data-ttu-id="67ab9-138">0</span><span class="sxs-lookup"><span data-stu-id="67ab9-138">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="67ab9-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67ab9-139">See also</span></span>
 [<span data-ttu-id="67ab9-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="67ab9-140">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="67ab9-141">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="67ab9-141">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="67ab9-142">Tabelle der Werttypen</span><span class="sxs-lookup"><span data-stu-id="67ab9-142">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="67ab9-143">Werttypen</span><span class="sxs-lookup"><span data-stu-id="67ab9-143">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="67ab9-144">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="67ab9-144">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="67ab9-145">Referenztabellen für Typen</span><span class="sxs-lookup"><span data-stu-id="67ab9-145">Reference Tables for Types</span></span>](reference-tables-for-types.md)
