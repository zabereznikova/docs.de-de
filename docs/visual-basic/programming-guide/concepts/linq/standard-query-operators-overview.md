---
title: Übersicht über Standardabfrageoperatoren
ms.date: 07/20/2015
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
ms.openlocfilehash: 7c229a576f6695282473352d6253d2c699c76604
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406780"
---
# <a name="standard-query-operators-overview-visual-basic"></a><span data-ttu-id="a83c3-102">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="a83c3-102">Standard Query Operators Overview (Visual Basic)</span></span>

<span data-ttu-id="a83c3-103">Die *Standardabfrageoperatoren* sind die Methoden, die das LINQ-Muster bilden.</span><span class="sxs-lookup"><span data-stu-id="a83c3-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="a83c3-104">Die meisten dieser Methoden bearbeiten Sequenzen. Eine Sequenz ist hier ein Objekt, dessen Typ die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="a83c3-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="a83c3-105">Die Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation, Sortierung und weitere bereit.</span><span class="sxs-lookup"><span data-stu-id="a83c3-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>

<span data-ttu-id="a83c3-106">Es gibt zwei Gruppen von LINQ-Standardabfrageoperatoren: Eine Gruppe funktioniert auf Grundlage von Objekten vom Typ <xref:System.Collections.Generic.IEnumerable%601>, die andere auf Grundlage von Objekten vom Typ <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="a83c3-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="a83c3-107">Die Methoden, die eine Gruppe bilden, sind statische Member der Klassen <xref:System.Linq.Enumerable> und <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="a83c3-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="a83c3-108">Sie werden als *Erweiterungsmethoden* des Typs, auf dessen Grundlage sie funktionieren, definiert.</span><span class="sxs-lookup"><span data-stu-id="a83c3-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="a83c3-109">Das bedeutet, dass Sie entweder mit der Syntax für statische Methoden oder für Instanzmethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a83c3-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>

<span data-ttu-id="a83c3-110">Darüber hinaus funktionieren mehrere Standardabfrageoperator-Methoden auf Grundlage anderer Typen als die, die auf <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> basieren.</span><span class="sxs-lookup"><span data-stu-id="a83c3-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="a83c3-111">Der Typ <xref:System.Linq.Enumerable> definiert zwei Methoden, die beide auf Grundlage von Objekten vom Typ <xref:System.Collections.IEnumerable> funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a83c3-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="a83c3-112">Die Methoden <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> und <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> ermöglichen es Ihnen, eine nicht parametrisierte oder nicht generische Auflistung im LINQ-Muster abfragen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="a83c3-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="a83c3-113">Dies erfolgt durch Erstellen einer stark typisierten Sammlung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="a83c3-113">They do this by creating a strongly typed collection of objects.</span></span> <span data-ttu-id="a83c3-114">Die Klasse <xref:System.Linq.Queryable> definiert zwei ähnliche Methoden, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> und <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, die auf Grundlage von Objekten vom Typ <xref:System.Linq.Queryable> funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a83c3-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>

<span data-ttu-id="a83c3-115">Die Standardabfrageoperatoren unterscheiden sich im Zeitpunkt ihrer Ausführung. Dies hängt davon ab, ob sie einen Singleton-Wert oder eine Sequenz von Werten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a83c3-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="a83c3-116">Die Methoden, die einen Singleton-Wert zurückgeben (z.B. <xref:System.Linq.Enumerable.Average%2A> und <xref:System.Linq.Enumerable.Sum%2A>), werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a83c3-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="a83c3-117">Methoden, die eine Sequenz zurückgeben, verzögern die Abfrageausführung und geben ein auflistbares Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="a83c3-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>

<span data-ttu-id="a83c3-118">Bei Methoden, die auf Grundlage von im Speicher enthaltenen Auflistungen funktionieren, d.h. die Methoden, die <xref:System.Collections.Generic.IEnumerable%601> erweitern, erfasst das zurückgegebene auflistbare Objekt die Argumente, die an die Methode übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a83c3-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="a83c3-119">Wenn dieses Objekt auflistbar ist, tritt die Logik des Abfrageoperators in Kraft, und die Abfrageergebnisse werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a83c3-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>

<span data-ttu-id="a83c3-120">Im Gegensatz dazu implementieren Methoden, die <xref:System.Linq.IQueryable%601> erweitern, kein Abfrageverhalten. Sie erstellen stattdessen eine Ausdrucksbaumstruktur, die die auszuführende Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="a83c3-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="a83c3-121">Die Verarbeitung von Abfragen wird vom Quellobjekt <xref:System.Linq.IQueryable%601> übernommen.</span><span class="sxs-lookup"><span data-stu-id="a83c3-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>

<span data-ttu-id="a83c3-122">Aufrufe der Abfragemethode können miteinander in eine Abfrage verkettet werden. Dadurch können Abfragen von beliebiger Komplexität sein.</span><span class="sxs-lookup"><span data-stu-id="a83c3-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>

<span data-ttu-id="a83c3-123">Im folgenden Codebeispiel wird veranschaulicht, wie die Standardabfrageoperatoren verwendet werden können, um Informationen zu einer Sequenz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a83c3-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>

