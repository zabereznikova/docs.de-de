---
title: Behandeln von DataSet-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: b2b71dac58838a826933af570934bf4bbb35e025
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784611"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="80a89-102">Behandeln von DataSet-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="80a89-102">Handling DataSet Events</span></span>
<span data-ttu-id="80a89-103">Das <xref:System.Data.DataSet> -Objekt stellt die folgenden drei Ereignisse bereit: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>und <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="80a89-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="80a89-104">Das "MergeFailed"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="80a89-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="80a89-105">Das am häufigsten verwendete Ereignis des `DataSet` -Objekts ist `MergeFailed`. Dieses Ereignis wird ausgelöst, wenn sich die Schemas der `DataSet` -Objekte, die zusammengeführt werden, widersprechen.</span><span class="sxs-lookup"><span data-stu-id="80a89-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="80a89-106">Zu einem solchen Konflikt kommt es, wenn eine Ziel- und eine Quell- <xref:System.Data.DataRow> den gleichen Primärschlüsselwert besitzen und die <xref:System.Data.DataSet.EnforceConstraints%2A> -Eigenschaft auf `true`gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="80a89-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="80a89-107">Wenn z. B. die zusammenzuführenden Primärschlüsselspalten einer Tabelle in den Tabellen der beiden `DataSet` -Objekte identisch sind, wird eine Ausnahme ausgegeben und das `MergeFailed` -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="80a89-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="80a89-108">Das <xref:System.Data.MergeFailedEventArgs> -Objekt, das an das `MergeFailed` -Ereignis übergeben wird, besitzt eine <xref:System.Data.MergeFailedEventArgs.Conflict%2A> -Eigenschaft, die den Konflikt im Schema der beiden `DataSet` -Objekte kennzeichnet, sowie eine <xref:System.Data.MergeFailedEventArgs.Table%2A> -Eigenschaft, die den Namen der Tabelle mit dem Konflikt angibt.</span><span class="sxs-lookup"><span data-stu-id="80a89-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="80a89-109">Das folgende Codefragment zeigt, wie ein Ereignishandler für das `MergeFailed` -Ereignis hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="80a89-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a><span data-ttu-id="80a89-110">Das "Initialized"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="80a89-110">The Initialized Event</span></span>  
 <span data-ttu-id="80a89-111">Das <xref:System.Data.DataSet.Initialized> -Ereignis tritt ein, nachdem der `DataSet` -Konstruktor eine neue Instanz vom `DataSet`initialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="80a89-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="80a89-112">Die <xref:System.Data.DataSet.IsInitialized%2A> -Eigenschaft gibt `true` zurück, wenn die Initialisierung vom `DataSet` abgeschlossen wurde. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80a89-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="80a89-113">Die <xref:System.Data.DataSet.BeginInit%2A> -Methode, die die Initialisierung eines `DataSet`startet, setzt <xref:System.Data.DataSet.IsInitialized%2A> auf `false`.</span><span class="sxs-lookup"><span data-stu-id="80a89-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="80a89-114">Durch die <xref:System.Data.DataSet.EndInit%2A> -Methode, die die Initialisierung eines `DataSet`beendet, wird der Wert auf `true`gesetzt.</span><span class="sxs-lookup"><span data-stu-id="80a89-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="80a89-115">Diese Methoden werden von der Visual Studio-Entwurfs Umgebung verwendet, um eine `DataSet` zu initialisieren, die von einer anderen Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="80a89-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="80a89-116">Im Normalfall werden Sie diese Methoden in Ihrem Code nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="80a89-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="80a89-117">Das "Disposed"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="80a89-117">The Disposed Event</span></span>  
 <span data-ttu-id="80a89-118">Das`DataSet` wird von der <xref:System.ComponentModel.MarshalByValueComponent> -Klasse abgeleitet, die sowohl die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> -Methode als auch das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="80a89-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="80a89-119">Das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis fügt einen Ereignishandler hinzu, der auf das verworfene Ereignis für die Komponente lauscht.</span><span class="sxs-lookup"><span data-stu-id="80a89-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="80a89-120">Sie können das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis `DataSet` eines verwenden, wenn Sie Code ausführen möchten, wenn <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> die-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="80a89-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="80a89-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>Gibt die von <xref:System.ComponentModel.MarshalByValueComponent>verwendeten Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="80a89-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80a89-122">Die `DataSet` - `DataTable` und-Objekte <xref:System.ComponentModel.MarshalByValueComponent> erben von und <xref:System.Runtime.Serialization.ISerializable> unterstützen die-Schnittstelle für Remoting.</span><span class="sxs-lookup"><span data-stu-id="80a89-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="80a89-123">Dies sind die einzigen ADO.NET-Objekte, die remotingfähig sind.</span><span class="sxs-lookup"><span data-stu-id="80a89-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="80a89-124">Weitere Informationen finden Sie unter [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="80a89-124">For more information, see [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="80a89-125">Informationen zu anderen Ereignissen, die beim Arbeiten mit einem `DataSet`verfügbar sind, finden Sie unter [Verarbeiten von Daten](handling-datatable-events.md) und [Verarbeiten von DataAdapter-Ereignissen](../handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="80a89-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](handling-datatable-events.md) and [Handling DataAdapter Events](../handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a89-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80a89-126">See also</span></span>

- [<span data-ttu-id="80a89-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="80a89-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- <span data-ttu-id="80a89-128">[Überprüfen von Daten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="80a89-128">[Validating Data](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span></span>
- [<span data-ttu-id="80a89-129">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="80a89-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="80a89-130">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="80a89-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
