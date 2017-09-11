---
title: "Tabelle für Standardwerte (C#-Referenz)"
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: f8cf12317f1f0163028db003ff31604480da5d1c
ms.openlocfilehash: 975d416259778e0741347829d8a9c79aaa6cfc8c
ms.contentlocale: de-de
ms.lasthandoff: 08/12/2017

---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="3f6ac-102">Tabelle für Standardwerte (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3f6ac-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="3f6ac-103">In der folgenden Tabelle werden die Standardwerte von Werttypen gezeigt, die von den Standardkonstruktoren zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f6ac-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="3f6ac-104">Standardkonstruktoren werden mit dem `new`-Operator wie folgt aufgerufen:</span><span class="sxs-lookup"><span data-stu-id="3f6ac-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="3f6ac-105">Die vorherige Anweisung hat den gleichen Effekt wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="3f6ac-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="3f6ac-106">Denken Sie daran, dass die Verwendung von nicht initialisierten Variablen in C# nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="3f6ac-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="3f6ac-107">Werttyp</span><span class="sxs-lookup"><span data-stu-id="3f6ac-107">Value type</span></span>|<span data-ttu-id="3f6ac-108">Standardwert</span><span class="sxs-lookup"><span data-stu-id="3f6ac-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="3f6ac-109">bool</span><span class="sxs-lookup"><span data-stu-id="3f6ac-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="3f6ac-110">byte</span><span class="sxs-lookup"><span data-stu-id="3f6ac-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="3f6ac-111">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-111">0</span></span>|
|[<span data-ttu-id="3f6ac-112">char</span><span class="sxs-lookup"><span data-stu-id="3f6ac-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="3f6ac-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="3f6ac-113">'\0'</span></span>|
|[<span data-ttu-id="3f6ac-114">decimal</span><span class="sxs-lookup"><span data-stu-id="3f6ac-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="3f6ac-115">0.0M</span><span class="sxs-lookup"><span data-stu-id="3f6ac-115">0.0M</span></span>|
|[<span data-ttu-id="3f6ac-116">double</span><span class="sxs-lookup"><span data-stu-id="3f6ac-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="3f6ac-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="3f6ac-117">0.0D</span></span>|
|[<span data-ttu-id="3f6ac-118">enum</span><span class="sxs-lookup"><span data-stu-id="3f6ac-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="3f6ac-119">Der Wert, der vom Ausdruck (E)0 erzeugt wird, bei dem E der Enumerationsbezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="3f6ac-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="3f6ac-120">float</span><span class="sxs-lookup"><span data-stu-id="3f6ac-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="3f6ac-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="3f6ac-121">0.0F</span></span>|
|[<span data-ttu-id="3f6ac-122">int</span><span class="sxs-lookup"><span data-stu-id="3f6ac-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="3f6ac-123">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-123">0</span></span>|
|[<span data-ttu-id="3f6ac-124">long</span><span class="sxs-lookup"><span data-stu-id="3f6ac-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="3f6ac-125">0L</span><span class="sxs-lookup"><span data-stu-id="3f6ac-125">0L</span></span>|
|[<span data-ttu-id="3f6ac-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="3f6ac-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="3f6ac-127">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-127">0</span></span>|
|[<span data-ttu-id="3f6ac-128">short</span><span class="sxs-lookup"><span data-stu-id="3f6ac-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="3f6ac-129">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-129">0</span></span>|
|[<span data-ttu-id="3f6ac-130">struct</span><span class="sxs-lookup"><span data-stu-id="3f6ac-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="3f6ac-131">Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.</span><span class="sxs-lookup"><span data-stu-id="3f6ac-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="3f6ac-132">uint</span><span class="sxs-lookup"><span data-stu-id="3f6ac-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="3f6ac-133">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-133">0</span></span>|
|[<span data-ttu-id="3f6ac-134">ulong</span><span class="sxs-lookup"><span data-stu-id="3f6ac-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="3f6ac-135">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-135">0</span></span>|
|[<span data-ttu-id="3f6ac-136">ushort</span><span class="sxs-lookup"><span data-stu-id="3f6ac-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="3f6ac-137">0</span><span class="sxs-lookup"><span data-stu-id="3f6ac-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="3f6ac-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f6ac-138">See also</span></span>
 <span data-ttu-id="3f6ac-139">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f6ac-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3f6ac-140">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f6ac-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3f6ac-141">[Tabelle der Werttypen](../../../csharp/language-reference/keywords/value-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3f6ac-141">[Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md) </span></span>  
 <span data-ttu-id="3f6ac-142">[Werttypen](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="3f6ac-142">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="3f6ac-143">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="3f6ac-143">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="3f6ac-144">Referenztabellen für Typen</span><span class="sxs-lookup"><span data-stu-id="3f6ac-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

