---
title: Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie mit LINQ in C# Ergebnisse nach zusammenhängenden Schlüsseln gruppieren.
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659903"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="5e489-103">Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="5e489-103">Group results by contiguous keys</span></span>

<span data-ttu-id="5e489-104">Im folgende Beispiel wird veranschaulicht, wie Elemente in Segmenten gruppiert werden, die Untersequenzen von zusammenhängenden Schlüsseln darstellen.</span><span class="sxs-lookup"><span data-stu-id="5e489-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="5e489-105">Gehen wir beispielsweise von der folgenden Sequenz von Schlüssel-Wert-Paaren aus:</span><span class="sxs-lookup"><span data-stu-id="5e489-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>

|<span data-ttu-id="5e489-106">Taste</span><span class="sxs-lookup"><span data-stu-id="5e489-106">Key</span></span>|<span data-ttu-id="5e489-107">Wert</span><span class="sxs-lookup"><span data-stu-id="5e489-107">Value</span></span>|
|---------|-----------|
|<span data-ttu-id="5e489-108">A</span><span class="sxs-lookup"><span data-stu-id="5e489-108">A</span></span>|<span data-ttu-id="5e489-109">Wir</span><span class="sxs-lookup"><span data-stu-id="5e489-109">We</span></span>|
|<span data-ttu-id="5e489-110">A</span><span class="sxs-lookup"><span data-stu-id="5e489-110">A</span></span>|<span data-ttu-id="5e489-111">finden</span><span class="sxs-lookup"><span data-stu-id="5e489-111">think</span></span>|
|<span data-ttu-id="5e489-112">A</span><span class="sxs-lookup"><span data-stu-id="5e489-112">A</span></span>|<span data-ttu-id="5e489-113">dass</span><span class="sxs-lookup"><span data-stu-id="5e489-113">that</span></span>|
|<span data-ttu-id="5e489-114">B</span><span class="sxs-lookup"><span data-stu-id="5e489-114">B</span></span>|<span data-ttu-id="5e489-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="5e489-115">Linq</span></span>|
|<span data-ttu-id="5e489-116">C</span><span class="sxs-lookup"><span data-stu-id="5e489-116">C</span></span>|<span data-ttu-id="5e489-117">echt</span><span class="sxs-lookup"><span data-stu-id="5e489-117">is</span></span>|
|<span data-ttu-id="5e489-118">A</span><span class="sxs-lookup"><span data-stu-id="5e489-118">A</span></span>|<span data-ttu-id="5e489-119">cool</span><span class="sxs-lookup"><span data-stu-id="5e489-119">really</span></span>|
|<span data-ttu-id="5e489-120">B</span><span class="sxs-lookup"><span data-stu-id="5e489-120">B</span></span>|<span data-ttu-id="5e489-121">ist</span><span class="sxs-lookup"><span data-stu-id="5e489-121">cool</span></span>|
|<span data-ttu-id="5e489-122">B</span><span class="sxs-lookup"><span data-stu-id="5e489-122">B</span></span>|<span data-ttu-id="5e489-123">!</span><span class="sxs-lookup"><span data-stu-id="5e489-123">!</span></span>|

<span data-ttu-id="5e489-124">Die folgenden Gruppen werden in dieser Reihenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="5e489-124">The following groups will be created in this order:</span></span>

1. <span data-ttu-id="5e489-125">Wir, finden, dass</span><span class="sxs-lookup"><span data-stu-id="5e489-125">We, think, that</span></span>

2. <span data-ttu-id="5e489-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="5e489-126">Linq</span></span>

3. <span data-ttu-id="5e489-127">echt</span><span class="sxs-lookup"><span data-stu-id="5e489-127">is</span></span>

4. <span data-ttu-id="5e489-128">cool</span><span class="sxs-lookup"><span data-stu-id="5e489-128">really</span></span>

5. <span data-ttu-id="5e489-129">ist, !</span><span class="sxs-lookup"><span data-stu-id="5e489-129">cool, !</span></span>

<span data-ttu-id="5e489-130">Die Lösung wird als threadsichere Erweiterungsmethode implementiert, die die Ergebnisse streamend zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5e489-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="5e489-131">Das bedeutet, dass die Methode während dem Durchlaufen der Quellsequenz die Gruppen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="5e489-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="5e489-132">Im Gegensatz zu den Operatoren `group` und `orderby` kann die Methode mit dem Zurückgeben der Gruppen an den Aufrufer beginnen, bevor die ganze Sequenz gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="5e489-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>

<span data-ttu-id="5e489-133">Um Threadsicherheit zu gewährleisten, wird bei der Iteration der Gruppe eine Kopie der Gruppe oder des Abschnitts erstellt, wie in den Quellcodekommentaren erläutert.</span><span class="sxs-lookup"><span data-stu-id="5e489-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="5e489-134">Wenn die Quellsequenz eine lange Sequenz von zusammenhängenden Elementen enthält, löst die Common Language Runtime möglicherweise eine <xref:System.OutOfMemoryException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="5e489-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="5e489-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e489-135">Example</span></span>

<span data-ttu-id="5e489-136">Im folgenden Beispiel werden die Erweiterungsmethode und der Clientcode gezeigt, der sie verwendet:</span><span class="sxs-lookup"><span data-stu-id="5e489-136">The following example shows both the extension method and the client code that uses it:</span></span>

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

<span data-ttu-id="5e489-137">Um die Erweiterungsmethode in Ihrem Projekt zu verwenden, kopieren Sie die statische `MyExtensions`-Klasse in eine neue oder eine vorhandene Datenquelldatei, und fügen Sie, falls erforderlich, am Speicherort eine `using`-Direktive für den Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="5e489-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e489-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e489-138">See also</span></span>

- [<span data-ttu-id="5e489-139">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5e489-139">Language Integrated Query (LINQ)</span></span>](index.md)
