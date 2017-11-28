---
title: "Mengenvorgänge (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5b546d9df8752fd7afd6e0db4525bc923a74bbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="set-operations-c"></a><span data-ttu-id="614f3-102">Mengenvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="614f3-102">Set Operations (C#)</span></span>
<span data-ttu-id="614f3-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="614f3-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="614f3-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="614f3-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="614f3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="614f3-105">Methods</span></span>  
  
|<span data-ttu-id="614f3-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="614f3-106">Method Name</span></span>|<span data-ttu-id="614f3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="614f3-107">Description</span></span>|<span data-ttu-id="614f3-108">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="614f3-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="614f3-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="614f3-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="614f3-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="614f3-110">Distinct</span></span>|<span data-ttu-id="614f3-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="614f3-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="614f3-112">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="614f3-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="614f3-113">Except</span><span class="sxs-lookup"><span data-stu-id="614f3-113">Except</span></span>|<span data-ttu-id="614f3-114">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="614f3-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="614f3-115">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="614f3-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="614f3-116">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="614f3-116">Intersect</span></span>|<span data-ttu-id="614f3-117">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="614f3-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="614f3-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="614f3-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="614f3-119">Union</span><span class="sxs-lookup"><span data-stu-id="614f3-119">Union</span></span>|<span data-ttu-id="614f3-120">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="614f3-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="614f3-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="614f3-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="614f3-122">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="614f3-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="614f3-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="614f3-123">Distinct</span></span>  
 <span data-ttu-id="614f3-124">Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="614f3-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="614f3-125">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="614f3-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="614f3-126">![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="614f3-126">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="614f3-127">Except</span><span class="sxs-lookup"><span data-stu-id="614f3-127">Except</span></span>  
 <span data-ttu-id="614f3-128">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="614f3-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="614f3-129">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="614f3-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="614f3-130">![Grafische Darstellung der Aktion Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="614f3-130">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="614f3-131">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="614f3-131">Intersect</span></span>  
 <span data-ttu-id="614f3-132">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="614f3-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="614f3-133">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="614f3-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="614f3-134">![Grafische Darstellung der Schnittmenge von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="614f3-134">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="614f3-135">Union</span><span class="sxs-lookup"><span data-stu-id="614f3-135">Union</span></span>  
 <span data-ttu-id="614f3-136">Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar.</span><span class="sxs-lookup"><span data-stu-id="614f3-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="614f3-137">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="614f3-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="614f3-138">![Grafische Darstellung der Verbindung von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="614f3-138">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614f3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="614f3-139">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="614f3-140">Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="614f3-140">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="614f3-141">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="614f3-141">How to: Combine and Compare String Collections (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 [<span data-ttu-id="614f3-142">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="614f3-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
