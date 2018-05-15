---
title: Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln
description: So gruppieren Sie Ergebnisse nach zusammenhängenden Schlüsseln
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: a8d6ac133932a12154d5b23454065144c7652067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="6c921-103">Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="6c921-103">Group results by contiguous keys</span></span>

<span data-ttu-id="6c921-104">Im folgende Beispiel wird veranschaulicht, wie Elemente in Segmenten gruppiert werden, die Untersequenzen von zusammenhängenden Schlüsseln darstellen.</span><span class="sxs-lookup"><span data-stu-id="6c921-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="6c921-105">Gehen wir beispielsweise von der folgenden Sequenz von Schlüssel-Wert-Paaren aus:</span><span class="sxs-lookup"><span data-stu-id="6c921-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>  
  
|<span data-ttu-id="6c921-106">Key</span><span class="sxs-lookup"><span data-stu-id="6c921-106">Key</span></span>|<span data-ttu-id="6c921-107">Wert</span><span class="sxs-lookup"><span data-stu-id="6c921-107">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="6c921-108">A</span><span class="sxs-lookup"><span data-stu-id="6c921-108">A</span></span>|<span data-ttu-id="6c921-109">Wir</span><span class="sxs-lookup"><span data-stu-id="6c921-109">We</span></span>|  
|<span data-ttu-id="6c921-110">A</span><span class="sxs-lookup"><span data-stu-id="6c921-110">A</span></span>|<span data-ttu-id="6c921-111">finden</span><span class="sxs-lookup"><span data-stu-id="6c921-111">think</span></span>|  
|<span data-ttu-id="6c921-112">A</span><span class="sxs-lookup"><span data-stu-id="6c921-112">A</span></span>|<span data-ttu-id="6c921-113">dass</span><span class="sxs-lookup"><span data-stu-id="6c921-113">that</span></span>|  
|<span data-ttu-id="6c921-114">B</span><span class="sxs-lookup"><span data-stu-id="6c921-114">B</span></span>|<span data-ttu-id="6c921-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="6c921-115">Linq</span></span>|  
|<span data-ttu-id="6c921-116">C</span><span class="sxs-lookup"><span data-stu-id="6c921-116">C</span></span>|<span data-ttu-id="6c921-117">echt</span><span class="sxs-lookup"><span data-stu-id="6c921-117">is</span></span>|  
|<span data-ttu-id="6c921-118">A</span><span class="sxs-lookup"><span data-stu-id="6c921-118">A</span></span>|<span data-ttu-id="6c921-119">cool</span><span class="sxs-lookup"><span data-stu-id="6c921-119">really</span></span>|  
|<span data-ttu-id="6c921-120">B</span><span class="sxs-lookup"><span data-stu-id="6c921-120">B</span></span>|<span data-ttu-id="6c921-121">ist</span><span class="sxs-lookup"><span data-stu-id="6c921-121">cool</span></span>|  
|<span data-ttu-id="6c921-122">B</span><span class="sxs-lookup"><span data-stu-id="6c921-122">B</span></span>|<span data-ttu-id="6c921-123">!</span><span class="sxs-lookup"><span data-stu-id="6c921-123">!</span></span>|  
  
 <span data-ttu-id="6c921-124">Die folgenden Gruppen werden in dieser Reihenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="6c921-124">The following groups will be created in this order:</span></span>  
  
1.  <span data-ttu-id="6c921-125">Wir, finden, dass</span><span class="sxs-lookup"><span data-stu-id="6c921-125">We, think, that</span></span>  
  
2.  <span data-ttu-id="6c921-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="6c921-126">Linq</span></span>  
  
3.  <span data-ttu-id="6c921-127">echt</span><span class="sxs-lookup"><span data-stu-id="6c921-127">is</span></span>  
  
4.  <span data-ttu-id="6c921-128">cool</span><span class="sxs-lookup"><span data-stu-id="6c921-128">really</span></span>  
  
5.  <span data-ttu-id="6c921-129">ist, !</span><span class="sxs-lookup"><span data-stu-id="6c921-129">cool, !</span></span>  
  
 <span data-ttu-id="6c921-130">Die Lösung wird als threadsichere Erweiterungsmethode implementiert, die die Ergebnisse streamend zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6c921-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="6c921-131">Das bedeutet, dass die Methode während dem Durchlaufen der Quellsequenz die Gruppen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="6c921-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="6c921-132">Im Gegensatz zu den Operatoren `group` und `orderby` kann die Methode mit dem Zurückgeben der Gruppen an den Aufrufer beginnen, bevor die ganze Sequenz gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="6c921-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>  
  
 <span data-ttu-id="6c921-133">Um Threadsicherheit zu gewährleisten, wird bei der Iteration der Gruppe eine Kopie der Gruppe oder des Abschnitts erstellt, wie in den Quellcodekommentaren erläutert.</span><span class="sxs-lookup"><span data-stu-id="6c921-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="6c921-134">Wenn die Quellsequenz eine lange Sequenz von zusammenhängenden Elementen enthält, löst die Common Language Runtime möglicherweise eine <xref:System.OutOfMemoryException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="6c921-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c921-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c921-135">Example</span></span>  
 <span data-ttu-id="6c921-136">Im folgenden Beispiel werden die Erweiterungsmethode und der die Methode verwendende Clientcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c921-136">The following example shows both the extension method and the client code that uses it.</span></span>  
  
 [!code-csharp[cscsrefContiguousGroups#1](../../../samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]  
  
 <span data-ttu-id="6c921-137">Um die Erweiterungsmethode in Ihrem Projekt zu verwenden, kopieren Sie die statische `MyExtensions`-Klasse in eine neue oder eine vorhandene Datenquelldatei, und fügen Sie, falls erforderlich, am Speicherort eine `using`-Direktive für den Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="6c921-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c921-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c921-138">See also</span></span>  
 [<span data-ttu-id="6c921-139">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="6c921-139">LINQ Query Expressions</span></span>](index.md)  
 
