---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Join (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: e061c5fea0a406169ba9de29d62192dbff6fb7f6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="5d641-102">Beispiele für die methodenbasierte Abfragesyntax: Join (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="5d641-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>
<span data-ttu-id="5d641-103">Das Verknüpfen (JOIN) ist eine wichtige Operation bei Abfragen von Daten aus Datenquellen, bei denen es untereinander keine navigierbaren Beziehungen, wie Tabellen in relationalen Datenbanken, gibt.</span><span class="sxs-lookup"><span data-stu-id="5d641-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="5d641-104">Bei einer JOIN-Operation für zwei Datenquellen werden Objekte in einer Datenquelle mit Objekten in der anderen Datenquelle, die über ein gemeinsames Attribut verfügen, miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="5d641-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="5d641-105">Weitere Informationen finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="5d641-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="5d641-106">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der <xref:System.Linq.Enumerable.Join%2A>-Methode und der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="5d641-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="5d641-107">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben, [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="5d641-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="5d641-108">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="5d641-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="5d641-109">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="5d641-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="5d641-110">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="5d641-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="5d641-111">Join</span><span class="sxs-lookup"><span data-stu-id="5d641-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="5d641-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d641-112">Example</span></span>  
 <span data-ttu-id="5d641-113">In diesen Beispiel werden die Tabellen `Contact` und `SalesOrderHeader` mittels einer JOIN-Operation miteinander verknüpft.</span><span class="sxs-lookup"><span data-stu-id="5d641-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="5d641-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d641-114">Example</span></span>  
 <span data-ttu-id="5d641-115">In diesem Beispiel werden die Tabellen `Contact` und `SalesOrderHeader` mittels einer JOIN-Operation miteinander verknüpft, und die Ergebnisse werden nach der Kontakt-ID gruppiert.</span><span class="sxs-lookup"><span data-stu-id="5d641-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="5d641-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d641-116">See Also</span></span>  
 [<span data-ttu-id="5d641-117">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="5d641-117">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="5d641-118">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5d641-118">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="5d641-119">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="5d641-119">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 [<span data-ttu-id="5d641-120">Join-Beispiele</span><span class="sxs-lookup"><span data-stu-id="5d641-120">Join Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=187357)  
 [<span data-ttu-id="5d641-121">DataSet-Beispiele</span><span class="sxs-lookup"><span data-stu-id="5d641-121">Dataset Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=187358)
