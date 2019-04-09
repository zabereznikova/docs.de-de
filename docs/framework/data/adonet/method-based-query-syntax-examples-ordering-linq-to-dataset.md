---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Sortieren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: 76bc4751a25e82a731e136f838d12b8d1c1d691f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119560"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="10b34-102">Beispiele für die methodenbasierte Abfragesyntax: Sortieren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="10b34-102">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="10b34-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.OrderBy%2A>-Methode, der <xref:System.Linq.Enumerable.Reverse%2A>-Methode und der <xref:System.Linq.Enumerable.ThenBy%2A>-Methode sowie der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen und die Reihenfolge der Ergebnisse festlegen können.</span><span class="sxs-lookup"><span data-stu-id="10b34-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="10b34-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="10b34-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="10b34-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="10b34-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="10b34-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="10b34-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="10b34-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie eine LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="10b34-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="10b34-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="10b34-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="10b34-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10b34-109">Example</span></span>  
 <span data-ttu-id="10b34-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode mit einem benutzerdefinierten Vergleich verwendet, um die Nachnamen ohne Berücksichtigung der Groß- oder Kleinschreibung zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="10b34-110">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="10b34-111">Reverse</span><span class="sxs-lookup"><span data-stu-id="10b34-111">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="10b34-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10b34-112">Example</span></span>  
 <span data-ttu-id="10b34-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Reverse%2A>-Methode verwendet, um eine Liste der Aufträge zu erstellen, bei denen der `OrderDate`-Wert vor dem 20. Februar 2002 liegt.</span><span class="sxs-lookup"><span data-stu-id="10b34-113">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="10b34-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="10b34-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="10b34-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10b34-115">Example</span></span>  
 <span data-ttu-id="10b34-116">In diesem Beispiel werden die Methoden <xref:System.Linq.Enumerable.OrderBy%2A> und <xref:System.Linq.Enumerable.ThenBy%2A> mit einem benutzerdefinierten Vergleich verwendet, um die Daten zuerst nach dem Listenpreis zu und dann nach dem Produktnamen (ohne Berücksichtigung der Groß- oder Kleinschreibung) zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="10b34-116">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="10b34-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10b34-117">See also</span></span>

- [<span data-ttu-id="10b34-118">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="10b34-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="10b34-119">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="10b34-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="10b34-120">Übersicht über Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="10b34-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="10b34-121">Standard Query Operators Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10b34-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
