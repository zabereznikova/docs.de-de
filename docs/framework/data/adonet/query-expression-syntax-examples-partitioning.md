---
title: 'Beispiele für die Abfrageausdruckssyntax: Partitionierung (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: beb5f361-1ac8-44fb-afa1-2aacea15f166
ms.openlocfilehash: 456e4289af2c71ee2ef96f48939dc9f7b70c6bc0
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46518663"
---
# <a name="query-expression-syntax-examples-partitioning-linq-to-dataset"></a><span data-ttu-id="b93b2-102">Beispiele für die Abfrageausdruckssyntax: Partitionierung (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b93b2-102">Query Expression Syntax Examples: Partitioning (LINQ to DataSet)</span></span>
<span data-ttu-id="b93b2-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> und der Abfrageausdruckssyntax ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="b93b2-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="b93b2-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="b93b2-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="b93b2-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="b93b2-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b93b2-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="b93b2-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="b93b2-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b93b2-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="b93b2-108">Skip</span><span class="sxs-lookup"><span data-stu-id="b93b2-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="b93b2-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b93b2-109">Example</span></span>  
 <span data-ttu-id="b93b2-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Skip%2A>-Methode verwendet, um, mit Ausnahme der ersten beiden Adressen, alle Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b93b2-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="b93b2-111">Take</span><span class="sxs-lookup"><span data-stu-id="b93b2-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="b93b2-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b93b2-112">Example</span></span>  
 <span data-ttu-id="b93b2-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Take%2A>-Methode verwendet, um die ersten drei Adressen in Seattle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b93b2-113">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="b93b2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b93b2-114">See Also</span></span>  
 [<span data-ttu-id="b93b2-115">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="b93b2-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="b93b2-116">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b93b2-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="b93b2-117">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="b93b2-117">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
