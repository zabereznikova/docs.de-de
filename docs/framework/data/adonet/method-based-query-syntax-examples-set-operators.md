---
title: "Beispiele für die methodenbasierte Abfragesyntax: Set-Operatoren (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 637e1c2fe66bcfd31b0392076b8b1058d0008482
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="2c133-102">Beispiele für die methodenbasierte Abfragesyntax: Set-Operatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="2c133-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="2c133-103">In den Beispielen in diesem Thema wird gezeigt, wie mithilfe der <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, und <xref:System.Linq.Enumerable.Union%2A> Operatoren wertbasierte Vergleichsoperationen für einen Satz von Datenzeilen ausführen.[ Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) finden Sie unter [Vergleichen von DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) Weitere Informationen zu <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="2c133-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="2c133-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben, [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="2c133-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2c133-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="2c133-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2c133-106">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="2c133-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="2c133-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2c133-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="2c133-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="2c133-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="2c133-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c133-109">Example</span></span>  
 <span data-ttu-id="2c133-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Distinct%2A>-Methode verwendet, um doppelte Elemente in einer Sequenz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2c133-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="2c133-111">Except</span><span class="sxs-lookup"><span data-stu-id="2c133-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="2c133-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c133-112">Example</span></span>  
 <span data-ttu-id="2c133-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Except%2A>-Methode verwendet, um die Kontakte abzurufen, die zwar in der ersten, nicht aber in der zweiten Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2c133-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="2c133-114">Überschneiden</span><span class="sxs-lookup"><span data-stu-id="2c133-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="2c133-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c133-115">Example</span></span>  
 <span data-ttu-id="2c133-116">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Intersect%2A>-Methode verwendet, um die Kontakte abzurufen, die in beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2c133-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="2c133-117">Union</span><span class="sxs-lookup"><span data-stu-id="2c133-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="2c133-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c133-118">Example</span></span>  
 <span data-ttu-id="2c133-119">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Union%2A>-Methode verwendet, um die Kontakte abzurufen, die in nur einer der beiden Tabellen aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2c133-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="2c133-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c133-120">See Also</span></span>  
 [<span data-ttu-id="2c133-121">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="2c133-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="2c133-122">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2c133-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="2c133-123">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="2c133-123">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
