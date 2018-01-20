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
ms.openlocfilehash: 820d93529fc12f3eeacd730cc66ec85ffd560ff9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="handling-dataset-events"></a>Behandeln von DataSet-Ereignissen
Das <xref:System.Data.DataSet> -Objekt stellt die folgenden drei Ereignisse bereit: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>und <xref:System.Data.DataSet.MergeFailed>.  
  
## <a name="the-mergefailed-event"></a>Das "MergeFailed"-Ereignis  
 Das am häufigsten verwendete Ereignis des `DataSet` -Objekts ist `MergeFailed`. Dieses Ereignis wird ausgelöst, wenn sich die Schemas der `DataSet` -Objekte, die zusammengeführt werden, widersprechen. Zu einem solchen Konflikt kommt es, wenn eine Ziel- und eine Quell- <xref:System.Data.DataRow> den gleichen Primärschlüsselwert besitzen und die <xref:System.Data.DataSet.EnforceConstraints%2A> -Eigenschaft auf `true`gesetzt ist. Wenn z. B. die zusammenzuführenden Primärschlüsselspalten einer Tabelle in den Tabellen der beiden `DataSet` -Objekte identisch sind, wird eine Ausnahme ausgegeben und das `MergeFailed` -Ereignis ausgelöst. Das <xref:System.Data.MergeFailedEventArgs> -Objekt, das an das `MergeFailed` -Ereignis übergeben wird, besitzt eine <xref:System.Data.MergeFailedEventArgs.Conflict%2A> -Eigenschaft, die den Konflikt im Schema der beiden `DataSet` -Objekte kennzeichnet, sowie eine <xref:System.Data.MergeFailedEventArgs.Table%2A> -Eigenschaft, die den Namen der Tabelle mit dem Konflikt angibt.  
  
 Das folgende Codefragment zeigt, wie ein Ereignishandler für das `MergeFailed`-Ereignis hinzugefügt werden kann.  
  
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
  
## <a name="the-initialized-event"></a>Das "Initialized"-Ereignis  
 Das <xref:System.Data.DataSet.Initialized> -Ereignis tritt ein, nachdem der `DataSet` -Konstruktor eine neue Instanz vom `DataSet`initialisiert hat.  
  
 Die <xref:System.Data.DataSet.IsInitialized%2A> -Eigenschaft gibt `true` zurück, wenn die Initialisierung vom `DataSet` abgeschlossen wurde. Andernfalls wird `false`zurückgegeben. Die <xref:System.Data.DataSet.BeginInit%2A> -Methode, die die Initialisierung eines `DataSet`startet, setzt <xref:System.Data.DataSet.IsInitialized%2A> auf `false`. Durch die <xref:System.Data.DataSet.EndInit%2A> -Methode, die die Initialisierung eines `DataSet`beendet, wird der Wert auf `true`gesetzt. Diese Methoden werden von der [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] -Entwicklungsumgebung zum Initialisieren eines `DataSet` genutzt, das von einer anderen Komponente verwendet wird. Im Normalfall werden Sie diese Methoden in Ihrem Code nicht benötigen.  
  
## <a name="the-disposed-event"></a>Das "Disposed"-Ereignis  
 Das`DataSet` wird von der <xref:System.ComponentModel.MarshalByValueComponent> -Klasse abgeleitet, die sowohl die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> -Methode als auch das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis verfügbar macht. Die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis fügt einen Ereignishandler, um das "disposed"-Ereignis für die Komponente zu überwachen. Können Sie die <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis für ein `DataSet` Wenn ausgeführt werden soll code, wenn die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> Methode wird aufgerufen. <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>die verwendeten Ressourcen frei der <xref:System.ComponentModel.MarshalByValueComponent>.  
  
> [!NOTE]
>  Die `DataSet` und `DataTable` Objekte erben von <xref:System.ComponentModel.MarshalByValueComponent> und unterstützen die <xref:System.Runtime.Serialization.ISerializable> Schnittstelle für das Remoting. Dies sind die einzigen ADO.NET-Objekte, die remotingfähig sind. Weitere Informationen finden Sie unter [Remoteobjekte](http://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58).  
  
 Informationen zu anderen Ereignissen verfügbar, bei der Arbeit mit einem `DataSet`, finden Sie unter [Behandeln von DataTable-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) und [Behandeln von DataAdapter-Ereignissen](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Überprüfen von Daten](http://msdn.microsoft.com/library/b3a9ee4e-5d4d-4411-9c56-c811f2b4ee7e)  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
