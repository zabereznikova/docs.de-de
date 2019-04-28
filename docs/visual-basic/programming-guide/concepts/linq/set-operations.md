---
title: Set-Vorgänge (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: 59ab09607462c762758e6a246ec218a92e01f5de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786867"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="889ee-102">Set-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="889ee-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="889ee-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="889ee-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="889ee-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="889ee-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="889ee-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="889ee-105">Methods</span></span>  
  
|<span data-ttu-id="889ee-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="889ee-106">Method Name</span></span>|<span data-ttu-id="889ee-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="889ee-107">Description</span></span>|<span data-ttu-id="889ee-108">Visual Basic-Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="889ee-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="889ee-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="889ee-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="889ee-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="889ee-110">Distinct</span></span>|<span data-ttu-id="889ee-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="889ee-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="889ee-112">Except</span><span class="sxs-lookup"><span data-stu-id="889ee-112">Except</span></span>|<span data-ttu-id="889ee-113">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="889ee-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="889ee-114">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="889ee-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="889ee-115">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="889ee-115">Intersect</span></span>|<span data-ttu-id="889ee-116">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="889ee-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="889ee-117">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="889ee-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="889ee-118">Union</span><span class="sxs-lookup"><span data-stu-id="889ee-118">Union</span></span>|<span data-ttu-id="889ee-119">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="889ee-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="889ee-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="889ee-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="889ee-121">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="889ee-121">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="889ee-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="889ee-122">Distinct</span></span>  
 <span data-ttu-id="889ee-123">Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="889ee-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="889ee-124">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="889ee-124">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="889ee-126">Except</span><span class="sxs-lookup"><span data-stu-id="889ee-126">Except</span></span>  
 <span data-ttu-id="889ee-127">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="889ee-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="889ee-128">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="889ee-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="889ee-129">![Grafische Darstellung der Aktion von Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except.")</span><span class="sxs-lookup"><span data-stu-id="889ee-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="889ee-130">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="889ee-130">Intersect</span></span>  
 <span data-ttu-id="889ee-131">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="889ee-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="889ee-132">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="889ee-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)    
### <a name="union"></a><span data-ttu-id="889ee-134">Union</span><span class="sxs-lookup"><span data-stu-id="889ee-134">Union</span></span>  
 <span data-ttu-id="889ee-135">Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar.</span><span class="sxs-lookup"><span data-stu-id="889ee-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="889ee-136">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="889ee-136">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)    
## <a name="query-expression-syntax-example"></a><span data-ttu-id="889ee-138">Beispiel für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="889ee-138">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="889ee-139">Im folgenden Beispiel wird die `Distinct` -Klausel in einer LINQ-Abfrage, um die eindeutigen Nummern aus einer Liste von ganzen Zahlen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="889ee-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 [!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="889ee-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="889ee-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="889ee-141">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="889ee-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="889ee-142">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="889ee-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="889ee-143">Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="889ee-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="889ee-144">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="889ee-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
