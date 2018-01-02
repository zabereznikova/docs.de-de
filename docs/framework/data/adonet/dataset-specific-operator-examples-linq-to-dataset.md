---
title: "Beispiele für DataSet-spezifische Operatoren (LINQ to DataSet)"
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
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 74b6af309bf595e0caaf4e81ab0192bcda7dde35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="38f6b-102">Beispiele für DataSet-spezifische Operatoren (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="38f6b-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="38f6b-103">In den Beispielen in diesem Thema wird gezeigt, wie Sie die <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode und die <xref:System.Data.DataRowComparer>-Klasse verwenden können.</span><span class="sxs-lookup"><span data-stu-id="38f6b-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="38f6b-104">Die `FillDataSet` in diesen Beispielen verwendete Methode angegeben, [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="38f6b-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="38f6b-105">In den Beispielen in diesem Thema wird auf die Tabellen <legacyBold>Contact</legacyBold>, <legacyBold>Address</legacyBold>, <legacyBold>Product</legacyBold>, <legacyBold>SalesOrderHeader</legacyBold> und <legacyBold>SalesOrderDetail</legacyBold> in der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="38f6b-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="38f6b-106">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="38f6b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="38f6b-107">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines LINQ to DataSet-Projekt In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="38f6b-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="38f6b-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="38f6b-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="38f6b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38f6b-109">Example</span></span>  
 <span data-ttu-id="38f6b-110">In diesem Beispiel wird eine <xref:System.Data.DataTable> mithilfe der <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>-Methode mit Abfrageergebnissen geladen.</span><span class="sxs-lookup"><span data-stu-id="38f6b-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="38f6b-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="38f6b-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="38f6b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38f6b-112">Example</span></span>  
 <span data-ttu-id="38f6b-113">In diesem Beispiel werden zwei verschiedene Datenzeilen mithilfe von <xref:System.Data.DataRowComparer> miteinander verglichen.</span><span class="sxs-lookup"><span data-stu-id="38f6b-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="38f6b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38f6b-114">See Also</span></span>  
 [<span data-ttu-id="38f6b-115">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="38f6b-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="38f6b-116">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="38f6b-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
