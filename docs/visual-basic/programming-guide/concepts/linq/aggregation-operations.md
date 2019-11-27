---
title: Aggregationsoperationen
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 5c7f9344d379af2fed2a8f3d9f7c031c8ca00e8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345781"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="d85a2-102">Aggregations Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d85a2-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="d85a2-103">Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet.</span><span class="sxs-lookup"><span data-stu-id="d85a2-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="d85a2-104">Ein Beispiel für einen Aggregationsvorgang ist die Berechnung der durchschnittlichen Tagestemperatur aus den Tagestemperaturen eines Monats.</span><span class="sxs-lookup"><span data-stu-id="d85a2-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="d85a2-105">Die folgende Abbildung zeigt das Ergebnis von zwei verschiedenen Aggregationsvorgängen bei einer Zahlensequenz.</span><span class="sxs-lookup"><span data-stu-id="d85a2-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="d85a2-106">Der erste Vorgang zählt die Zahlen zusammen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-106">The first operation sums the numbers.</span></span> <span data-ttu-id="d85a2-107">Der zweite Vorgang gibt den höchsten Wert der Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="d85a2-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![Abbildung der LINQ-Aggregationsvorgänge](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="d85a2-109">Die Methoden des Standardabfrageoperators, die Aggregationsvorgänge ausführen, sind im folgenden Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d85a2-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d85a2-110">Methoden</span><span class="sxs-lookup"><span data-stu-id="d85a2-110">Methods</span></span>  
  
|<span data-ttu-id="d85a2-111">Methodenname</span><span class="sxs-lookup"><span data-stu-id="d85a2-111">Method Name</span></span>|<span data-ttu-id="d85a2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d85a2-112">Description</span></span>|<span data-ttu-id="d85a2-113">Syntax von Visual Basic-Abfrage Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="d85a2-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="d85a2-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d85a2-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="d85a2-115">Aggregat</span><span class="sxs-lookup"><span data-stu-id="d85a2-115">Aggregate</span></span>|<span data-ttu-id="d85a2-116">Führt einen benutzerdefinierten Aggregationsvorgang für die Werte einer Auflistung durch.</span><span class="sxs-lookup"><span data-stu-id="d85a2-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="d85a2-117">Nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="d85a2-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d85a2-118">Durchschnitt</span><span class="sxs-lookup"><span data-stu-id="d85a2-118">Average</span></span>|<span data-ttu-id="d85a2-119">Berechnet den Durchschnittswert einer Auflistung von Werten.</span><span class="sxs-lookup"><span data-stu-id="d85a2-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d85a2-120">Anzahl</span><span class="sxs-lookup"><span data-stu-id="d85a2-120">Count</span></span>|<span data-ttu-id="d85a2-121">Zählt die Elemente einer Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d85a2-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="d85a2-122">LongCount</span></span>|<span data-ttu-id="d85a2-123">Zählt die Elemente einer großen Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d85a2-124">Max</span><span class="sxs-lookup"><span data-stu-id="d85a2-124">Max</span></span>|<span data-ttu-id="d85a2-125">Bestimmt den Maximalwert einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d85a2-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d85a2-126">Min</span><span class="sxs-lookup"><span data-stu-id="d85a2-126">Min</span></span>|<span data-ttu-id="d85a2-127">Bestimmt den Minimalwert einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d85a2-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d85a2-128">Sum</span><span class="sxs-lookup"><span data-stu-id="d85a2-128">Sum</span></span>|<span data-ttu-id="d85a2-129">Berechnet die Summe der Werte einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d85a2-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="d85a2-130">Beispiele für die Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="d85a2-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="d85a2-131">Durchschnitt</span><span class="sxs-lookup"><span data-stu-id="d85a2-131">Average</span></span>  
 <span data-ttu-id="d85a2-132">Im folgenden Codebeispiel wird die `Aggregate Into Average`-Klausel in Visual Basic verwendet, um die Durchschnittstemperatur in einem Array von Zahlen zu berechnen, die Temperaturen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="d85a2-133">Anzahl</span><span class="sxs-lookup"><span data-stu-id="d85a2-133">Count</span></span>  
 <span data-ttu-id="d85a2-134">Im folgenden Codebeispiel wird die `Aggregate Into Count`-Klausel in Visual Basic verwendet, um die Anzahl von Werten in einem Array zu zählen, die größer oder gleich 80 sind.</span><span class="sxs-lookup"><span data-stu-id="d85a2-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="d85a2-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="d85a2-135">LongCount</span></span>  
 <span data-ttu-id="d85a2-136">Im folgenden Codebeispiel wird die `Aggregate Into LongCount`-Klausel verwendet, um die Anzahl von Werten in einem Array zu zählen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="d85a2-137">Max</span><span class="sxs-lookup"><span data-stu-id="d85a2-137">Max</span></span>  
 <span data-ttu-id="d85a2-138">Im folgenden Codebeispiel wird die `Aggregate Into Max`-Klausel verwendet, um die maximale Temperatur in einem Array von Zahlen zu berechnen, die Temperaturen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="d85a2-139">Min</span><span class="sxs-lookup"><span data-stu-id="d85a2-139">Min</span></span>  
 <span data-ttu-id="d85a2-140">Im folgenden Codebeispiel wird die `Aggregate Into Min`-Klausel verwendet, um die minimale Temperatur in einem Array von Zahlen zu berechnen, die Temperaturen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="d85a2-141">Sum</span><span class="sxs-lookup"><span data-stu-id="d85a2-141">Sum</span></span>  
 <span data-ttu-id="d85a2-142">Im folgenden Codebeispiel wird die `Aggregate Into Sum`-Klausel verwendet, um die Gesamtkosten eines Arrays von Werten zu berechnen, die Ausgaben darstellen.</span><span class="sxs-lookup"><span data-stu-id="d85a2-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d85a2-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d85a2-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="d85a2-144">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="d85a2-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="d85a2-145">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="d85a2-145">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="d85a2-146">Gewusst wie: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d85a2-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="d85a2-147">Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten</span><span class="sxs-lookup"><span data-stu-id="d85a2-147">How to: Count, Sum, or Average Data</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="d85a2-148">Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis</span><span class="sxs-lookup"><span data-stu-id="d85a2-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="d85a2-149">Gewusst wie: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d85a2-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="d85a2-150">Gewusst wie: Abfragen der Gesamtanzahl von Bytes in einem Ordner Satz (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d85a2-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
