---
title: "Beispiele für die methodenbasierte Abfragesyntax: Projektion (LINQ to DataSet)"
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
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 879754e0604b9dfa6a6ffc7b7777094cc156befb
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a><span data-ttu-id="8d762-102">Beispiele für die methodenbasierte Abfragesyntax: Projektion (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="8d762-102">Method-Based Query Syntax Examples: Projection (LINQ to DataSet)</span></span>
<span data-ttu-id="8d762-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mithilfe der Methoden <xref:System.Linq.Enumerable.Select%2A> und <xref:System.Linq.Enumerable.SelectMany%2A> und der methodenbasierten Abfragesyntax ein <xref:System.Data.DataSet> abfragen können.</span><span class="sxs-lookup"><span data-stu-id="8d762-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the method-based query syntax.</span></span>  
  
 <span data-ttu-id="8d762-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben, [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="8d762-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="8d762-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="8d762-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8d762-106">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="8d762-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="8d762-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8d762-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="8d762-108">Auswählen</span><span class="sxs-lookup"><span data-stu-id="8d762-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d762-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d762-109">Example</span></span>  
 <span data-ttu-id="8d762-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Select%2A>-Methode verwendet, um die Eigenschaften `Name`, `ProductNumber` und `ListPrice` auf eine Abfolge anonymer Typen zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="8d762-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to project the `Name`, `ProductNumber`, and `ListPrice` properties to a sequence of anonymous types.</span></span>  <span data-ttu-id="8d762-111">Im sich dabei ergebenden Typ wird außerdem die `ListPrice`-Eigenschaft in `Price` umbenannt.</span><span class="sxs-lookup"><span data-stu-id="8d762-111">The `ListPrice` property is also renamed to `Price` in the resulting type.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="8d762-112">SelectMany</span><span class="sxs-lookup"><span data-stu-id="8d762-112">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d762-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d762-113">Example</span></span>  
 <span data-ttu-id="8d762-114">In diesem Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, bei denen `TotalDue` kleiner als 500.00 ist.</span><span class="sxs-lookup"><span data-stu-id="8d762-114">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="8d762-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d762-115">Example</span></span>  
 <span data-ttu-id="8d762-116">In diesem Beispiel wird die <xref:System.Linq.Enumerable.SelectMany%2A>-Methode verwendet, um alle Aufträge auszuwählen, bei denen die Bestellung am 1. Oktober 2002 oder später eingegangen ist.</span><span class="sxs-lookup"><span data-stu-id="8d762-116">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="8d762-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d762-117">See Also</span></span>  
 [<span data-ttu-id="8d762-118">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="8d762-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="8d762-119">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="8d762-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="8d762-120">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="8d762-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
