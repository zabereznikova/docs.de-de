---
title: Laden von Daten in ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: cb5578d790e5d3f54f75f964bb3288d861c9d7c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878539"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="228ce-102">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="228ce-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="228ce-103">Ein <xref:System.Data.DataSet>-Objekt muss zuerst aufgefüllt werden, bevor Sie es mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] abfragen können.</span><span class="sxs-lookup"><span data-stu-id="228ce-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="228ce-104">Das Auffüllen des <xref:System.Data.DataSet>-Objekts kann auf verschiedene Art und Weise erfolgen.</span><span class="sxs-lookup"><span data-stu-id="228ce-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="228ce-105">Beispielsweise können Sie [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] zum Abfragen der Datenbank, und laden die Ergebnisse in die <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="228ce-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="228ce-106">Weitere Informationen finden Sie unter [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="228ce-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="228ce-107">Eine andere Möglichkeit, Daten in ein <xref:System.Data.DataSet> zu laden, besteht darin, Daten mithilfe der <xref:System.Data.Common.DataAdapter>-Klasse aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="228ce-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="228ce-108">Dies wird im folgenden Beispiel illustriert.</span><span class="sxs-lookup"><span data-stu-id="228ce-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="228ce-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="228ce-109">Example</span></span>  
 <span data-ttu-id="228ce-110">In diesem Beispiel wird ein <xref:System.Data.Common.DataAdapter> verwendet, um aus der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank Verkaufsinformationen für das Jahr 2002 abzurufen und die Ergebnisse in ein <xref:System.Data.DataSet> zu laden.</span><span class="sxs-lookup"><span data-stu-id="228ce-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="228ce-111">Nachdem das <xref:System.Data.DataSet> aufgefüllt wurde, können Sie mithilfe von [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfragen Daten aus ihm abrufen.</span><span class="sxs-lookup"><span data-stu-id="228ce-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="228ce-112">Die `FillDataSet` -Methode in diesem Beispiel wird verwendet, in den Beispielabfragen in [LINQ to DataSet-Beispielen](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="228ce-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="228ce-113">Weitere Informationen finden Sie unter [DataSets Abfragen](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="228ce-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="228ce-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="228ce-114">See also</span></span>

- [<span data-ttu-id="228ce-115">Übersicht über LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="228ce-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="228ce-116">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="228ce-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="228ce-117">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="228ce-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
