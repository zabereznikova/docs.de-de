---
title: Behandeln von DataView-Ereignissen
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
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2abade8bbbf5ab8a9d2cf146271e89703ec34cb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="handling-dataview-events"></a>Behandeln von DataView-Ereignissen
Sie können das <xref:System.Data.DataView.ListChanged>-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde. Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über- oder untergeordneten Beziehung. Die **ListChanged** Ereignis benachrichtigt Sie auch, wenn die Liste der angezeigten Zeilen aufgrund einer neuen Sortierreihenfolge oder ein Filter erheblich geändert hat.  
  
 Die **ListChanged** Ereignis implementiert die **ListChangedEventHandler** delegieren, der die <xref:System.ComponentModel> Namespaces und akzeptiert als Eingabe eine <xref:System.ComponentModel.ListChangedEventArgs> Objekt. Können Sie ermitteln, welche Art von Änderung aufgetreten ist mit der <xref:System.ComponentModel.ListChangedType> Enumerationswert in der **ListChangedType** Eigenschaft von der **ListChangedEventArgs** Objekt. Informationen zu Änderungen, bei denen hinzufügen, löschen oder Verschieben von Zeilen, den neuen Index der hinzugefügten oder verschobenen Zeile und den vorherigen Index der gelöschten Zeile zugegriffen werden kann mithilfe der **NewIndex** Eigenschaft von der **ListChangedEventArgs** Objekt. Eine verschobene Zeile der vorherige Index der verschobenen Zeile möglich, die mithilfe der **OldIndex** Eigenschaft von der **ListChangedEventArgs** Objekt.  
  
 Die **DataViewManager** macht auch eine **ListChanged** Ereignis, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde, oder um eine Änderung vorgenommen wurde die **Beziehungen** Auflistung von der zugrunde liegende **DataSet**.  
  
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
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
