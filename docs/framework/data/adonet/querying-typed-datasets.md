---
title: Abfragen von typisierten DataSets
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739645"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="80362-102">Abfragen von typisierten "DataSets"</span><span class="sxs-lookup"><span data-stu-id="80362-102">Query typed DataSets</span></span>

<span data-ttu-id="80362-103">Wenn das Schema der <xref:System.Data.DataSet> heißt Zeitpunkt der Anwendungskonzeptionierung, es wird empfohlen, dass Sie eine typisierte verwenden <xref:System.Data.DataSet> bei der Verwendung von LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="80362-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="80362-104">Eine typisierte <xref:System.Data.DataSet> ist eine abgeleitete Klasse eine <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="80362-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="80362-105">Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="80362-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="80362-106">Darüber hinaus eine typisierte <xref:System.Data.DataSet> stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="80362-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="80362-107">Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="80362-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="80362-108">Dadurch werden Abfragen einfacher und lesbarer.</span><span class="sxs-lookup"><span data-stu-id="80362-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="80362-109">Weitere Informationen finden Sie unter [typisierter DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="80362-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="80362-110">LINQ to DataSet ebenfalls unterstützt Abfragen von Daten in einem typisierten <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="80362-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="80362-111">Mit einer typisierten <xref:System.Data.DataSet>, Sie müssen nicht die generischen <xref:System.Data.DataRowExtensions.Field%2A> Methode oder <xref:System.Data.DataRowExtensions.SetField%2A> Methode, um Spaltendaten zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="80362-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="80362-112">Eigenschaftennamen sind zum Zeitpunkt der Kompilierung verfügbar, da die Typinformationen, in enthalten ist der <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="80362-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="80362-113">LINQ to DataSet bietet Zugriff auf Spaltenwerte als korrektem Typ, ein, sodass Typkonflikte abgefangen werden, wenn der Code statt zur Laufzeit kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="80362-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="80362-114">Bevor Sie beginnen können, eine typisierte Abfrage <xref:System.Data.DataSet>, müssen Sie die Klasse generieren, mit der **DataSet-Designer** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="80362-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="80362-115">Weitere Informationen finden Sie unter [erstellen und Konfigurieren von DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="80362-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="80362-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80362-116">Example</span></span>

<span data-ttu-id="80362-117">Im folgenden Beispiel wird eine Abfrage von Daten in einem typisierten <xref:System.Data.DataSet> veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="80362-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="80362-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80362-118">See also</span></span>

- [<span data-ttu-id="80362-119">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="80362-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="80362-120">Tabellenübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="80362-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="80362-121">Abfragen für einzelne Tabellen</span><span class="sxs-lookup"><span data-stu-id="80362-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
