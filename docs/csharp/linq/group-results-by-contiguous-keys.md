---
title: Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie mit LINQ in C# Ergebnisse nach zusammenhängenden Schlüsseln gruppieren.
ms.date: 12/1/2016
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: 8ad08d861e2d0f5ee0f8a2eceeb8d82a9aa2a5a6
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404761"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="c524e-103">Gruppieren von Ergebnissen nach zusammenhängenden Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="c524e-103">Group results by contiguous keys</span></span>

<span data-ttu-id="c524e-104">Im folgende Beispiel wird veranschaulicht, wie Elemente in Segmenten gruppiert werden, die Untersequenzen von zusammenhängenden Schlüsseln darstellen.</span><span class="sxs-lookup"><span data-stu-id="c524e-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="c524e-105">Gehen wir beispielsweise von der folgenden Sequenz von Schlüssel-Wert-Paaren aus:</span><span class="sxs-lookup"><span data-stu-id="c524e-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>

|<span data-ttu-id="c524e-106">Key</span><span class="sxs-lookup"><span data-stu-id="c524e-106">Key</span></span>|<span data-ttu-id="c524e-107">Wert</span><span class="sxs-lookup"><span data-stu-id="c524e-107">Value</span></span>|
|---------|-----------|
|<span data-ttu-id="c524e-108">A</span><span class="sxs-lookup"><span data-stu-id="c524e-108">A</span></span>|<span data-ttu-id="c524e-109">Wir</span><span class="sxs-lookup"><span data-stu-id="c524e-109">We</span></span>|
|<span data-ttu-id="c524e-110">A</span><span class="sxs-lookup"><span data-stu-id="c524e-110">A</span></span>|<span data-ttu-id="c524e-111">finden</span><span class="sxs-lookup"><span data-stu-id="c524e-111">think</span></span>|
|<span data-ttu-id="c524e-112">A</span><span class="sxs-lookup"><span data-stu-id="c524e-112">A</span></span>|<span data-ttu-id="c524e-113">dass</span><span class="sxs-lookup"><span data-stu-id="c524e-113">that</span></span>|
|<span data-ttu-id="c524e-114">B</span><span class="sxs-lookup"><span data-stu-id="c524e-114">B</span></span>|<span data-ttu-id="c524e-115">LINQ</span><span class="sxs-lookup"><span data-stu-id="c524e-115">Linq</span></span>|
|<span data-ttu-id="c524e-116">C</span><span class="sxs-lookup"><span data-stu-id="c524e-116">C</span></span>|<span data-ttu-id="c524e-117">echt</span><span class="sxs-lookup"><span data-stu-id="c524e-117">is</span></span>|
|<span data-ttu-id="c524e-118">A</span><span class="sxs-lookup"><span data-stu-id="c524e-118">A</span></span>|<span data-ttu-id="c524e-119">cool</span><span class="sxs-lookup"><span data-stu-id="c524e-119">really</span></span>|
|<span data-ttu-id="c524e-120">B</span><span class="sxs-lookup"><span data-stu-id="c524e-120">B</span></span>|<span data-ttu-id="c524e-121">ist</span><span class="sxs-lookup"><span data-stu-id="c524e-121">cool</span></span>|
|<span data-ttu-id="c524e-122">B</span><span class="sxs-lookup"><span data-stu-id="c524e-122">B</span></span>|<span data-ttu-id="c524e-123">!</span><span class="sxs-lookup"><span data-stu-id="c524e-123">!</span></span>|

<span data-ttu-id="c524e-124">Die folgenden Gruppen werden in dieser Reihenfolge erstellt:</span><span class="sxs-lookup"><span data-stu-id="c524e-124">The following groups will be created in this order:</span></span>

1. <span data-ttu-id="c524e-125">Wir, finden, dass</span><span class="sxs-lookup"><span data-stu-id="c524e-125">We, think, that</span></span>

2. <span data-ttu-id="c524e-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="c524e-126">Linq</span></span>

3. <span data-ttu-id="c524e-127">echt</span><span class="sxs-lookup"><span data-stu-id="c524e-127">is</span></span>

4. <span data-ttu-id="c524e-128">cool</span><span class="sxs-lookup"><span data-stu-id="c524e-128">really</span></span>

5. <span data-ttu-id="c524e-129">ist, !</span><span class="sxs-lookup"><span data-stu-id="c524e-129">cool, !</span></span>

<span data-ttu-id="c524e-130">Die Lösung wird als threadsichere Erweiterungsmethode implementiert, die die Ergebnisse streamend zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c524e-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="c524e-131">Das bedeutet, dass die Methode während dem Durchlaufen der Quellsequenz die Gruppen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c524e-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="c524e-132">Im Gegensatz zu den Operatoren `group` und `orderby` kann die Methode mit dem Zurückgeben der Gruppen an den Aufrufer beginnen, bevor die ganze Sequenz gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="c524e-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>

<span data-ttu-id="c524e-133">Um Threadsicherheit zu gewährleisten, wird bei der Iteration der Gruppe eine Kopie der Gruppe oder des Abschnitts erstellt, wie in den Quellcodekommentaren erläutert.</span><span class="sxs-lookup"><span data-stu-id="c524e-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="c524e-134">Wenn die Quellsequenz eine lange Sequenz von zusammenhängenden Elementen enthält, löst die Common Language Runtime möglicherweise eine <xref:System.OutOfMemoryException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="c524e-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="c524e-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c524e-135">Example</span></span>

<span data-ttu-id="c524e-136">Im folgenden Beispiel werden die Erweiterungsmethode und der Clientcode gezeigt, der sie verwendet:</span><span class="sxs-lookup"><span data-stu-id="c524e-136">The following example shows both the extension method and the client code that uses it:</span></span>

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

<span data-ttu-id="c524e-137">Um die Erweiterungsmethode in Ihrem Projekt zu verwenden, kopieren Sie die statische `MyExtensions`-Klasse in eine neue oder eine vorhandene Datenquelldatei, und fügen Sie, falls erforderlich, am Speicherort eine `using`-Direktive für den Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="c524e-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>

## <a name="see-also"></a><span data-ttu-id="c524e-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c524e-138">See also</span></span>

[<span data-ttu-id="c524e-139">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="c524e-139">Language Integrated Query (LINQ)</span></span>](index.md)