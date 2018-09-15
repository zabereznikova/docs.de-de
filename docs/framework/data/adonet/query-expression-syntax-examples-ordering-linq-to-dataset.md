---
title: 'Beispiele für die Abfrageausdruckssyntax: Sortieren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: 1e3ee4372c1c2173cff0d93dfdf84c96c60130d4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45597458"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="b83ad-102">Beispiele für die Abfrageausdruckssyntax: Sortieren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b83ad-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="b83ad-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> und <xref:System.Linq.Enumerable.ThenByDescending%2A> und der Abfrageausdruckssyntax ein <xref:System.Data.DataSet> abfragen und die Reihenfolge der Ergebnisse festlegen können.</span><span class="sxs-lookup"><span data-stu-id="b83ad-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="b83ad-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="b83ad-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="b83ad-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="b83ad-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b83ad-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="b83ad-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="b83ad-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b83ad-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="b83ad-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="b83ad-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="b83ad-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b83ad-109">Example</span></span>  
 <span data-ttu-id="b83ad-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode verwendet, um eine nach Nachnamen geordnete Liste der Kontakte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b83ad-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="b83ad-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b83ad-111">Example</span></span>  
 <span data-ttu-id="b83ad-112">In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode verwendet, um eine nach der Länge der Nachnamen geordnete Liste der Kontakte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b83ad-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="b83ad-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="b83ad-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="b83ad-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b83ad-114">Example</span></span>  
 <span data-ttu-id="b83ad-115">In diesem Beispiel wird `orderby… descending` (`Order By … Descending`), das Äquivalent zur <xref:System.Linq.Enumerable.OrderByDescending%2A>-Methode, verwendet, um die Preisliste in absteigender Reihenfolge (höchster Preis zuerst, niedrigster zuletzt) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b83ad-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="b83ad-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="b83ad-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="b83ad-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b83ad-117">Example</span></span>  
 <span data-ttu-id="b83ad-118">In diesem Beispiel wird <xref:System.Linq.Enumerable.Reverse%2A> verwendet, um eine Liste der Aufträge zu erstellen, bei denen der `OrderDate`-Wert vor dem 20. Februar 2002 liegt.</span><span class="sxs-lookup"><span data-stu-id="b83ad-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="b83ad-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="b83ad-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="b83ad-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b83ad-120">Example</span></span>  
 <span data-ttu-id="b83ad-121">In diesem Beispiel wird `OrderBy… Descending`, das Äquivalent zur <xref:System.Linq.Enumerable.ThenByDescending%2A>-Methode, verwendet, um eine Liste von Produkten absteigend zuerst nach dem Namen und dann nach dem Listenpreis (höchster Preis zuerst, niedrigster Preis zuletzt) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="b83ad-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="b83ad-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b83ad-122">See Also</span></span>  
 [<span data-ttu-id="b83ad-123">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="b83ad-123">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="b83ad-124">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b83ad-124">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="b83ad-125">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="b83ad-125">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
