---
title: Übersicht über Standardabfrageoperatoren (C#)
description: Die LINQ-Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation und Sortierung in C# bereit.
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 1ff98e47641dbe7a884b7d6c7758c1fe61b95091
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178774"
---
# <a name="standard-query-operators-overview-c"></a><span data-ttu-id="570b4-103">Übersicht über Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="570b4-103">Standard Query Operators Overview (C#)</span></span>

<span data-ttu-id="570b4-104">Die *Standardabfrageoperatoren* sind die Methoden, die das LINQ-Muster bilden.</span><span class="sxs-lookup"><span data-stu-id="570b4-104">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="570b4-105">Die meisten dieser Methoden bearbeiten Sequenzen. Eine Sequenz ist hier ein Objekt, dessen Typ die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle oder die <xref:System.Linq.IQueryable%601>-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="570b4-105">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="570b4-106">Die Standardabfrageoperatoren stellen Abfragefunktionen wie Filterung, Projektion, Aggregation, Sortierung und weitere bereit.</span><span class="sxs-lookup"><span data-stu-id="570b4-106">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="570b4-107">Es gibt zwei Gruppen von LINQ-Standardabfrageoperatoren: Eine Gruppe funktioniert auf Grundlage von Objekten vom Typ <xref:System.Collections.Generic.IEnumerable%601>, die andere auf Grundlage von Objekten vom Typ <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="570b4-107">There are two sets of LINQ standard query operators: one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601>, another that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="570b4-108">Die Methoden, die eine Gruppe bilden, sind statische Member der Klassen <xref:System.Linq.Enumerable> und <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="570b4-108">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="570b4-109">Sie werden als *Erweiterungsmethoden* des Typs, auf dessen Grundlage sie funktionieren, definiert.</span><span class="sxs-lookup"><span data-stu-id="570b4-109">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="570b4-110">Erweiterungsmethoden können entweder mit der Syntax für statische Methoden oder mit der für Instanzmethoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="570b4-110">Extension methods can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="570b4-111">Darüber hinaus funktionieren mehrere Standardabfrageoperator-Methoden auf Grundlage anderer Typen als die, die auf <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> basieren.</span><span class="sxs-lookup"><span data-stu-id="570b4-111">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="570b4-112">Der Typ <xref:System.Linq.Enumerable> definiert zwei Methoden, die beide auf Grundlage von Objekten vom Typ <xref:System.Collections.IEnumerable> funktionieren.</span><span class="sxs-lookup"><span data-stu-id="570b4-112">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="570b4-113">Die Methoden <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> und <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> ermöglichen es Ihnen, eine nicht parametrisierte oder nicht generische Auflistung im LINQ-Muster abfragen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="570b4-113">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="570b4-114">Dies erfolgt durch Erstellen einer stark typisierten Sammlung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="570b4-114">They do this by creating a strongly typed collection of objects.</span></span> <span data-ttu-id="570b4-115">Die Klasse <xref:System.Linq.Queryable> definiert zwei ähnliche Methoden, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> und <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, die auf Grundlage von Objekten vom Typ <xref:System.Linq.Queryable> funktionieren.</span><span class="sxs-lookup"><span data-stu-id="570b4-115">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="570b4-116">Die Standardabfrageoperatoren unterscheiden sich im Zeitpunkt ihrer Ausführung. Dies hängt davon ab, ob sie einen Singleton-Wert oder eine Sequenz von Werten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="570b4-116">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="570b4-117">Die Methoden, die einen Singleton-Wert zurückgeben (z.B. <xref:System.Linq.Enumerable.Average%2A> und <xref:System.Linq.Enumerable.Sum%2A>), werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="570b4-117">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="570b4-118">Methoden, die eine Sequenz zurückgeben, verzögern die Abfrageausführung und geben ein auflistbares Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="570b4-118">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="570b4-119">Bei Methoden, die auf In-Memory-Sammlungen angewendet werden, d. h. den Methoden, die <xref:System.Collections.Generic.IEnumerable%601> erweitern, erfasst das zurückgegebene auflistbare Objekt die Argumente, die an die Methode übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="570b4-119">For methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="570b4-120">Wenn dieses Objekt auflistbar ist, tritt die Logik des Abfrageoperators in Kraft, und die Abfrageergebnisse werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="570b4-120">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="570b4-121">Im Gegensatz dazu implementieren Methoden, die <xref:System.Linq.IQueryable%601> erweitern, kein Abfrageverhalten.</span><span class="sxs-lookup"><span data-stu-id="570b4-121">In contrast, methods that extend <xref:System.Linq.IQueryable%601> don't implement any querying behavior.</span></span> <span data-ttu-id="570b4-122">Sie erstellen eine Ausdrucksbaumstruktur, die die auszuführende Abfrage darstellt.</span><span class="sxs-lookup"><span data-stu-id="570b4-122">They build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="570b4-123">Die Verarbeitung von Abfragen wird vom Quellobjekt <xref:System.Linq.IQueryable%601> übernommen.</span><span class="sxs-lookup"><span data-stu-id="570b4-123">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="570b4-124">Aufrufe der Abfragemethode können miteinander in eine Abfrage verkettet werden. Dadurch können Abfragen von beliebiger Komplexität sein.</span><span class="sxs-lookup"><span data-stu-id="570b4-124">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="570b4-125">Im folgenden Codebeispiel wird veranschaulicht, wie die Standardabfrageoperatoren verwendet werden können, um Informationen zu einer Sequenz zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="570b4-125">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="570b4-126">Abfrageausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="570b4-126">Query Expression Syntax</span></span>  

 <span data-ttu-id="570b4-127">Einige der häufiger verwendeten Standardabfrageoperatoren verfügen über eine dedizierte Schlüsselwortsyntax von C# und Visual Basic-Sprache, wodurch sie als Teil eines *query*-*Ausdrucks* aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="570b4-127">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="570b4-128">Weitere Informationen über Standardabfrageoperatoren, die über dedizierte Schlüsselwörter und deren entsprechende Syntax verfügen, finden Sie unter [Query Expression Syntax for Standard Query Operators (C#) (Abfrageausdruckssyntax für Standardabfrageoperatoren (C#))](./query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="570b4-128">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (C#)](./query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="570b4-129">Erweitern der Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="570b4-129">Extending the Standard Query Operators</span></span>  

 <span data-ttu-id="570b4-130">Sie können die Gruppe von Standardabfrageoperatoren durch Erstellen von domänenspezifischen Methoden erweitern, die für Ihre Zieldomäne oder -technologie geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="570b4-130">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="570b4-131">Sie können die Standardabfrageoperatoren auch mit ihren eigenen Implementierungen ersetzen, die zusätzliche Dienste bieten, z.B. Remote-Auswertung, Abfrageübersetzung und Optimierung.</span><span class="sxs-lookup"><span data-stu-id="570b4-131">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="570b4-132">Ein Beispiel finden Sie unter <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="570b4-132">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="570b4-133">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="570b4-133">Related Sections</span></span>  

 <span data-ttu-id="570b4-134">Über die folgenden Links gelangen Sie zu Artikeln, die Ihnen weitere Informationen über die verschiedenen Standardabfrageoperatoren basierend auf deren Funktionen bieten.</span><span class="sxs-lookup"><span data-stu-id="570b4-134">The following links take you to articles that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="570b4-135">Sorting Data (C#) (Sortieren von Daten (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-135">Sorting Data (C#)</span></span>](./sorting-data.md)  
  
 [<span data-ttu-id="570b4-136">Set Operations (C#) (Set-Vorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-136">Set Operations (C#)</span></span>](./set-operations.md)  
  
 [<span data-ttu-id="570b4-137">Filtering Data (C#) (Filtern von Daten (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-137">Filtering Data (C#)</span></span>](./filtering-data.md)  
  
 [<span data-ttu-id="570b4-138">Quantifier Operations (C#) (Quantifizierer-Vorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-138">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)  
  
 [<span data-ttu-id="570b4-139">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-139">Projection Operations (C#)</span></span>](./projection-operations.md)  
  
 [<span data-ttu-id="570b4-140">Partitioning Data (C#) (Partitionieren von Daten (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-140">Partitioning Data (C#)</span></span>](./partitioning-data.md)  
  
 [<span data-ttu-id="570b4-141">Join Operations (C#) (Verknüpfungsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-141">Join Operations (C#)</span></span>](./join-operations.md)  
  
 [<span data-ttu-id="570b4-142">Grouping Data (C#) (Gruppieren von Daten (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-142">Grouping Data (C#)</span></span>](./grouping-data.md)  
  
 [<span data-ttu-id="570b4-143">Generation Operations (C#) (Generierungsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-143">Generation Operations (C#)</span></span>](./generation-operations.md)  
  
 [<span data-ttu-id="570b4-144">quality Operations (C#) (Gleichheitsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-144">Equality Operations (C#)</span></span>](./equality-operations.md)  
  
 [<span data-ttu-id="570b4-145">Element Operations (C#) (Elementvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-145">Element Operations (C#)</span></span>](./element-operations.md)  
  
 [<span data-ttu-id="570b4-146">Converting Data Types (C#) (Konvertieren von Datentypen (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-146">Converting Data Types (C#)</span></span>](./converting-data-types.md)  
  
 [<span data-ttu-id="570b4-147">Concatenation Operations (C#) (Verkettungsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-147">Concatenation Operations (C#)</span></span>](./concatenation-operations.md)  
  
 [<span data-ttu-id="570b4-148">Aggregation Operations (C#) (Aggregationsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-148">Aggregation Operations (C#)</span></span>](./aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="570b4-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="570b4-149">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="570b4-150">Introduction to LINQ Queries (C#) (Einführung in LINQ-Abfragen (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-150">Introduction to LINQ Queries (C#)</span></span>](./introduction-to-linq-queries.md)
- [<span data-ttu-id="570b4-151">Abfrageausdruckssyntax für Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="570b4-151">Query Expression Syntax for Standard Query Operators (C#)</span></span>](./query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="570b4-152">Classification of Standard Query Operators by Manner of Execution (C#) (Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (C#))</span><span class="sxs-lookup"><span data-stu-id="570b4-152">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](./classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="570b4-153">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="570b4-153">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
