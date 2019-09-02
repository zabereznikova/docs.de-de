---
title: Behandeln von DataView-Ereignissen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b3a1077bff9bf457b4aef0b05357d4a9260f8973
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204825"
---
# <a name="handling-dataview-events"></a>Behandeln von DataView-Ereignissen
Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde. Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung. Das **ListChanged** -Ereignis benachrichtigt Sie auch, wenn sich die Liste der Zeilen, die Sie anzeigen, aufgrund der Anwendung einer neuen Sortierreihenfolge oder eines Filters erheblich geändert hat.  
  
 Das **ListChanged** -Ereignis implementiert den **listchangedebug-thandler** -Delegaten des <xref:System.ComponentModel> -Namespace und übernimmt als Eingabe ein <xref:System.ComponentModel.ListChangedEventArgs> -Objekt. Sie können mit dem <xref:System.ComponentModel.ListChangedType> -Enumerationswert in der **ListChangedType** -Eigenschaft des **ListChangedEventArgs** -Objekts ermitteln, welche Art von Änderung aufgetreten ist. Bei Änderungen, die das Hinzufügen, löschen oder Verschieben von Zeilen einschließen, kann auf den neuen Index der hinzugefügten oder verschobenen Zeile und den vorherigen Index der gelöschten Zeile mithilfe der Eigenschaft " **netwindex** " des **ListChangedEventArgs** -Objekts zugegriffen werden. Im Fall einer verschobene Zeile kann auf den vorherigen Index der verschobene Zeile mithilfe der **OldIndex** -Eigenschaft des **ListChangedEventArgs** -Objekts zugegriffen werden.  
  
 Der **DataViewManager** macht auch ein **ListChanged** -Ereignis verfügbar, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde, oder wenn eine Änderung an der **Beziehungs** Auflistung des zugrunde liegenden **DataSets**vorgenommen wurde.  
  
 Im folgenden Codebeispiel wird gezeigt, wie ein **ListChanged** -Ereignishandler hinzugefügt wird.  
  
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

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [DataViews](dataviews.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
