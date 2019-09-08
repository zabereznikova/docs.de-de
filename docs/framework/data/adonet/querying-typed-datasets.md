---
title: Abfragen von typisierten DataSets
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782967"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="9b293-102">Abfragen von typisierten Datasets</span><span class="sxs-lookup"><span data-stu-id="9b293-102">Query typed DataSets</span></span>

<span data-ttu-id="9b293-103">Wenn das Schema <xref:System.Data.DataSet> der zum Zeitpunkt der Anwendungs Entwurfszeit bekannt ist, empfiehlt es sich, bei Verwendung <xref:System.Data.DataSet> von LINQ to DataSet eine typisierte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b293-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="9b293-104">Ein typisierter <xref:System.Data.DataSet> ist eine Klasse, die von <xref:System.Data.DataSet>einem abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="9b293-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b293-105">Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9b293-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b293-106">Darüber hinaus stellt ein <xref:System.Data.DataSet> typisiertes stark typisierte Methoden, Ereignisse und Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="9b293-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="9b293-107">Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="9b293-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="9b293-108">Dadurch werden Abfragen einfacher und lesbarer.</span><span class="sxs-lookup"><span data-stu-id="9b293-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="9b293-109">Weitere Informationen finden Sie unter [typisierte Datasets](./dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="9b293-109">For more information, see [Typed DataSets](./dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="9b293-110">LINQ to DataSet unterstützt auch das Abfragen über ein <xref:System.Data.DataSet>typisiertes.</span><span class="sxs-lookup"><span data-stu-id="9b293-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b293-111">Bei einem typisierten <xref:System.Data.DataSet>müssen Sie die generische <xref:System.Data.DataRowExtensions.Field%2A> Methode oder <xref:System.Data.DataRowExtensions.SetField%2A> Methode nicht verwenden, um auf Spaltendaten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9b293-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="9b293-112">Eigenschaftsnamen sind zum Zeitpunkt der Kompilierung verfügbar, da die Typinformationen <xref:System.Data.DataSet>in enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9b293-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9b293-113">LINQ to DataSet bietet Zugriff auf Spaltenwerte als korrekten Typ, sodass Typen Konflikt Fehler abgefangen werden, wenn der Code statt zur Laufzeit kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="9b293-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="9b293-114">Bevor Sie mit dem Abfragen eines typisierten <xref:System.Data.DataSet>beginnen können, müssen Sie die-Klasse mithilfe des **DataSet-Designers** in Visual Studio generieren.</span><span class="sxs-lookup"><span data-stu-id="9b293-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="9b293-115">Weitere Informationen finden Sie unter [Erstellen und Konfigurieren von Datasets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9b293-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="9b293-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b293-116">Example</span></span>

<span data-ttu-id="9b293-117">Im folgenden Beispiel wird eine Abfrage von Daten in einem typisierten <xref:System.Data.DataSet> veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="9b293-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9b293-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b293-118">See also</span></span>

- [<span data-ttu-id="9b293-119">Abfragen von DataSets</span><span class="sxs-lookup"><span data-stu-id="9b293-119">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="9b293-120">Tabellenübergreifende Abfragen</span><span class="sxs-lookup"><span data-stu-id="9b293-120">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="9b293-121">Abfragen für einzelne Tabellen</span><span class="sxs-lookup"><span data-stu-id="9b293-121">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)
