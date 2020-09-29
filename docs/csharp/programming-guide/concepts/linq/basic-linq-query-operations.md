---
title: Grundlegende LINQ-Abfragevorgänge (C#)
description: Informieren Sie sich über die LINQ-Abfrageausdrücke und einige der Vorgänge, die Sie bei einer Abfrage möglicherweise ausführen.
ms.date: 07/20/2015
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
ms.openlocfilehash: 9f5d39e396e9be3e633326d4034a89d874373d75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159292"
---
# <a name="basic-linq-query-operations-c"></a><span data-ttu-id="01f0c-103">Grundlegende LINQ-Abfragevorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="01f0c-103">Basic LINQ Query Operations (C#)</span></span>

<span data-ttu-id="01f0c-104">Dieses Thema gibt einen kurzen Überblick über LINQ-Abfrageausdrücke und einige der geläufigsten Vorgänge, die Sie in einer Abfrage durchführen können.</span><span class="sxs-lookup"><span data-stu-id="01f0c-104">This topic gives a brief introduction to LINQ query expressions and some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="01f0c-105">Ausführlichere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="01f0c-105">More detailed information is in the following topics:</span></span>  
  
 [<span data-ttu-id="01f0c-106">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="01f0c-106">LINQ Query Expressions</span></span>](../../../linq/index.md)  
  
 [<span data-ttu-id="01f0c-107">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="01f0c-107">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)  
  
 [<span data-ttu-id="01f0c-108">Exemplarische Vorgehensweise: Schreiben von Abfragen in C#</span><span class="sxs-lookup"><span data-stu-id="01f0c-108">Walkthrough: Writing Queries in C#</span></span>](./walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
> <span data-ttu-id="01f0c-109">Wenn Sie sich bereits mit einer Abfragesprache wie SQL oder XQuery auskennen, können Sie einen Großteil dieses Themas überspringen.</span><span class="sxs-lookup"><span data-stu-id="01f0c-109">If you already are familiar with a query language such as SQL or XQuery, you can skip most of this topic.</span></span> <span data-ttu-id="01f0c-110">Im nächsten Abschnitt erfahren Sie mehr über die `from`-Klausel und die Reihenfolge von Klauseln in einem LINQ-Abfrageausdruck.</span><span class="sxs-lookup"><span data-stu-id="01f0c-110">Read about the "`from` clause" in the next section to learn about the order of clauses in LINQ query expressions.</span></span>  
  
## <a name="obtaining-a-data-source"></a><span data-ttu-id="01f0c-111">Abrufen einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="01f0c-111">Obtaining a Data Source</span></span>  

 <span data-ttu-id="01f0c-112">Der erste Schritt für eine LINQ-Abfrage ist das Festlegen einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="01f0c-112">In a LINQ query, the first step is to specify the data source.</span></span> <span data-ttu-id="01f0c-113">Wie in den meisten Programmiersprachen muss eine Variable in C# vor ihrer Verwendung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-113">In C# as in most programming languages a variable must be declared before it can be used.</span></span> <span data-ttu-id="01f0c-114">In einer LINQ-Abfrage steht die `from`-Klausel an erster Stelle; sie führt die Datenquelle (`customers`) und die *Bereichsvariable* (`cust`) ein.</span><span class="sxs-lookup"><span data-stu-id="01f0c-114">In a LINQ query, the `from` clause comes first in order to introduce the data source (`customers`) and the *range variable* (`cust`).</span></span>  
  
 [!code-csharp[csLINQGettingStarted#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#23)]  
  
 <span data-ttu-id="01f0c-115">Die Bereichsvariable befindet sich wie die Iterationvariable in einer `foreach`-Schleife, mit dem Unterschied, dass in einem Abfrageausdruck keine Iterationen vorkommen.</span><span class="sxs-lookup"><span data-stu-id="01f0c-115">The range variable is like the iteration variable in a `foreach` loop except that no actual iteration occurs in a query expression.</span></span> <span data-ttu-id="01f0c-116">Wenn die Abfrage ausgeführt wird, fungiert die Bereichsvariable als Verweis auf jedes aufeinanderfolgende Element in `customers`.</span><span class="sxs-lookup"><span data-stu-id="01f0c-116">When the query is executed, the range variable will serve as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="01f0c-117">Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet.</span><span class="sxs-lookup"><span data-stu-id="01f0c-117">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="01f0c-118">Weitere Bereichsvariablen können mithilfe der `let`-Klausel eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-118">Additional range variables can be introduced by a `let` clause.</span></span> <span data-ttu-id="01f0c-119">Weitere Informationen finden Sie unter [let-Klausel](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-119">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01f0c-120">Die Bereichsvariable muss für nicht generische Datenquellen wie <xref:System.Collections.ArrayList> explizit typisiert sein.</span><span class="sxs-lookup"><span data-stu-id="01f0c-120">For non-generic data sources such as <xref:System.Collections.ArrayList>, the range variable must be explicitly typed.</span></span> <span data-ttu-id="01f0c-121">Weitere Informationen finden Sie unter [Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) und [from-Klausel](../../../language-reference/keywords/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-121">For more information, see [How to query an ArrayList with LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) and [from clause](../../../language-reference/keywords/from-clause.md).</span></span>  
  
## <a name="filtering"></a><span data-ttu-id="01f0c-122">Filtern</span><span class="sxs-lookup"><span data-stu-id="01f0c-122">Filtering</span></span>  

 <span data-ttu-id="01f0c-123">Die wahrscheinlich üblichste Abfrageoperation ist das Anwenden eines Filters in Form eines booleschen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="01f0c-123">Probably the most common query operation is to apply a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="01f0c-124">Das Filtern bewirkt, dass die Abfrage nur jene Elemente zurückgibt, für die der Ausdruck den Wert TRUE hat.</span><span class="sxs-lookup"><span data-stu-id="01f0c-124">The filter causes the query to return only those elements for which the expression is true.</span></span> <span data-ttu-id="01f0c-125">Das Ergebnis wird durch Verwendung der `where`-Klausel erzeugt.</span><span class="sxs-lookup"><span data-stu-id="01f0c-125">The result is produced by using the `where` clause.</span></span> <span data-ttu-id="01f0c-126">Faktisch gibt der Filter an, welche Elemente nicht in die Quellsequenz eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="01f0c-126">The filter in effect specifies which elements to exclude from the source sequence.</span></span> <span data-ttu-id="01f0c-127">In folgendem Beispiel werden nur die `customers` zurückgegeben, die eine Londoner Adresse haben.</span><span class="sxs-lookup"><span data-stu-id="01f0c-127">In the following example, only those `customers` who have an address in London are returned.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#24)]  
  
 <span data-ttu-id="01f0c-128">Sie können die geläufigen logischen C#-Operatoren `AND` und `OR` verwenden, um so viele Filterausdrücke wie benötigt in der `where`-Klausel anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-128">You can use the familiar C# logical `AND` and `OR` operators to apply as many filter expressions as necessary in the `where` clause.</span></span> <span data-ttu-id="01f0c-129">Wenn Sie z.B. nur Kunden aus „London“ zurückgeben möchten, deren Name „Devon“ ist, können Sie dazu `AND` verwenden wie in folgendem Codebeispiel:</span><span class="sxs-lookup"><span data-stu-id="01f0c-129">For example, to return only customers from "London" `AND` whose name is "Devon" you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#25)]  
  
 <span data-ttu-id="01f0c-130">Um Kunden aus London oder Paris zurückzugeben, verwenden Sie folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="01f0c-130">To return customers from London or Paris, you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#26)]  
  
 <span data-ttu-id="01f0c-131">Weitere Informationen finden Sie unter [where-Klausel](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-131">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="ordering"></a><span data-ttu-id="01f0c-132">Sortieren</span><span class="sxs-lookup"><span data-stu-id="01f0c-132">Ordering</span></span>  

 <span data-ttu-id="01f0c-133">Es kann häufig praktisch sein, die zurückgegebenen Daten zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="01f0c-133">Often it is convenient to sort the returned data.</span></span> <span data-ttu-id="01f0c-134">Die `orderby`-Klausel sortiert die Elemente in der zurückgegebenen Sequenz anhand des Standardcomparers für den zu sortierenden Typ.</span><span class="sxs-lookup"><span data-stu-id="01f0c-134">The `orderby` clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted.</span></span> <span data-ttu-id="01f0c-135">Die folgende Abfrage kann z.B. so erweitert werden, dass Sie die Ergebnisse nach der Eigenschaft `Name` sortiert.</span><span class="sxs-lookup"><span data-stu-id="01f0c-135">For example, the following query can be extended to sort the results based on the `Name` property.</span></span> <span data-ttu-id="01f0c-136">Der Standardcomparer nimmt eine Sortierung in alphabetischer Reihenfolge (A bis Z) vor, das es sich bei `Name` um eine Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="01f0c-136">Because `Name` is a string, the default comparer performs an alphabetical sort from A to Z.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#27)]  
  
 <span data-ttu-id="01f0c-137">Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `orderby…descending`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-137">To order the results in reverse order, from Z to A, use the `orderby…descending` clause.</span></span>  
  
 <span data-ttu-id="01f0c-138">Weitere Informationen finden Sie unter [orderby-Klausel](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-138">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
## <a name="grouping"></a><span data-ttu-id="01f0c-139">Gruppierung</span><span class="sxs-lookup"><span data-stu-id="01f0c-139">Grouping</span></span>  

 <span data-ttu-id="01f0c-140">Die `group`-Klausel ermöglicht Ihnen, die Ergebnisse auf Grundlage eines von Ihnen angegebenen Schlüssels zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="01f0c-140">The `group` clause enables you to group your results based on a key that you specify.</span></span> <span data-ttu-id="01f0c-141">Sie können z.B. angeben, dass die Ergebnisse nach `City` gruppiert werden sollen, sodass sich alle Kunden aus London oder Paris in einer einzelnen Gruppe befinden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-141">For example you could specify that the results should be grouped by the `City` so that all customers from London or Paris are in individual groups.</span></span> <span data-ttu-id="01f0c-142">In diesem Fall ist `cust.City` der Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="01f0c-142">In this case, `cust.City` is the key.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#28)]  
  
 <span data-ttu-id="01f0c-143">Wenn Sie eine Abfrage mit einer `group`-Klausel beenden, werden Ihre Ergebnisse in einer Liste aus Listen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="01f0c-143">When you end a query with a `group` clause, your results take the form of a list of lists.</span></span> <span data-ttu-id="01f0c-144">Jedes Element auf der Liste ist ein Objekt, dass über einen `Key`-Member und eine Liste von Elementen verfügt, die anhand dieses Schlüssels gruppiert wurden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-144">Each element in the list is an object that has a `Key` member and a list of elements that are grouped under that key.</span></span> <span data-ttu-id="01f0c-145">Wenn Sie eine Abfrage durchlaufen, die eine Sequenz von Gruppen erzeugt, müssen Sie eine geschachtelte `foreach`-Schleife verwenden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-145">When you iterate over a query that produces a sequence of groups, you must use a nested `foreach` loop.</span></span> <span data-ttu-id="01f0c-146">Die äußere Schleife durchläuft jede Gruppe, und die innere Schleife durchläuft alle Member jeder Gruppe.</span><span class="sxs-lookup"><span data-stu-id="01f0c-146">The outer loop iterates over each group, and the inner loop iterates over each group's members.</span></span>  
  
 <span data-ttu-id="01f0c-147">Wenn Sie auf die Ergebnisse eines Gruppenvorgangs verweisen müssen, könne Sie das Schlüsselwort `into` verwenden, um einen Bezeichner zu erstellen, der weiter abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="01f0c-147">If you must refer to the results of a group operation, you can use the `into` keyword to create an identifier that can be queried further.</span></span> <span data-ttu-id="01f0c-148">Die folgende Abfrage gibt nur die Gruppen zurück, die mehr als zwei Kunden enthalten:</span><span class="sxs-lookup"><span data-stu-id="01f0c-148">The following query returns only those groups that contain more than two customers:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#29)]  
  
 <span data-ttu-id="01f0c-149">Weitere Informationen finden Sie unter [group-Klausel](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-149">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="joining"></a><span data-ttu-id="01f0c-150">Verknüpfen</span><span class="sxs-lookup"><span data-stu-id="01f0c-150">Joining</span></span>  

 <span data-ttu-id="01f0c-151">Verknüpfungsvorgänge erstellen Verknüpfungen zwischen Sequenzen, die nicht explizit in der Datenquelle modelliert werden.</span><span class="sxs-lookup"><span data-stu-id="01f0c-151">Join operations create associations between sequences that are not explicitly modeled in the data sources.</span></span> <span data-ttu-id="01f0c-152">Sie können z.B. eine Verknüpfung erstellen, um alle Kunden und Händler mit demselben Standort ausfindig zu machen.</span><span class="sxs-lookup"><span data-stu-id="01f0c-152">For example you can perform a join to find all the customers and distributors who have the same location.</span></span> <span data-ttu-id="01f0c-153">In LINQ arbeitet die `join`-Klausel immer mit Objektsammlungen statt direkt mit Datenbanktabellen.</span><span class="sxs-lookup"><span data-stu-id="01f0c-153">In LINQ the `join` clause always works against object collections instead of database tables directly.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#36)]  
  
 <span data-ttu-id="01f0c-154">In L müssen Sie nicht `join` so häufig wie in SQL verwenden, da Fremdschlüssel in LINQ im Objektmodell als Eigenschaften dargestellt werden, die eine Elementauflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="01f0c-154">In LINQ, you do not have to use `join` as often as you do in SQL, because foreign keys in LINQ are represented in the object model as properties that hold a collection of items.</span></span> <span data-ttu-id="01f0c-155">Ein `Customer`-Objekt enthält z.B. eine Auflistung von `Order`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="01f0c-155">For example, a `Customer` object contains a collection of `Order` objects.</span></span> <span data-ttu-id="01f0c-156">Sie können auf die Bestellungen zugreifen, indem Sie Punktnotation statt einer Verknüpfung verwenden:</span><span class="sxs-lookup"><span data-stu-id="01f0c-156">Rather than performing a join, you access the orders by using dot notation:</span></span>  
  
```csharp
from order in Customer.Orders...  
```  
  
 <span data-ttu-id="01f0c-157">Weitere Informationen finden Sie unter [join-Klausel](../../../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-157">For more information, see [join clause](../../../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="selecting-projections"></a><span data-ttu-id="01f0c-158">Auswählen (Projektionen)</span><span class="sxs-lookup"><span data-stu-id="01f0c-158">Selecting (Projections)</span></span>  

 <span data-ttu-id="01f0c-159">Die `select`-Klausel erzeugt die Ergebnisse der Abfrage und gibt die „Form“ oder den Typ jedes zurückgegebenen Elements an.</span><span class="sxs-lookup"><span data-stu-id="01f0c-159">The `select` clause produces the results of the query and specifies the "shape" or type of each returned element.</span></span> <span data-ttu-id="01f0c-160">Sie können z.B. bestimmen, ob Ihre Ergebnisse aus vollständigen `Customer`-Objekte, aus lediglich einem Member, aus einer Teilmenge von Membern oder aus einem ganz anderen Ergebnistyp, der auf einer Berechnung oder einem neu erstellten Objekt basiert, bestehen sollen.</span><span class="sxs-lookup"><span data-stu-id="01f0c-160">For example, you can specify whether your results will consist of complete `Customer` objects, just one member, a subset of members, or some completely different result type based on a computation or new object creation.</span></span> <span data-ttu-id="01f0c-161">Wenn die `select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="01f0c-161">When the `select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span> <span data-ttu-id="01f0c-162">Das Verwenden von Projektionen zur Datentransformation ist eine leistungsfähige Funktion von LINQ-Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="01f0c-162">The use of projections to transform data is a powerful capability of LINQ query expressions.</span></span> <span data-ttu-id="01f0c-163">Weitere Informationen finden Sie unter [Datentransformationen mit LINQ (C#)](./data-transformations-with-linq.md) und [select-Klausel](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="01f0c-163">For more information, see [Data Transformations with LINQ (C#)](./data-transformations-with-linq.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f0c-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01f0c-164">See also</span></span>

- [<span data-ttu-id="01f0c-165">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="01f0c-165">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="01f0c-166">Exemplarische Vorgehensweise: Schreiben von Abfragen in C#</span><span class="sxs-lookup"><span data-stu-id="01f0c-166">Walkthrough: Writing Queries in C#</span></span>](./walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="01f0c-167">Abfrageschlüsselwörter (LINQ)</span><span class="sxs-lookup"><span data-stu-id="01f0c-167">Query Keywords (LINQ)</span></span>](../../../language-reference/keywords/query-keywords.md)
- [<span data-ttu-id="01f0c-168">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="01f0c-168">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
