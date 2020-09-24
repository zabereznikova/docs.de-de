---
title: Laden von Daten in ein DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166715"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="97508-102">Laden von Daten in ein DataSet</span><span class="sxs-lookup"><span data-stu-id="97508-102">Loading Data Into a DataSet</span></span>

<span data-ttu-id="97508-103">Ein- <xref:System.Data.DataSet> Objekt muss zuerst aufgefüllt werden, bevor es mit LINQ to DataSet abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="97508-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="97508-104">Das Auffüllen des <xref:System.Data.DataSet>-Objekts kann auf verschiedene Art und Weise erfolgen.</span><span class="sxs-lookup"><span data-stu-id="97508-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="97508-105">Beispielsweise können Sie verwenden, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] um die Datenbank abzufragen und die Ergebnisse in die zu laden <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="97508-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="97508-106">Weitere Informationen finden Sie unter [LINQ to SQL](./sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="97508-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="97508-107">Eine andere Möglichkeit, Daten in ein <xref:System.Data.DataSet> zu laden, besteht darin, Daten mithilfe der <xref:System.Data.Common.DataAdapter>-Klasse aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="97508-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="97508-108">Dies wird im folgenden Beispiel illustriert.</span><span class="sxs-lookup"><span data-stu-id="97508-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97508-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97508-109">Example</span></span>  

 <span data-ttu-id="97508-110">In diesem Beispiel wird ein <xref:System.Data.Common.DataAdapter> verwendet, um aus der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank Verkaufsinformationen für das Jahr 2002 abzurufen und die Ergebnisse in ein <xref:System.Data.DataSet> zu laden.</span><span class="sxs-lookup"><span data-stu-id="97508-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="97508-111">Nachdem der aufgefüllt wurde <xref:System.Data.DataSet> , können Sie Abfragen für ihn mit LINQ to DataSet schreiben.</span><span class="sxs-lookup"><span data-stu-id="97508-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="97508-112">Die- `FillDataSet` Methode in diesem Beispiel wird in den Beispielabfragen in [LINQ to DataSet Beispielen](linq-to-dataset-examples.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="97508-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="97508-113">Weitere Informationen finden Sie unter [Abfragen von Datasets](querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="97508-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="97508-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97508-114">See also</span></span>

- [<span data-ttu-id="97508-115">Übersicht über LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="97508-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="97508-116">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="97508-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="97508-117">Beispiele für LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="97508-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
