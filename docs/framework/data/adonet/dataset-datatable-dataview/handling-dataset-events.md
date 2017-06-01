---
title: "Behandeln von DataSet-Ereignissen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Behandeln von DataSet-Ereignissen
Das <xref:System.Data.DataSet>\-Objekt stellt die folgenden drei Ereignisse bereit: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized> und <xref:System.Data.DataSet.MergeFailed>.  
  
## Das "MergeFailed"\-Ereignis  
 Das am häufigsten verwendete Ereignis des `DataSet`\-Objekts ist `MergeFailed`. Dieses Ereignis wird ausgelöst, wenn sich die Schemas der `DataSet`\-Objekte, die zusammengeführt werden, widersprechen. Zu einem solchen Konflikt kommt es, wenn eine Ziel\- und eine Quell\-<xref:System.Data.DataRow> den gleichen Primärschlüsselwert besitzen und die <xref:System.Data.DataSet.EnforceConstraints%2A>\-Eigenschaft auf `true` gesetzt ist. Wenn z. B. die zusammenzuführenden Primärschlüsselspalten einer Tabelle in den Tabellen der beiden `DataSet`\-Objekte identisch sind, wird eine Ausnahme ausgegeben und das `MergeFailed`\-Ereignis ausgelöst. Das <xref:System.Data.MergeFailedEventArgs>\-Objekt, das an das `MergeFailed`\-Ereignis übergeben wird, besitzt eine <xref:System.Data.MergeFailedEventArgs.Conflict%2A>\-Eigenschaft, die den Konflikt im Schema der beiden `DataSet`\-Objekte kennzeichnet, sowie eine <xref:System.Data.MergeFailedEventArgs.Table%2A>\-Eigenschaft, die den Namen der Tabelle mit dem Konflikt angibt.  
  
 Das folgende Codefragment zeigt, wie ein Ereignishandler für das `MergeFailed`\-Ereignis hinzugefügt werden kann.  
  
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
  
## Das "Initialized"\-Ereignis  
 Das <xref:System.Data.DataSet.Initialized>\-Ereignis tritt ein, nachdem der `DataSet`\-Konstruktor eine neue Instanz vom `DataSet` initialisiert hat.  
  
 Die <xref:System.Data.DataSet.IsInitialized%2A>\-Eigenschaft gibt `true` zurück, wenn die Initialisierung vom `DataSet` abgeschlossen wurde. Andernfalls wird `false` zurückgegeben. Die <xref:System.Data.DataSet.BeginInit%2A>\-Methode, die die Initialisierung eines `DataSet` startet, setzt <xref:System.Data.DataSet.IsInitialized%2A> auf `false`. Durch die <xref:System.Data.DataSet.EndInit%2A>\-Methode, die die Initialisierung eines `DataSet` beendet, wird der Wert auf `true` gesetzt. Diese Methoden werden von der [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]\-Entwicklungsumgebung zum Initialisieren eines `DataSet` genutzt, das von einer anderen Komponente verwendet wird. Im Normalfall werden Sie diese Methoden in Ihrem Code nicht benötigen.  
  
## Das "Disposed"\-Ereignis  
 Das `DataSet` wird von der <xref:System.ComponentModel.MarshalByValueComponent>\-Klasse abgeleitet, die sowohl die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>\-Methode als auch das <xref:System.ComponentModel.MarshalByValueComponent.Disposed>\-Ereignis verfügbar macht. Mit dem <xref:System.ComponentModel.MarshalByValueComponent.Disposed>\-Ereignis wird ein Ereignishandler hinzugefügt, der die Komponente auf das Eintreten des Disposed\-Ereignisses lauscht. Sie können das <xref:System.ComponentModel.MarshalByValueComponent.Disposed>\-Ereignis eines `DataSet` verwenden, wenn beim Aufrufen der <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>\-Methode Code ausgeführt werden soll.<xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> gibt die von der <xref:System.ComponentModel.MarshalByValueComponent> verwendeten Ressourcen frei.  
  
> [!NOTE]
>  Das `DataSet`\-Objekt und das `DataTable`\-Objekt erben von <xref:System.ComponentModel.MarshalByValueComponent> und unterstützen die <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle für das Remoting. Dies sind die einzigen ADO.NET\-Objekte, die remotingfähig sind. Weitere Informationen finden Sie unter [Remote Objects](http://msdn.microsoft.com/de-de/515686e6-0a8d-42f7-8188-73abede57c58).  
  
 Informationen zu weiteren verfügbaren Ereignissen beim Arbeiten mit einem `DataSet` finden Sie unter [Behandlung von DataTable\-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) und [Umgang mit 'DataAdapter'\-Ereignissen](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Überprüfen von Daten](../Topic/Validating%20Data.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)