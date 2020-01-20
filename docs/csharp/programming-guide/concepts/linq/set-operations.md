---
title: Mengenvorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 170316b36705eaed51a9a17f8f79333a29e8c315
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346509"
---
# <a name="set-operations-c"></a><span data-ttu-id="2fe15-102">Mengenvorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="2fe15-102">Set Operations (C#)</span></span>
<span data-ttu-id="2fe15-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="2fe15-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="2fe15-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2fe15-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fe15-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2fe15-105">Methods</span></span>  
  
|<span data-ttu-id="2fe15-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="2fe15-106">Method Name</span></span>|<span data-ttu-id="2fe15-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fe15-107">Description</span></span>|<span data-ttu-id="2fe15-108">C#-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="2fe15-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="2fe15-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fe15-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="2fe15-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="2fe15-110">Distinct</span></span>|<span data-ttu-id="2fe15-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="2fe15-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="2fe15-112">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2fe15-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2fe15-113">Except</span><span class="sxs-lookup"><span data-stu-id="2fe15-113">Except</span></span>|<span data-ttu-id="2fe15-114">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="2fe15-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="2fe15-115">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2fe15-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2fe15-116">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="2fe15-116">Intersect</span></span>|<span data-ttu-id="2fe15-117">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="2fe15-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="2fe15-118">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2fe15-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="2fe15-119">Union</span><span class="sxs-lookup"><span data-stu-id="2fe15-119">Union</span></span>|<span data-ttu-id="2fe15-120">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="2fe15-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="2fe15-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="2fe15-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="2fe15-122">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="2fe15-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="2fe15-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="2fe15-123">Distinct</span></span>  
 <span data-ttu-id="2fe15-124">Das folgende Beispiel veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="2fe15-124">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="2fe15-125">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="2fe15-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)  
 
 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="2fe15-127">Except</span><span class="sxs-lookup"><span data-stu-id="2fe15-127">Except</span></span>  
 <span data-ttu-id="2fe15-128">Im folgenden Beispiel wird das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2fe15-128">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2fe15-129">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="2fe15-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="2fe15-130">![Grafische Darstellung der Aktion Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except an.")</span><span class="sxs-lookup"><span data-stu-id="2fe15-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="2fe15-131">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="2fe15-131">Intersect</span></span>  
 <span data-ttu-id="2fe15-132">Im folgenden Beispiel wird das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2fe15-132">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2fe15-133">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fe15-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)  
 
[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="2fe15-135">Union</span><span class="sxs-lookup"><span data-stu-id="2fe15-135">Union</span></span>  
 <span data-ttu-id="2fe15-136">Das folgende Beispiel veranschaulicht einen Vereinigungsvorgang zweier Zeichensequenzen.</span><span class="sxs-lookup"><span data-stu-id="2fe15-136">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="2fe15-137">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="2fe15-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]
 
## <a name="see-also"></a><span data-ttu-id="2fe15-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fe15-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="2fe15-140">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="2fe15-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="2fe15-141">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2fe15-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="2fe15-142">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2fe15-142">How to find the set difference between two lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
