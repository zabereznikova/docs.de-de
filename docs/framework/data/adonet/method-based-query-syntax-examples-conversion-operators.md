---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Konvertierungsoperatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: e50707155d509b8300966cbba8ee885492e5b815
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108640"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="7ea5b-102">Beispiele für die methodenbasierte Abfragesyntax: Konvertierungsoperatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="7ea5b-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="7ea5b-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> und <xref:System.Linq.Enumerable.ToList%2A> einen Abfrageausdruck sofort ausführen können.</span><span class="sxs-lookup"><span data-stu-id="7ea5b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="7ea5b-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="7ea5b-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="7ea5b-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="7ea5b-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7ea5b-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="7ea5b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="7ea5b-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie eine LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7ea5b-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="7ea5b-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="7ea5b-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="7ea5b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ea5b-109">Example</span></span>  
 <span data-ttu-id="7ea5b-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToArray%2A>-Methode verwendet, um ein Array sofort in eine Sequenz umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="7ea5b-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="7ea5b-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="7ea5b-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="7ea5b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ea5b-112">Example</span></span>  
 <span data-ttu-id="7ea5b-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToDictionary%2A>-Methode verwendet, um eine Sequenz und einen zugehörigen Schlüsselausdruck sofort in ein Wörterbuch umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="7ea5b-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="7ea5b-114">ToList</span><span class="sxs-lookup"><span data-stu-id="7ea5b-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="7ea5b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ea5b-115">Example</span></span>  
 <span data-ttu-id="7ea5b-116">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ToList%2A>-Methode verwendet, um eine Sequenz sofort in eine <xref:System.Collections.Generic.List%601> umzuwandeln, wobei `T` vom Typ <xref:System.Data.DataRow> ist.</span><span class="sxs-lookup"><span data-stu-id="7ea5b-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="7ea5b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ea5b-117">See also</span></span>

- [<span data-ttu-id="7ea5b-118">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="7ea5b-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="7ea5b-119">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7ea5b-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="7ea5b-120">Übersicht über Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="7ea5b-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="7ea5b-121">Standard Query Operators Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ea5b-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
