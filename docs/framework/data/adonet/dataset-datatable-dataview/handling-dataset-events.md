---
title: Behandeln von DataSet-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: 5e1de3effcae5700aa25f5dbb84f2dec3a0b20f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195281"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="a7790-102">Behandeln von DataSet-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="a7790-102">Handling DataSet Events</span></span>
<span data-ttu-id="a7790-103">Das <xref:System.Data.DataSet> -Objekt stellt die folgenden drei Ereignisse bereit: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>und <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="a7790-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="a7790-104">Das "MergeFailed"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a7790-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="a7790-105">Das am häufigsten verwendete Ereignis des `DataSet` -Objekts ist `MergeFailed`. Dieses Ereignis wird ausgelöst, wenn sich die Schemas der `DataSet` -Objekte, die zusammengeführt werden, widersprechen.</span><span class="sxs-lookup"><span data-stu-id="a7790-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="a7790-106">Zu einem solchen Konflikt kommt es, wenn eine Ziel- und eine Quell- <xref:System.Data.DataRow> den gleichen Primärschlüsselwert besitzen und die <xref:System.Data.DataSet.EnforceConstraints%2A> -Eigenschaft auf `true`gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a7790-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="a7790-107">Wenn z. B. die zusammenzuführenden Primärschlüsselspalten einer Tabelle in den Tabellen der beiden `DataSet` -Objekte identisch sind, wird eine Ausnahme ausgegeben und das `MergeFailed` -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a7790-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="a7790-108">Das <xref:System.Data.MergeFailedEventArgs> -Objekt, das an das `MergeFailed` -Ereignis übergeben wird, besitzt eine <xref:System.Data.MergeFailedEventArgs.Conflict%2A> -Eigenschaft, die den Konflikt im Schema der beiden `DataSet` -Objekte kennzeichnet, sowie eine <xref:System.Data.MergeFailedEventArgs.Table%2A> -Eigenschaft, die den Namen der Tabelle mit dem Konflikt angibt.</span><span class="sxs-lookup"><span data-stu-id="a7790-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="a7790-109">Das folgende Codefragment zeigt, wie ein Ereignishandler für das `MergeFailed` -Ereignis hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7790-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
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
  
## <a name="the-initialized-event"></a><span data-ttu-id="a7790-110">Das "Initialized"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a7790-110">The Initialized Event</span></span>  
 <span data-ttu-id="a7790-111">Das <xref:System.Data.DataSet.Initialized> -Ereignis tritt ein, nachdem der `DataSet` -Konstruktor eine neue Instanz vom `DataSet`initialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="a7790-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="a7790-112">Die <xref:System.Data.DataSet.IsInitialized%2A> -Eigenschaft gibt `true` zurück, wenn die Initialisierung vom `DataSet` abgeschlossen wurde. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a7790-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="a7790-113">Die <xref:System.Data.DataSet.BeginInit%2A> -Methode, die die Initialisierung eines `DataSet`startet, setzt <xref:System.Data.DataSet.IsInitialized%2A> auf `false`.</span><span class="sxs-lookup"><span data-stu-id="a7790-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="a7790-114">Durch die <xref:System.Data.DataSet.EndInit%2A> -Methode, die die Initialisierung eines `DataSet`beendet, wird der Wert auf `true`gesetzt.</span><span class="sxs-lookup"><span data-stu-id="a7790-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="a7790-115">Diese Methoden werden von der Visual Studio-entwurfsumgebung verwendet, zum Initialisieren einer `DataSet` , der von einer anderen Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7790-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="a7790-116">Im Normalfall werden Sie diese Methoden in Ihrem Code nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="a7790-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="a7790-117">Das "Disposed"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="a7790-117">The Disposed Event</span></span>  
 `DataSet` <span data-ttu-id="a7790-118">stammt aus der <xref:System.ComponentModel.MarshalByValueComponent> -Klasse, die beide macht die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Methode und die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a7790-118">is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="a7790-119">Die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis fügt einen Ereignishandler zur Überwachung des disposed-Ereignisses für die Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7790-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="a7790-120">Können Sie die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis eine `DataSet` Wenn ausgeführt werden soll code, wenn die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a7790-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> <span data-ttu-id="a7790-121">Gibt die Ressourcen, die von verwendet die <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="a7790-121">releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7790-122">Die `DataSet` und `DataTable` Objekte erben von <xref:System.ComponentModel.MarshalByValueComponent> und unterstützen die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle für das Remoting.</span><span class="sxs-lookup"><span data-stu-id="a7790-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="a7790-123">Dies sind die einzigen ADO.NET-Objekte, die remotingfähig sind.</span><span class="sxs-lookup"><span data-stu-id="a7790-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="a7790-124">Weitere Informationen finden Sie unter [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a7790-124">For more information, see [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="a7790-125">Informationen zu weiteren verfügbaren Ereignissen beim Arbeiten mit einem `DataSet`, finden Sie unter [Behandeln von DataTable-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) und [Behandeln von DataAdapter-Ereignissen](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="a7790-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7790-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7790-126">See also</span></span>

- [<span data-ttu-id="a7790-127">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="a7790-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="a7790-128">Überprüfen von Daten</span><span class="sxs-lookup"><span data-stu-id="a7790-128">Validating Data</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [<span data-ttu-id="a7790-129">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a7790-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="a7790-130">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a7790-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
