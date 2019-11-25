---
title: Sortieren von Daten
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: f1d4d8afb9b6e176a7ac048ba3270ecafdce24c9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350585"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="b7ba3-102">Sorting Data (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7ba3-102">Sorting Data (Visual Basic)</span></span>

<span data-ttu-id="b7ba3-103">Bei einem Sortiervorgang werden die Elemente einer Sequenz auf Grundlage eines oder mehrerer Attribute sortiert.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="b7ba3-104">Mit dem ersten Sortierkriterium wird eine primäre Sortierung der Elemente ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="b7ba3-105">Sie können die Elemente innerhalb jeder primären Sortiergruppe sortieren, indem Sie ein zweites Sortierkriterium angeben.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>

<span data-ttu-id="b7ba3-106">Die folgende Abbildung zeigt das Ergebnis eines alphabetischen Sortiervorgangs bei einer Zeichensequenz.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>

![Grafik, die einen alphabetischen Sortiervorgang zeigt.](./media/sorting-data/alphabetical-sort-operation.png)

<span data-ttu-id="b7ba3-108">Die Methoden des Standardabfrageoperators, die Daten sortieren, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-108">The standard query operator methods that sort data are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="b7ba3-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="b7ba3-109">Methods</span></span>

|<span data-ttu-id="b7ba3-110">Methodenname</span><span class="sxs-lookup"><span data-stu-id="b7ba3-110">Method Name</span></span>|<span data-ttu-id="b7ba3-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7ba3-111">Description</span></span>|<span data-ttu-id="b7ba3-112">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="b7ba3-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="b7ba3-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7ba3-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="b7ba3-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="b7ba3-114">OrderBy</span></span>|<span data-ttu-id="b7ba3-115">Sortiert Werte in aufsteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="b7ba3-115">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b7ba3-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="b7ba3-116">OrderByDescending</span></span>|<span data-ttu-id="b7ba3-117">Sortiert Werte in absteigender Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="b7ba3-117">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b7ba3-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="b7ba3-118">ThenBy</span></span>|<span data-ttu-id="b7ba3-119">Führt eine sekundäre Sortierung in aufsteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="b7ba3-119">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b7ba3-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b7ba3-120">ThenByDescending</span></span>|<span data-ttu-id="b7ba3-121">Führt eine sekundäre Sortierung in absteigender Reihenfolge durch</span><span class="sxs-lookup"><span data-stu-id="b7ba3-121">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="b7ba3-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="b7ba3-122">Reverse</span></span>|<span data-ttu-id="b7ba3-123">Kehrt die Reihenfolge der Elemente in einer Auflistung um</span><span class="sxs-lookup"><span data-stu-id="b7ba3-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="b7ba3-124">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="b7ba3-125">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="b7ba3-125">Query Expression Syntax Examples</span></span>

### <a name="primary-sort-examples"></a><span data-ttu-id="b7ba3-126">Primäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="b7ba3-126">Primary Sort Examples</span></span>

#### <a name="primary-ascending-sort"></a><span data-ttu-id="b7ba3-127">Primäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="b7ba3-127">Primary Ascending Sort</span></span>

<span data-ttu-id="b7ba3-128">Im folgenden Beispiel wird veranschaulicht, wie man die `Order By`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in einem Array in aufsteigender Reihenfolge nach der Länge der Zeichenfolgen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-128">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a><span data-ttu-id="b7ba3-129">Primäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="b7ba3-129">Primary Descending Sort</span></span>

<span data-ttu-id="b7ba3-130">Im nächsten Beispiel wird veranschaulicht, wie man die `Order By Descending`-Klausel in einer LINQ-Abfrage verwendet, um die Zeichenfolgen in absteigender Reihenfolge nach ihrem ersten Buchstaben zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-130">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a><span data-ttu-id="b7ba3-131">Sekundäre Sortierungsbeispiele</span><span class="sxs-lookup"><span data-stu-id="b7ba3-131">Secondary Sort Examples</span></span>

#### <a name="secondary-ascending-sort"></a><span data-ttu-id="b7ba3-132">Sekundäre aufsteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="b7ba3-132">Secondary Ascending Sort</span></span>

<span data-ttu-id="b7ba3-133">Im folgenden Beispiel wird veranschaulicht, wie man die `Order By`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre und eine sekundäre Sortierung der Zeichenfolgen in einem Array durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-133">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="b7ba3-134">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert, beide Male in aufsteigender Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a><span data-ttu-id="b7ba3-135">Sekundäre absteigende Sortierung</span><span class="sxs-lookup"><span data-stu-id="b7ba3-135">Secondary Descending Sort</span></span>

<span data-ttu-id="b7ba3-136">Im nächsten Beispiel wird gezeigt, wie man die `Order By Descending`-Klausel in einer LINQ-Abfrage verwendet, um eine primäre Sortierung in aufsteigender Reihenfolge und eine sekundäre Sortierung in absteigender Reihenfolge durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-136">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="b7ba3-137">Die Zeichenfolgen werden primär nach der Länge und sekundär nach dem ersten Buchstaben der Zeichenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="b7ba3-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a><span data-ttu-id="b7ba3-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7ba3-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="b7ba3-139">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="b7ba3-139">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="b7ba3-140">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="b7ba3-140">Order By Clause</span></span>](../../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="b7ba3-141">Gewusst wie: Sortieren von Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="b7ba3-141">How to: Sort Query Results</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="b7ba3-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7ba3-142">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
