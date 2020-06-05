---
title: Mengenvorgänge
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: b6ff14794343ae7623ee38894cef02cfc0a2a597
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406819"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="51f04-102">Set-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51f04-102">Set Operations (Visual Basic)</span></span>

<span data-ttu-id="51f04-103">Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.</span><span class="sxs-lookup"><span data-stu-id="51f04-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>

<span data-ttu-id="51f04-104">Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="51f04-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="51f04-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="51f04-105">Methods</span></span>

|<span data-ttu-id="51f04-106">Methodenname</span><span class="sxs-lookup"><span data-stu-id="51f04-106">Method Name</span></span>|<span data-ttu-id="51f04-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51f04-107">Description</span></span>|<span data-ttu-id="51f04-108">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="51f04-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="51f04-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51f04-109">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="51f04-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="51f04-110">Distinct</span></span>|<span data-ttu-id="51f04-111">Entfernt doppelte Werte aus einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="51f04-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|<span data-ttu-id="51f04-112">Except</span><span class="sxs-lookup"><span data-stu-id="51f04-112">Except</span></span>|<span data-ttu-id="51f04-113">Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="51f04-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="51f04-114">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="51f04-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|<span data-ttu-id="51f04-115">Intersect</span><span class="sxs-lookup"><span data-stu-id="51f04-115">Intersect</span></span>|<span data-ttu-id="51f04-116">Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="51f04-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="51f04-117">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="51f04-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|<span data-ttu-id="51f04-118">Union</span><span class="sxs-lookup"><span data-stu-id="51f04-118">Union</span></span>|<span data-ttu-id="51f04-119">Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="51f04-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="51f04-120">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="51f04-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a><span data-ttu-id="51f04-121">Vergleich von Mengenvorgängen</span><span class="sxs-lookup"><span data-stu-id="51f04-121">Comparison of Set Operations</span></span>

### <a name="distinct"></a><span data-ttu-id="51f04-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="51f04-122">Distinct</span></span>

<span data-ttu-id="51f04-123">Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="51f04-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="51f04-124">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.</span><span class="sxs-lookup"><span data-stu-id="51f04-124">The returned sequence contains the unique elements from the input sequence.</span></span>

![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a><span data-ttu-id="51f04-126">Except</span><span class="sxs-lookup"><span data-stu-id="51f04-126">Except</span></span>

<span data-ttu-id="51f04-127">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51f04-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="51f04-128">Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.</span><span class="sxs-lookup"><span data-stu-id="51f04-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>

<span data-ttu-id="51f04-129">![Grafische Darstellung der Aktion Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except an.")</span><span class="sxs-lookup"><span data-stu-id="51f04-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>

### <a name="intersect"></a><span data-ttu-id="51f04-130">Intersect</span><span class="sxs-lookup"><span data-stu-id="51f04-130">Intersect</span></span>

<span data-ttu-id="51f04-131">Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51f04-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="51f04-132">Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51f04-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>

![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a><span data-ttu-id="51f04-134">Union</span><span class="sxs-lookup"><span data-stu-id="51f04-134">Union</span></span>

<span data-ttu-id="51f04-135">Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar.</span><span class="sxs-lookup"><span data-stu-id="51f04-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="51f04-136">Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.</span><span class="sxs-lookup"><span data-stu-id="51f04-136">The returned sequence contains the unique elements from both input sequences.</span></span>

![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a><span data-ttu-id="51f04-138">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="51f04-138">Query Expression Syntax Example</span></span>

<span data-ttu-id="51f04-139">Im folgenden Beispiel wird die- `Distinct` Klausel in einer LINQ-Abfrage verwendet, um die eindeutigen Zahlen aus einer Liste von ganzen Zahlen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="51f04-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a><span data-ttu-id="51f04-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51f04-140">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="51f04-141">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="51f04-141">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="51f04-142">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="51f04-142">Distinct Clause</span></span>](../../../language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="51f04-143">Vorgehensweise: kombinieren und Vergleichen von Zeichen folgen Auflistungen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51f04-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="51f04-144">Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51f04-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)
