---
title: "Set-Vorgänge (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2b9fd7ec122fff2601296ae3a46bb7607b2b32ef
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="fdfe7-102">Set-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdfe7-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="fdfe7-103">Mengenoperationen in LINQ finden Sie in der Query-Vorgänge, die ein Resultset erzeugen, die auf der Gegenwart oder Abwesenheit äquivalenter Elemente in demselben oder auf verschiedenen Sammlungen (oder Gruppen) basiert.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="fdfe7-104">Die Standardabfrageoperator-Methoden, die Set-Vorgänge ausführen, werden im folgenden Abschnitt aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdfe7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fdfe7-105">Methods</span></span>  
  
|<span data-ttu-id="fdfe7-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="fdfe7-106">Method Name</span></span>|<span data-ttu-id="fdfe7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fdfe7-107">Description</span></span>|<span data-ttu-id="fdfe7-108">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="fdfe7-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="fdfe7-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdfe7-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="fdfe7-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="fdfe7-110">Distinct</span></span>|<span data-ttu-id="fdfe7-111">Entfernt doppelte Werte aus einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<span data-ttu-id="fdfe7-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="fdfe7-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="fdfe7-114">Except</span><span class="sxs-lookup"><span data-stu-id="fdfe7-114">Except</span></span>|<span data-ttu-id="fdfe7-115">Gibt die Differenzmenge, also die Elemente einer Auflistung, die nicht in einer zweiten Auflistung erscheinen.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="fdfe7-116">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-116">Not applicable.</span></span>|<span data-ttu-id="fdfe7-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="fdfe7-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="fdfe7-119">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="fdfe7-119">Intersect</span></span>|<span data-ttu-id="fdfe7-120">Gibt die Schnittmenge, d.h. Elemente, die in jeder der beiden Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-120">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="fdfe7-121">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-121">Not applicable.</span></span>|<span data-ttu-id="fdfe7-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="fdfe7-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="fdfe7-124">Union</span><span class="sxs-lookup"><span data-stu-id="fdfe7-124">Union</span></span>|<span data-ttu-id="fdfe7-125">Gibt die Vereinigungsmenge, d.h. eindeutige Elemente, die in einem der beiden Auflistungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-125">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="fdfe7-126">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-126">Not applicable.</span></span>|<span data-ttu-id="fdfe7-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="fdfe7-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span></span>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="fdfe7-129">Vergleich der Set-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="fdfe7-129">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="fdfe7-130">Distinct</span><span class="sxs-lookup"><span data-stu-id="fdfe7-130">Distinct</span></span>  
 <span data-ttu-id="fdfe7-131">Die folgende Abbildung zeigt das Verhalten der <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>Methode auf eine Sequenz von Zeichen.</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-131">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> method on a sequence of characters.</span></span> <span data-ttu-id="fdfe7-132">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-132">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="fdfe7-133">![Grafik des Verhaltens von Distinct(). ] (../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="fdfe7-133">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="fdfe7-134">Except</span><span class="sxs-lookup"><span data-stu-id="fdfe7-134">Except</span></span>  
 <span data-ttu-id="fdfe7-135">Die folgende Abbildung zeigt das Verhalten der <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-135">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="fdfe7-136">Die zurückgegebene Sequenz enthält nur die Elemente der ersten Eingabesequenz, die nicht in der zweiten Eingabesequenz sind.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-136">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="fdfe7-137">![Grafik, die der Aktion EXCEPT(). ](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="fdfe7-137">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="fdfe7-138">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="fdfe7-138">Intersect</span></span>  
 <span data-ttu-id="fdfe7-139">Die folgende Abbildung zeigt das Verhalten der <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fdfe7-139">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="fdfe7-140">Die zurückgegebene Sequenz enthält die Elemente, die beiden Eingabesequenzen gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-140">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="fdfe7-141">![Grafik, die die Schnittmenge von zwei Sequenzen. ] (../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="fdfe7-141">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="fdfe7-142">Union</span><span class="sxs-lookup"><span data-stu-id="fdfe7-142">Union</span></span>  
 <span data-ttu-id="fdfe7-143">Die folgende Abbildung zeigt eine union-Operation für zwei Sequenzen von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-143">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="fdfe7-144">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-144">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="fdfe7-145">![Grafik, die die Vereinigung von zwei Sequenzen. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="fdfe7-145">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="fdfe7-146">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="fdfe7-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="fdfe7-147">Im folgenden Beispiel wird die `Distinct` -Klausel in einer LINQ-Abfrage, um die eindeutigen Zahlen aus einer Liste von ganzen Zahlen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdfe7-147">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 <span data-ttu-id="fdfe7-148">[!code-vb[CsLINQSetOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fdfe7-148">[!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfe7-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdfe7-149">See Also</span></span>  
 <span data-ttu-id="fdfe7-150"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="fdfe7-150"><xref:System.Linq></span></span>   
<span data-ttu-id="fdfe7-151"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="fdfe7-151"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="fdfe7-152"> [DISTINCT-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span><span class="sxs-lookup"><span data-stu-id="fdfe7-152"> [Distinct Clause](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span></span>  
<span data-ttu-id="fdfe7-153"> [Gewusst wie: kombinieren und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span><span class="sxs-lookup"><span data-stu-id="fdfe7-153"> [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span></span>  
<span data-ttu-id="fdfe7-154"> [Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span><span class="sxs-lookup"><span data-stu-id="fdfe7-154"> [How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span></span>
