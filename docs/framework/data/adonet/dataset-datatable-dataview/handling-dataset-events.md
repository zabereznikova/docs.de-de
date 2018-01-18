---
title: Behandeln von DataSet-Ereignissen
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
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6c87e805bd710b49ce805af8223cddb5c7036c50
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="handling-dataset-events"></a><span data-ttu-id="70d50-102">Behandeln von DataSet-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="70d50-102">Handling DataSet Events</span></span>
<span data-ttu-id="70d50-103">Das <xref:System.Data.DataSet> -Objekt stellt die folgenden drei Ereignisse bereit: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>und <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="70d50-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="70d50-104">Das "MergeFailed"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="70d50-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="70d50-105">Das am häufigsten verwendete Ereignis des `DataSet` -Objekts ist `MergeFailed`. Dieses Ereignis wird ausgelöst, wenn sich die Schemas der `DataSet` -Objekte, die zusammengeführt werden, widersprechen.</span><span class="sxs-lookup"><span data-stu-id="70d50-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="70d50-106">Zu einem solchen Konflikt kommt es, wenn eine Ziel- und eine Quell- <xref:System.Data.DataRow> den gleichen Primärschlüsselwert besitzen und die <xref:System.Data.DataSet.EnforceConstraints%2A> -Eigenschaft auf `true`gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="70d50-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="70d50-107">Wenn z. B. die zusammenzuführenden Primärschlüsselspalten einer Tabelle in den Tabellen der beiden `DataSet` -Objekte identisch sind, wird eine Ausnahme ausgegeben und das `MergeFailed` -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="70d50-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="70d50-108">Das <xref:System.Data.MergeFailedEventArgs> -Objekt, das an das `MergeFailed` -Ereignis übergeben wird, besitzt eine <xref:System.Data.MergeFailedEventArgs.Conflict%2A> -Eigenschaft, die den Konflikt im Schema der beiden `DataSet` -Objekte kennzeichnet, sowie eine <xref:System.Data.MergeFailedEventArgs.Table%2A> -Eigenschaft, die den Namen der Tabelle mit dem Konflikt angibt.</span><span class="sxs-lookup"><span data-stu-id="70d50-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="70d50-109">Das folgende Codefragment zeigt, wie ein Ereignishandler für das `MergeFailed`-Ereignis hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="70d50-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
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
  
## <a name="the-initialized-event"></a><span data-ttu-id="70d50-110">Das "Initialized"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="70d50-110">The Initialized Event</span></span>  
 <span data-ttu-id="70d50-111">Das <xref:System.Data.DataSet.Initialized> -Ereignis tritt ein, nachdem der `DataSet` -Konstruktor eine neue Instanz vom `DataSet`initialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="70d50-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="70d50-112">Die <xref:System.Data.DataSet.IsInitialized%2A> -Eigenschaft gibt `true` zurück, wenn die Initialisierung vom `DataSet` abgeschlossen wurde. Andernfalls wird `false`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="70d50-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="70d50-113">Die <xref:System.Data.DataSet.BeginInit%2A> -Methode, die die Initialisierung eines `DataSet`startet, setzt <xref:System.Data.DataSet.IsInitialized%2A> auf `false`.</span><span class="sxs-lookup"><span data-stu-id="70d50-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="70d50-114">Durch die <xref:System.Data.DataSet.EndInit%2A> -Methode, die die Initialisierung eines `DataSet`beendet, wird der Wert auf `true`gesetzt.</span><span class="sxs-lookup"><span data-stu-id="70d50-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="70d50-115">Diese Methoden werden von der [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] -Entwicklungsumgebung zum Initialisieren eines `DataSet` genutzt, das von einer anderen Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70d50-115">These methods are used by the [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="70d50-116">Im Normalfall werden Sie diese Methoden in Ihrem Code nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="70d50-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="70d50-117">Das "Disposed"-Ereignis</span><span class="sxs-lookup"><span data-stu-id="70d50-117">The Disposed Event</span></span>  
 <span data-ttu-id="70d50-118">Das`DataSet` wird von der <xref:System.ComponentModel.MarshalByValueComponent> -Klasse abgeleitet, die sowohl die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> -Methode als auch das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="70d50-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="70d50-119">Die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis fügt einen Ereignishandler, um das "disposed"-Ereignis für die Komponente zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="70d50-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="70d50-120">Können Sie die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis für ein `DataSet` Wenn ausgeführt werden soll code, wenn die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="70d50-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="70d50-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>die verwendeten Ressourcen frei der <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="70d50-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70d50-122">Die `DataSet` und `DataTable` Objekte erben von <xref:System.ComponentModel.MarshalByValueComponent> und unterstützen die <xref:System.Runtime.Serialization.ISerializable> Schnittstelle für das Remoting.</span><span class="sxs-lookup"><span data-stu-id="70d50-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="70d50-123">Dies sind die einzigen ADO.NET-Objekte, die remotingfähig sind.</span><span class="sxs-lookup"><span data-stu-id="70d50-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="70d50-124">Weitere Informationen finden Sie unter [Remote Objects](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58).</span><span class="sxs-lookup"><span data-stu-id="70d50-124">For more information, see [Remote Objects](http://msdn.microsoft.com/en-us/515686e6-0a8d-42f7-8188-73abede57c58).</span></span>  
  
 <span data-ttu-id="70d50-125">Informationen zu anderen Ereignissen verfügbar, bei der Arbeit mit einem `DataSet`, finden Sie unter [Behandeln von DataTable-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) und [Behandeln von DataAdapter-Ereignissen](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="70d50-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) and [Handling DataAdapter Events](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d50-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d50-126">See Also</span></span>  
 [<span data-ttu-id="70d50-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="70d50-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="70d50-128">Überprüfen von Daten</span><span class="sxs-lookup"><span data-stu-id="70d50-128">Validating Data</span></span>](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 [<span data-ttu-id="70d50-129">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="70d50-129">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="70d50-130">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="70d50-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
