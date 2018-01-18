---
title: "Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren (LINQ to DataSet)"
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
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ba6a774c0e270cda1e139ab9ddb9233e994c3f12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="ea76d-102">Beispiele für die methodenbasierte Abfragesyntax: Elementoperatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ea76d-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="ea76d-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie mit der <xref:System.Linq.Enumerable.First%2A>-Methode und der <xref:System.Linq.Enumerable.ElementAt%2A>-Methode und mithilfe der Abfrageausdruckssyntax <xref:System.Data.DataRow>-Elemente aus einem <xref:System.Data.DataSet> abrufen können.</span><span class="sxs-lookup"><span data-stu-id="ea76d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="ea76d-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben, [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ea76d-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="ea76d-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="ea76d-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ea76d-106">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="ea76d-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 <span data-ttu-id="ea76d-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="ea76d-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="ea76d-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="ea76d-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="ea76d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea76d-109">Example</span></span>  
 <span data-ttu-id="ea76d-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.ElementAt%2A>-Methode verwendet, um die fünfte Adresse abzurufen, bei der `PostalCode` gleich "M4B 1V7" ist.</span><span class="sxs-lookup"><span data-stu-id="ea76d-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a><span data-ttu-id="ea76d-111">First</span><span class="sxs-lookup"><span data-stu-id="ea76d-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="ea76d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea76d-112">Example</span></span>  
 <span data-ttu-id="ea76d-113">In diesem Beispiel wird die <xref:System.Linq.Enumerable.First%2A>-Methode verwendet, um den ersten Kontakt zurückzugeben, dessen Vorname "Brooke" lautet.</span><span class="sxs-lookup"><span data-stu-id="ea76d-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a><span data-ttu-id="ea76d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea76d-114">See Also</span></span>  
 [<span data-ttu-id="ea76d-115">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="ea76d-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="ea76d-116">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ea76d-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="ea76d-117">Übersicht über Standardabfrageoperatoren</span><span class="sxs-lookup"><span data-stu-id="ea76d-117">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
