---
title: Tabelle für Standardwerte (C#-Referenz)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="f2b7a-102">Tabelle für Standardwerte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f2b7a-102">Default values table (C# Reference)</span></span>

<span data-ttu-id="f2b7a-103">In der folgenden Tabelle werden die Standardwerte von Werttypen gezeigt, die von den Standardkonstruktoren zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2b7a-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="f2b7a-104">Standardkonstruktoren werden mit dem `new`-Operator wie folgt aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="f2b7a-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="f2b7a-105">Die vorherige Anweisung hat den gleichen Effekt wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="f2b7a-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="f2b7a-106">Denken Sie daran, dass die Verwendung von nicht initialisierten Variablen in C# nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="f2b7a-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="f2b7a-107">Werttyp</span><span class="sxs-lookup"><span data-stu-id="f2b7a-107">Value type</span></span>|<span data-ttu-id="f2b7a-108">Standardwert</span><span class="sxs-lookup"><span data-stu-id="f2b7a-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="f2b7a-109">bool</span><span class="sxs-lookup"><span data-stu-id="f2b7a-109">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="f2b7a-110">byte</span><span class="sxs-lookup"><span data-stu-id="f2b7a-110">byte</span></span>](byte.md)|<span data-ttu-id="f2b7a-111">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-111">0</span></span>|
|[<span data-ttu-id="f2b7a-112">char</span><span class="sxs-lookup"><span data-stu-id="f2b7a-112">char</span></span>](char.md)|<span data-ttu-id="f2b7a-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="f2b7a-113">'\0'</span></span>|
|[<span data-ttu-id="f2b7a-114">decimal</span><span class="sxs-lookup"><span data-stu-id="f2b7a-114">decimal</span></span>](decimal.md)|<span data-ttu-id="f2b7a-115">0M</span><span class="sxs-lookup"><span data-stu-id="f2b7a-115">0M</span></span>|
|[<span data-ttu-id="f2b7a-116">double</span><span class="sxs-lookup"><span data-stu-id="f2b7a-116">double</span></span>](double.md)|<span data-ttu-id="f2b7a-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="f2b7a-117">0.0D</span></span>|
|[<span data-ttu-id="f2b7a-118">enum</span><span class="sxs-lookup"><span data-stu-id="f2b7a-118">enum</span></span>](enum.md)|<span data-ttu-id="f2b7a-119">Der Wert, der vom Ausdruck (E)0 erzeugt wird, bei dem E der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="f2b7a-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="f2b7a-120">float</span><span class="sxs-lookup"><span data-stu-id="f2b7a-120">float</span></span>](float.md)|<span data-ttu-id="f2b7a-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="f2b7a-121">0.0F</span></span>|
|[<span data-ttu-id="f2b7a-122">int</span><span class="sxs-lookup"><span data-stu-id="f2b7a-122">int</span></span>](int.md)|<span data-ttu-id="f2b7a-123">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-123">0</span></span>|
|[<span data-ttu-id="f2b7a-124">long</span><span class="sxs-lookup"><span data-stu-id="f2b7a-124">long</span></span>](long.md)|<span data-ttu-id="f2b7a-125">0L</span><span class="sxs-lookup"><span data-stu-id="f2b7a-125">0L</span></span>|
|[<span data-ttu-id="f2b7a-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="f2b7a-126">sbyte</span></span>](sbyte.md)|<span data-ttu-id="f2b7a-127">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-127">0</span></span>|
|[<span data-ttu-id="f2b7a-128">short</span><span class="sxs-lookup"><span data-stu-id="f2b7a-128">short</span></span>](short.md)|<span data-ttu-id="f2b7a-129">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-129">0</span></span>|
|[<span data-ttu-id="f2b7a-130">struct</span><span class="sxs-lookup"><span data-stu-id="f2b7a-130">struct</span></span>](struct.md)|<span data-ttu-id="f2b7a-131">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.</span><span class="sxs-lookup"><span data-stu-id="f2b7a-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="f2b7a-132">uint</span><span class="sxs-lookup"><span data-stu-id="f2b7a-132">uint</span></span>](uint.md)|<span data-ttu-id="f2b7a-133">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-133">0</span></span>|
|[<span data-ttu-id="f2b7a-134">ulong</span><span class="sxs-lookup"><span data-stu-id="f2b7a-134">ulong</span></span>](ulong.md)|<span data-ttu-id="f2b7a-135">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-135">0</span></span>|
|[<span data-ttu-id="f2b7a-136">ushort</span><span class="sxs-lookup"><span data-stu-id="f2b7a-136">ushort</span></span>](ushort.md)|<span data-ttu-id="f2b7a-137">0</span><span class="sxs-lookup"><span data-stu-id="f2b7a-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="f2b7a-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2b7a-138">See also</span></span>
 [<span data-ttu-id="f2b7a-139">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f2b7a-139">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="f2b7a-140">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f2b7a-140">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="f2b7a-141">Tabelle der Werttypen</span><span class="sxs-lookup"><span data-stu-id="f2b7a-141">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="f2b7a-142">Werttypen</span><span class="sxs-lookup"><span data-stu-id="f2b7a-142">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="f2b7a-143">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="f2b7a-143">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="f2b7a-144">Referenztabellen für Typen</span><span class="sxs-lookup"><span data-stu-id="f2b7a-144">Reference Tables for Types</span></span>](reference-tables-for-types.md)
