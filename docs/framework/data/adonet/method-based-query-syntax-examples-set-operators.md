---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Set-Operatoren (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 48aa6044f39be93f144b6c4af5137b131dda0b30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772137"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="51240-102">Beispiele für die methodenbasierte Abfragesyntax: Set-Operatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="51240-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="51240-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, und <xref:System.Linq.Enumerable.Union%2A> Operatoren wertbasierte Vergleichsoperationen für einen Satz von Datenzeilen ausführen.[ Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) finden Sie unter [Vergleichen von DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) für Weitere Informationen zu <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="51240-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="51240-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben ist, im [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="51240-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="51240-105">In den Beispielen in diesem Thema wird auf die Tabellen &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;, &lt;legacyBold&gt;Address&lt;/legacyBold&gt;, &lt;legacyBold&gt;Product&lt;/legacyBold&gt;, &lt;legacyBold&gt;SalesOrderHeader&lt;/legacyBold&gt; und &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt; in der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="51240-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="51240-106">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="51240-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="51240-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie eine LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="51240-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="51240-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="51240-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="51240-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51240-109">Example</span></span>  
 <span data-ttu-id="51240-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Distinct%2A>-Methode verwendet, um doppelte Elemente in einer Sequenz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="51240-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="51240-111">Except</span><span class="sxs-lookup"><span data-stu-id="51240-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="51240-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51240-112">Example</span></span>  
 <span data-ttu-id="51240-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Except%2A>-Methode verwendet, um die Kontakte abzurufen, die zwar in der ersten, nicht aber in der zweiten Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="51240-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="51240-114">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="51240-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="51240-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51240-115">Example</span></span>  
 <span data-ttu-id="51240-116">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Intersect%2A>-Methode verwendet, um die Kontakte abzurufen, die in beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="51240-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="51240-117">Union</span><span class="sxs-lookup"><span data-stu-id="51240-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="51240-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51240-118">Example</span></span>  
 <span data-ttu-id="51240-119">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Union%2A>-Methode verwendet, um die Kontakte abzurufen, die in nur einer der beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="51240-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="51240-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51240-120">See also</span></span>

- [<span data-ttu-id="51240-121">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="51240-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="51240-122">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="51240-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="51240-123">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="51240-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="51240-124">Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="51240-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
