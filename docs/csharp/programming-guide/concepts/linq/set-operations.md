---
title: Mengenvorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 7fd61e17c37c3d9056159cf4ec3ccfafa2ceb871
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140927"
---
# <a name="set-operations-c"></a><span data-ttu-id="820fb-102">Mengenvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="820fb-102">Set Operations (C#)</span></span>
<span data-ttu-id="820fb-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="820fb-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="820fb-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="820fb-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="820fb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="820fb-105">Methods</span></span>  
  
|<span data-ttu-id="820fb-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="820fb-106">Method Name</span></span>|<span data-ttu-id="820fb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="820fb-107">Description</span></span>|<span data-ttu-id="820fb-108">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="820fb-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="820fb-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="820fb-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="820fb-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="820fb-110">Distinct</span></span>|<span data-ttu-id="820fb-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="820fb-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="820fb-112">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="820fb-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="820fb-113">Except</span><span class="sxs-lookup"><span data-stu-id="820fb-113">Except</span></span>|<span data-ttu-id="820fb-114">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="820fb-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="820fb-115">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="820fb-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="820fb-116">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="820fb-116">Intersect</span></span>|<span data-ttu-id="820fb-117">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="820fb-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="820fb-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="820fb-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="820fb-119">Union</span><span class="sxs-lookup"><span data-stu-id="820fb-119">Union</span></span>|<span data-ttu-id="820fb-120">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="820fb-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="820fb-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="820fb-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="820fb-122">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="820fb-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="820fb-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="820fb-123">Distinct</span></span>  
 <span data-ttu-id="820fb-124">Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="820fb-124">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="820fb-125">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="820fb-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="820fb-127">Except</span><span class="sxs-lookup"><span data-stu-id="820fb-127">Except</span></span>  
 <span data-ttu-id="820fb-128">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="820fb-128">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="820fb-129">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="820fb-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="820fb-130">![Grafische Darstellung der Aktion Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except an.")</span><span class="sxs-lookup"><span data-stu-id="820fb-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="820fb-131">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="820fb-131">Intersect</span></span>  
 <span data-ttu-id="820fb-132">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="820fb-132">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="820fb-133">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="820fb-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a><span data-ttu-id="820fb-135">Union</span><span class="sxs-lookup"><span data-stu-id="820fb-135">Union</span></span>  
 <span data-ttu-id="820fb-136">Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar.</span><span class="sxs-lookup"><span data-stu-id="820fb-136">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="820fb-137">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="820fb-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a><span data-ttu-id="820fb-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="820fb-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="820fb-140">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="820fb-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="820fb-141">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="820fb-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="820fb-142">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="820fb-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
