---
title: Abfragen von typisierten DataSets
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
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fff678a54416e72f4be8c3fdfdcacec5a7d90af7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="querying-typed-datasets"></a><span data-ttu-id="59d7d-102">Abfragen von typisierten DataSets</span><span class="sxs-lookup"><span data-stu-id="59d7d-102">Querying Typed DataSets</span></span>
<span data-ttu-id="59d7d-103">Wenn zum Zeitpunkt der Anwendungskonzeptionierung bereits das <xref:System.Data.DataSet>-Schema bekannt ist, wird empfohlen, bei der Benutzung von <xref:System.Data.DataSet> mit einem typisierten [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="59d7d-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="59d7d-104">Eine typisierte <xref:System.Data.DataSet> ist eine Klasse, die von abgeleitet ist eine <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="59d7d-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="59d7d-105">Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="59d7d-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="59d7d-106">Darüber hinaus eine typisierte <xref:System.Data.DataSet> stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="59d7d-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="59d7d-107">Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="59d7d-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="59d7d-108">Dadurch werden Abfragen einfacher und lesbarer.</span><span class="sxs-lookup"><span data-stu-id="59d7d-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="59d7d-109">Weitere Informationen finden Sie unter [typisierter DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="59d7d-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="59d7d-110">unterstützt auch das Abfragen von Daten in einem typisierten <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="59d7d-110"> also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="59d7d-111">Mit einer typisierten <xref:System.Data.DataSet>, Sie müssen nicht die generischen <xref:System.Data.DataRowExtensions.Field%2A> Methode oder <xref:System.Data.DataRowExtensions.SetField%2A> Methode, um Spaltendaten zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="59d7d-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span>  <span data-ttu-id="59d7d-112">Eigenschaftennamen sind zum Zeitpunkt der Kompilierung verfügbar, da die Typinformationen, in enthalten ist der <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="59d7d-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="59d7d-113">bietet Zugriff auf Spaltenwerte den richtigen Typ aufweist, sodass Typfehler-Konflikt beim Kompilieren des Codes statt zur Laufzeit abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="59d7d-113"> provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>  
  
 <span data-ttu-id="59d7d-114">Bevor Sie mit der Abfrage eines typisierten <xref:System.Data.DataSet> beginnen können, müssen Sie die Klasse mithilfe des DataSet-Designers in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] generieren.</span><span class="sxs-lookup"><span data-stu-id="59d7d-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the DataSet Designer in [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].</span></span>  <span data-ttu-id="59d7d-115">Weitere Informationen finden Sie unter [Erstellen und Konfigurieren von Datasets in Visual Studio](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="59d7d-115">For more information, see [Create and configure datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59d7d-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59d7d-116">Example</span></span>  
 <span data-ttu-id="59d7d-117">Im folgenden Beispiel wird eine Abfrage von Daten in einem typisierten <xref:System.Data.DataSet> veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="59d7d-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>  
  
```csharp  
var query = from o in orders  
            where o.OnlineOrderFlag == true  
            select new { o.SalesOrderID,  
                         o.OrderDate,  
                         o.SalesOrderNumber };  
  
foreach(var order in query)   
{  
    Console.WriteLine("{0}\t{1:d}\t{2}",   
order.SalesOrderID,   
order.OrderDate,   
order.SalesOrderNumber);  
}  
```  
  
```vb  
Dim orders = ds.Tables("SalesOrderHeader")  
  
Dim query = _  
       From o In orders _  
       Where o.OnlineOrderFlag = True _  
       Select New {SalesOrderID := o.SalesOrderID, _  
                   OrderDate := o.OrderDate, _  
                   SalesOrderNumber := o.SalesOrderNumber}  
  
For Each Dim onlineOrder In query  
 Console.WriteLine("{0}\t{1:d}\t{2}", _  
 onlineOrder.SalesOrderID, _  
 onlineOrder.OrderDate, _  
 onlineOrder.SalesOrderNumber)  
Next  
```  
  
## <a name="see-also"></a><span data-ttu-id="59d7d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59d7d-118">See Also</span></span>  
 [<span data-ttu-id="59d7d-119">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="59d7d-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="59d7d-120">Tabellenübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="59d7d-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 [<span data-ttu-id="59d7d-121">Abfragen für einzelne Tabellen</span><span class="sxs-lookup"><span data-stu-id="59d7d-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
