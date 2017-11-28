---
title: "Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln"
description: "So gruppieren Sie Ergebnisse nach zusammenhängenden Schlüsseln"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: cdd06a6fad037291bbc5aa011b47bb668fa2f062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="349ca-104">Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="349ca-104">Group results by contiguous keys</span></span>

<span data-ttu-id="349ca-105">Im folgende Beispiel wird veranschaulicht, wie Elemente in Segmenten gruppiert werden, die Untersequenzen von zusammenhängenden Schlüsseln darstellen.</span><span class="sxs-lookup"><span data-stu-id="349ca-105">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="349ca-106">Gehen wir beispielsweise von der folgenden Sequenz von Schlüssel-Wert-Paaren aus:</span><span class="sxs-lookup"><span data-stu-id="349ca-106">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="349ca-107">Key</span><span class="sxs-lookup"><span data-stu-id="349ca-107">Key</span></span>|<span data-ttu-id="349ca-108">Wert</span><span class="sxs-lookup"><span data-stu-id="349ca-108">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="349ca-109">A</span><span class="sxs-lookup"><span data-stu-id="349ca-109">A</span></span>|<span data-ttu-id="349ca-110">Wir</span><span class="sxs-lookup"><span data-stu-id="349ca-110">We</span></span>|  
|<span data-ttu-id="349ca-111">A</span><span class="sxs-lookup"><span data-stu-id="349ca-111">A</span></span>|<span data-ttu-id="349ca-112">finden</span><span class="sxs-lookup"><span data-stu-id="349ca-112">think</span></span>|  
|<span data-ttu-id="349ca-113">A</span><span class="sxs-lookup"><span data-stu-id="349ca-113">A</span></span>|<span data-ttu-id="349ca-114">dass</span><span class="sxs-lookup"><span data-stu-id="349ca-114">that</span></span>|  
|<span data-ttu-id="349ca-115">B</span><span class="sxs-lookup"><span data-stu-id="349ca-115">B</span></span>|<span data-ttu-id="349ca-116">LINQ</span><span class="sxs-lookup"><span data-stu-id="349ca-116">Linq</span></span>|  
|<span data-ttu-id="349ca-117">A</span><span class="sxs-lookup"><span data-stu-id="349ca-117">C</span></span>|<span data-ttu-id="349ca-118">echt</span><span class="sxs-lookup"><span data-stu-id="349ca-118">is</span></span>|  
|<span data-ttu-id="349ca-119">A</span><span class="sxs-lookup"><span data-stu-id="349ca-119">A</span></span>|<span data-ttu-id="349ca-120">cool</span><span class="sxs-lookup"><span data-stu-id="349ca-120">really</span></span>|  
|<span data-ttu-id="349ca-121">B</span><span class="sxs-lookup"><span data-stu-id="349ca-121">B</span></span>|<span data-ttu-id="349ca-122">ist</span><span class="sxs-lookup"><span data-stu-id="349ca-122">cool</span></span>|  
|<span data-ttu-id="349ca-123">B</span><span class="sxs-lookup"><span data-stu-id="349ca-123">B</span></span>|<span data-ttu-id="349ca-124">!</span><span class="sxs-lookup"><span data-stu-id="349ca-124">!</span></span>|  
  
 <span data-ttu-id="349ca-125">Die folgenden Gruppen werden in dieser Reihenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="349ca-125">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="349ca-126">Wir, finden, dass</span><span class="sxs-lookup"><span data-stu-id="349ca-126">We, think, that</span></span>  
  
2.  <span data-ttu-id="349ca-127">LINQ</span><span class="sxs-lookup"><span data-stu-id="349ca-127">Linq</span></span>  
  
3.  <span data-ttu-id="349ca-128">echt</span><span class="sxs-lookup"><span data-stu-id="349ca-128">is</span></span>  
  
4.  <span data-ttu-id="349ca-129">cool</span><span class="sxs-lookup"><span data-stu-id="349ca-129">really</span></span>  
  
5.  <span data-ttu-id="349ca-130">ist, !</span><span class="sxs-lookup"><span data-stu-id="349ca-130">cool, !</span></span>  
  
 <span data-ttu-id="349ca-131">Die Lösung wird als threadsichere Erweiterungsmethode implementiert, die die Ergebnisse streamend zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="349ca-131">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="349ca-132">Das bedeutet, dass die Methode während dem Durchlaufen der Quellsequenz die Gruppen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="349ca-132">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="349ca-133">Im Gegensatz zu den Operatoren `group` und `orderby` kann die Methode mit dem Zurückgeben der Gruppen an den Aufrufer beginnen, bevor die ganze Sequenz gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="349ca-133">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="349ca-134">Um Threadsicherheit zu gewährleisten, wird bei der Iteration der Gruppe eine Kopie der Gruppe oder des Abschnitts erstellt, wie in den Quellcodekommentaren erläutert.</span><span class="sxs-lookup"><span data-stu-id="349ca-134">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="349ca-135">Wenn die Quellsequenz eine lange Sequenz von zusammenhängenden Elementen enthält, löst die Common Language Runtime möglicherweise eine <xref:System.OutOfMemoryException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="349ca-135">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="349ca-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="349ca-136">Example</span></span>  
 <span data-ttu-id="349ca-137">Im folgenden Beispiel werden die Erweiterungsmethode und der die Methode verwendende Clientcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="349ca-137">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="349ca-138">Um die Erweiterungsmethode in Ihrem Projekt zu verwenden, kopieren Sie die statische `MyExtensions`-Klasse in eine neue oder eine vorhandene Datenquelldatei, und fügen Sie, falls erforderlich, am Speicherort eine `using`-Direktive für den Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="349ca-138">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349ca-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="349ca-139">See also</span></span>  
 [<span data-ttu-id="349ca-140">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="349ca-140">LINQ Query Expressions</span></span>](index.md)  
 
