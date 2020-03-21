---
title: Behandeln von DataView-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b625fad846c4c6cf008843bff1f6b0eabe0e1de4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151103"
---
# <a name="handling-dataview-events"></a>Behandeln von DataView-Ereignissen
Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde. Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung. Das **ListChanged-Ereignis** benachrichtigt Sie auch, wenn sich die Liste der angezeigten Zeilen aufgrund der Anwendung einer neuen Sortierreihenfolge oder eines Filters erheblich geändert hat.  
  
 Das **ListChanged-Ereignis** implementiert den **ListChangedEventHandler-Delegaten** des <xref:System.ComponentModel> <xref:System.ComponentModel.ListChangedEventArgs> Namespace und nimmt als Eingabe ein Objekt an. Sie können mithilfe des <xref:System.ComponentModel.ListChangedType> Enumerationswerts in der **ListChangedType-Eigenschaft** des **ListChangedEventArgs-Objekts** bestimmen, welche Art von Änderung aufgetreten ist. Bei Änderungen, die das Hinzufügen, Löschen oder Verschieben von Zeilen beinhalten, kann über die **NewIndex-Eigenschaft** des **ListChangedEventArgs-Objekts** auf den neuen Index der hinzugefügten oder verschobenen Zeile und auf den vorherigen Index der gelöschten Zeile zugegriffen werden. Im Fall einer verschobenen Zeile kann mit der **OldIndex-Eigenschaft** des **ListChangedEventArgs-Objekts** auf den vorherigen Index der verschobenen Zeile zugegriffen werden.  
  
 **Der DataViewManager** macht auch ein **ListChanged-Ereignis** verfügbar, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde oder ob eine Änderung an der **Relations-Auflistung** des zugrunde liegenden **DataSet**vorgenommen wurde.  
  
 Das folgende Codebeispiel zeigt, wie Sie einen **ListChanged-Ereignishandler** hinzufügen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- ["DataViews"](dataviews.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