```vb
Dim sentence = "the quick brown fox jumps over the lazy dog"
' Split the string into individual words to create a collection.
Dim words = sentence.Split(" "c)

Dim query = From word In words
            Group word.ToUpper() By word.Length Into gr = Group
            Order By Length _
            Select Length, GroupedWords = gr

Dim output As New System.Text.StringBuilder
For Each obj In query
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))
    For Each word As String In obj.GroupedWords
        output.AppendLine(word)
    Next
Next

'Display the output
MsgBox(output.ToString())

' This code example produces the following output:
'
' Words of length 3:
' THE
' FOX
' THE
' DOG
' Words of length 4:
' OVER
' LAZY
' Words of length 5:
' QUICK
' BROWN
' JUMPS
```

## <a name="query-expression-syntax"></a><span data-ttu-id="a83c3-124">Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="a83c3-124">Query Expression Syntax</span></span>

<span data-ttu-id="a83c3-125">Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax von C# und Visual Basic-Sprache, wodurch sie als Teil eines *query*-*Ausdrucks* aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="a83c3-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="a83c3-126">Weitere Informationen zu Standard Abfrage Operatoren mit dedizierten Schlüsselwörtern und ihrer entsprechenden Syntax finden Sie unter [Abfrage Ausdrucks Syntax für Standard Abfrage Operatoren (Visual Basic)](query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="a83c3-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (Visual Basic)](query-expression-syntax-for-standard-query-operators.md).</span></span>

## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="a83c3-127">Erweitern der Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="a83c3-127">Extending the Standard Query Operators</span></span>

<span data-ttu-id="a83c3-128">Sie können die Gruppe von Standardabfrageoperatoren durch Erstellen von domänenspezifischen Methoden erweitern, die für Ihre Zieldomäne oder -technologie geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="a83c3-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="a83c3-129">Sie können die Standardabfrageoperatoren auch mit ihren eigenen Implementierungen ersetzen, die zusätzliche Dienste bieten, z.B. Remote-Auswertung, Abfrageübersetzung und Optimierung.</span><span class="sxs-lookup"><span data-stu-id="a83c3-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="a83c3-130">Ein Beispiel finden Sie unter <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="a83c3-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>

## <a name="related-sections"></a><span data-ttu-id="a83c3-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a83c3-131">Related Sections</span></span>

<span data-ttu-id="a83c3-132">Über die folgenden Links gelangen Sie zu Themen, die Ihnen weitere Informationen über die verschiedenen Standardabfrageoperatoren basierend auf deren Funktionen bieten.</span><span class="sxs-lookup"><span data-stu-id="a83c3-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>

- [<span data-ttu-id="a83c3-133">Sortieren von Daten</span><span class="sxs-lookup"><span data-stu-id="a83c3-133">Sorting Data</span></span>](sorting-data.md)

- [<span data-ttu-id="a83c3-134">Set-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-134">Set Operations (Visual Basic)</span></span>](set-operations.md)

- [<span data-ttu-id="a83c3-135">Filtern von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-135">Filtering Data (Visual Basic)</span></span>](filtering-data.md)

- [<span data-ttu-id="a83c3-136">Quantifizierer-Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-136">Quantifier Operations (Visual Basic)</span></span>](quantifier-operations.md)

- [<span data-ttu-id="a83c3-137">Projektions Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-137">Projection Operations (Visual Basic)</span></span>](projection-operations.md)

- [<span data-ttu-id="a83c3-138">Partitionierung von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-138">Partitioning Data (Visual Basic)</span></span>](partitioning-data.md)

- [<span data-ttu-id="a83c3-139">Joinvorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-139">Join Operations (Visual Basic)</span></span>](join-operations.md)

- [<span data-ttu-id="a83c3-140">Gruppieren von Daten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-140">Grouping Data (Visual Basic)</span></span>](grouping-data.md)

- [<span data-ttu-id="a83c3-141">Generierungs Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-141">Generation Operations (Visual Basic)</span></span>](generation-operations.md)

- [<span data-ttu-id="a83c3-142">Gleichheits Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-142">Equality Operations (Visual Basic)</span></span>](equality-operations.md)

- [<span data-ttu-id="a83c3-143">Element Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-143">Element Operations (Visual Basic)</span></span>](element-operations.md)

- [<span data-ttu-id="a83c3-144">Datentypen werden umgerechnet (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-144">Converting Data Types (Visual Basic)</span></span>](converting-data-types.md)

- [<span data-ttu-id="a83c3-145">Verkettungs Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-145">Concatenation Operations (Visual Basic)</span></span>](concatenation-operations.md)

- [<span data-ttu-id="a83c3-146">Aggregations Vorgänge (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-146">Aggregation Operations (Visual Basic)</span></span>](aggregation-operations.md)

## <a name="see-also"></a><span data-ttu-id="a83c3-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a83c3-147">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="a83c3-148">Introduction to LINQ (Visual Basic) (Einführung in LINQ (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="a83c3-148">Introduction to LINQ (Visual Basic)</span></span>](introduction-to-linq.md)
- [<span data-ttu-id="a83c3-149">Abfrage Ausdrucks Syntax für Standard Abfrage Operatoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-149">Query Expression Syntax for Standard Query Operators (Visual Basic)</span></span>](query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="a83c3-150">Klassifizierung von Standard Abfrage Operatoren nach Ausführungs Arten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a83c3-150">Classification of Standard Query Operators by Manner of Execution (Visual Basic)</span></span>](classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="a83c3-151">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="a83c3-151">Extension Methods</span></span>](../../language-features/procedures/extension-methods.md)
