---
title: Mengenvorgänge (C#)
description: Hier erfahren Sie mehr über Mengenvorgänge und die Methoden von Standardabfrageoperatoren, die Mengenvorgänge in LINQ in C# ausführen.
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 8679f804adaaeada390206e3e1dd2a0711a2cbf6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195609"
---
# <a name="set-operations-c"></a><span data-ttu-id="b4c4c-103">Mengenvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="b4c4c-103">Set Operations (C#)</span></span>

<span data-ttu-id="b4c4c-104">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-104">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="b4c4c-105">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-105">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4c4c-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="b4c4c-106">Methods</span></span>  
  
|<span data-ttu-id="b4c4c-107">Methodenname</span><span class="sxs-lookup"><span data-stu-id="b4c4c-107">Method Name</span></span>|<span data-ttu-id="b4c4c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4c4c-108">Description</span></span>|<span data-ttu-id="b4c4c-109">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="b4c4c-109">C# Query Expression Syntax</span></span>|<span data-ttu-id="b4c4c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4c4c-110">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="b4c4c-111">Distinct</span><span class="sxs-lookup"><span data-stu-id="b4c4c-111">Distinct</span></span>|<span data-ttu-id="b4c4c-112">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="b4c4c-112">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="b4c4c-113">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-113">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b4c4c-114">Except</span><span class="sxs-lookup"><span data-stu-id="b4c4c-114">Except</span></span>|<span data-ttu-id="b4c4c-115">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="b4c4c-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="b4c4c-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b4c4c-117">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="b4c4c-117">Intersect</span></span>|<span data-ttu-id="b4c4c-118">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="b4c4c-118">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="b4c4c-119">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="b4c4c-120">Union</span><span class="sxs-lookup"><span data-stu-id="b4c4c-120">Union</span></span>|<span data-ttu-id="b4c4c-121">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="b4c4c-121">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="b4c4c-122">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="b4c4c-123">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="b4c4c-123">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="b4c4c-124">Distinct</span><span class="sxs-lookup"><span data-stu-id="b4c4c-124">Distinct</span></span>  

 <span data-ttu-id="b4c4c-125">Das folgende Beispiel veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-125">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="b4c4c-126">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-126">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="b4c4c-128">Except</span><span class="sxs-lookup"><span data-stu-id="b4c4c-128">Except</span></span>  

 <span data-ttu-id="b4c4c-129">Im folgenden Beispiel wird das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-129">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4c4c-130">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-130">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="b4c4c-131">![Grafische Darstellung der Aktion Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except an.")</span><span class="sxs-lookup"><span data-stu-id="b4c4c-131">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="b4c4c-132">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="b4c4c-132">Intersect</span></span>  

 <span data-ttu-id="b4c4c-133">Im folgenden Beispiel wird das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-133">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4c4c-134">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-134">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="b4c4c-136">Union</span><span class="sxs-lookup"><span data-stu-id="b4c4c-136">Union</span></span>  

 <span data-ttu-id="b4c4c-137">Das folgende Beispiel veranschaulicht einen Vereinigungsvorgang zweier Zeichensequenzen.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-137">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="b4c4c-138">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="b4c4c-138">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a><span data-ttu-id="b4c4c-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4c4c-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b4c4c-141">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="b4c4c-141">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="b4c4c-142">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b4c4c-142">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="b4c4c-143">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b4c4c-143">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
