---
title: "Set-Vorgänge (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2e30c521635326afeea4aad9ce932d5206d06c6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="87049-102">Set-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87049-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="87049-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="87049-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="87049-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="87049-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87049-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="87049-105">Methods</span></span>  
  
|<span data-ttu-id="87049-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="87049-106">Method Name</span></span>|<span data-ttu-id="87049-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87049-107">Description</span></span>|<span data-ttu-id="87049-108">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="87049-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="87049-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87049-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="87049-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="87049-110">Distinct</span></span>|<span data-ttu-id="87049-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="87049-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="87049-112">Except</span><span class="sxs-lookup"><span data-stu-id="87049-112">Except</span></span>|<span data-ttu-id="87049-113">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="87049-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="87049-114">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="87049-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="87049-115">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="87049-115">Intersect</span></span>|<span data-ttu-id="87049-116">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="87049-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="87049-117">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="87049-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="87049-118">Union</span><span class="sxs-lookup"><span data-stu-id="87049-118">Union</span></span>|<span data-ttu-id="87049-119">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="87049-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="87049-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="87049-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="87049-121">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="87049-121">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="87049-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="87049-122">Distinct</span></span>  
 <span data-ttu-id="87049-123">Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="87049-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="87049-124">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="87049-124">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="87049-125">![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="87049-125">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="87049-126">Except</span><span class="sxs-lookup"><span data-stu-id="87049-126">Except</span></span>  
 <span data-ttu-id="87049-127">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87049-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87049-128">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="87049-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="87049-129">![Grafische Darstellung der Aktion Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="87049-129">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="87049-130">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="87049-130">Intersect</span></span>  
 <span data-ttu-id="87049-131">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="87049-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87049-132">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87049-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="87049-133">![Grafische Darstellung der Schnittmenge von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="87049-133">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="87049-134">Union</span><span class="sxs-lookup"><span data-stu-id="87049-134">Union</span></span>  
 <span data-ttu-id="87049-135">Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar.</span><span class="sxs-lookup"><span data-stu-id="87049-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="87049-136">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="87049-136">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="87049-137">![Grafische Darstellung der Verbindung von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="87049-137">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="87049-138">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="87049-138">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="87049-139">Im folgenden Beispiel wird die `Distinct` -Klausel in einer LINQ-Abfrage, um die eindeutigen Zahlen aus einer Liste von ganzen Zahlen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="87049-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 [!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="87049-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87049-140">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="87049-141">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="87049-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="87049-142">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="87049-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="87049-143">Vorgehensweise: kombinieren und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87049-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 [<span data-ttu-id="87049-144">Vorgehensweise: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87049-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
