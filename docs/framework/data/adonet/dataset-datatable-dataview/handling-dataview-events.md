---
title: Behandeln von DataView-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 2f30a578c5233e8b86a165dd220efd45348c5042
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44088010"
---
# <a name="handling-dataview-events"></a>Behandeln von DataView-Ereignissen
Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde. Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung. Die **ListChanged** Ereignis ebenfalls eine Benachrichtigung, wenn die Liste der angezeigten Zeilen aufgrund einer neuen Sortierreihenfolge oder ein Filter erheblich geändert hat.  
  
 Die **ListChanged** Ereignis implementiert die **ListChangedEventHandler** -Delegaten des der <xref:System.ComponentModel> Namespaces und akzeptiert als Eingabe eine <xref:System.ComponentModel.ListChangedEventArgs> Objekt. Können Sie bestimmen, welche Art von Änderung aufgetreten ist, mit der <xref:System.ComponentModel.ListChangedType> Enumerationswert in der **ListChangedType** Eigenschaft der **ListChangedEventArgs** Objekt. Änderungen, bei denen hinzufügen, löschen oder Verschieben von Zeilen, den neuen Index der hinzugefügten oder verschobenen Zeile und den vorherigen Index der gelöschten Zeile zugegriffen werden kann mithilfe der **NewIndex** Eigenschaft der **ListChangedEventArgs** Objekt. Im Fall von einer verschobenen Zeile der vorherige Index der verschobenen Zeile erfolgen kann mithilfe der **OldIndex** Eigenschaft der **ListChangedEventArgs** Objekt.  
  
 Der **DataViewManager** macht auch eine **ListChanged** Ereignis, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurden oder auf eine Änderung vorgenommen wurde der **Beziehungen** Auflistung von der zugrunde liegende **DataSet**.  
  
 Das folgende Codebeispiel veranschaulicht das Hinzufügen einer **ListChanged** -Ereignishandler.  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
