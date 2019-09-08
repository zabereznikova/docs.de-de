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
# <a name="handling-dataset-events"></a>Behandeln von DataSet-Ereignissen
Das <xref:System.Data.DataSet> -Objekt stellt die folgenden drei Ereignisse bereit: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>und <xref:System.Data.DataSet.MergeFailed>.  
  
## <a name="the-mergefailed-event"></a>Das "MergeFailed"-Ereignis  
 Das am häufigsten verwendete Ereignis des `DataSet` -Objekts ist `MergeFailed`. Dieses Ereignis wird ausgelöst, wenn sich die Schemas der `DataSet` -Objekte, die zusammengeführt werden, widersprechen. Zu einem solchen Konflikt kommt es, wenn eine Ziel- und eine Quell- <xref:System.Data.DataRow> den gleichen Primärschlüsselwert besitzen und die <xref:System.Data.DataSet.EnforceConstraints%2A> -Eigenschaft auf `true`gesetzt ist. Wenn z. B. die zusammenzuführenden Primärschlüsselspalten einer Tabelle in den Tabellen der beiden `DataSet` -Objekte identisch sind, wird eine Ausnahme ausgegeben und das `MergeFailed` -Ereignis ausgelöst. Das <xref:System.Data.MergeFailedEventArgs> -Objekt, das an das `MergeFailed` -Ereignis übergeben wird, besitzt eine <xref:System.Data.MergeFailedEventArgs.Conflict%2A> -Eigenschaft, die den Konflikt im Schema der beiden `DataSet` -Objekte kennzeichnet, sowie eine <xref:System.Data.MergeFailedEventArgs.Table%2A> -Eigenschaft, die den Namen der Tabelle mit dem Konflikt angibt.  
  
 Das folgende Codefragment zeigt, wie ein Ereignishandler für das `MergeFailed` -Ereignis hinzugefügt werden kann.  
  
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
  
 Die <xref:System.Data.DataSet.IsInitialized%2A> -Eigenschaft gibt `true` zurück, wenn die Initialisierung vom `DataSet` abgeschlossen wurde. Andernfalls wird `false`zurückgegeben. Die <xref:System.Data.DataSet.BeginInit%2A> -Methode, die die Initialisierung eines `DataSet`startet, setzt <xref:System.Data.DataSet.IsInitialized%2A> auf `false`. Durch die <xref:System.Data.DataSet.EndInit%2A> -Methode, die die Initialisierung eines `DataSet`beendet, wird der Wert auf `true`gesetzt. Diese Methoden werden von der Visual Studio-Entwurfs Umgebung verwendet, um eine `DataSet` zu initialisieren, die von einer anderen Komponente verwendet wird. Im Normalfall werden Sie diese Methoden in Ihrem Code nicht benötigen.  
  
## <a name="the-disposed-event"></a>Das "Disposed"-Ereignis  
 Das`DataSet` wird von der <xref:System.ComponentModel.MarshalByValueComponent> -Klasse abgeleitet, die sowohl die <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> -Methode als auch das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis verfügbar macht. Das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Ereignis fügt einen Ereignishandler hinzu, der auf das verworfene Ereignis für die Komponente lauscht. Sie können das <xref:System.ComponentModel.MarshalByValueComponent.Disposed> -Ereignis `DataSet` eines verwenden, wenn Sie Code ausführen möchten, wenn <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> die-Methode aufgerufen wird. <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>Gibt die von <xref:System.ComponentModel.MarshalByValueComponent>verwendeten Ressourcen frei.  
  
> [!NOTE]
> Die `DataSet` - `DataTable` und-Objekte <xref:System.ComponentModel.MarshalByValueComponent> erben von und <xref:System.Runtime.Serialization.ISerializable> unterstützen die-Schnittstelle für Remoting. Dies sind die einzigen ADO.NET-Objekte, die remotingfähig sind. Weitere Informationen finden Sie unter [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).  
  
 Informationen zu anderen Ereignissen, die beim Arbeiten mit einem `DataSet`verfügbar sind, finden Sie unter [Verarbeiten von Daten](handling-datatable-events.md) und [Verarbeiten von DataAdapter-Ereignissen](../handling-dataadapter-events.md).  
  
## <a name="see-also"></a>Siehe auch

- [DataSets, DataTables und DataViews](index.md)
- [Überprüfen von Daten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
