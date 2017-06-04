---
title: "Behandlung von DataView-Ereignissen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Behandlung von DataView-Ereignissen
Sie können das <xref:System.Data.DataView.ListChanged>\-Ereignis von <xref:System.Data.DataView> verwenden, um festzustellen, ob eine Ansicht aktualisiert wurde.  Zu den Updatevorgängen, die das Ereignis auslösen, zählen das Hinzufügen, Löschen oder Ändern einer Zeile in einer zugrundeliegenden Tabelle, das Hinzufügen oder Löschen einer Spalte im Schema der zugrundeliegenden Tabelle und das Ausführen von Änderungen an einer über\- oder untergeordneten Beziehung.  Das **ListChanged**\-Ereignis benachrichtigt Sie auch, wenn die Liste der Zeilen, die Sie anzeigen, sich wesentlich aufgrund einer neuen Sortierreihenfolge oder eines Filters geändert hat.  
  
 Das **ListChanged**\-Ereignis implementiert den **ListChangedEventHandler**\-Delegaten des <xref:System.ComponentModel>\-Namespaces und akzeptiert als Eingabe ein <xref:System.ComponentModel.ListChangedEventArgs>\-Objekt.  Mit dem <xref:System.ComponentModel.ListChangedType>\-Enumerationswert in der **ListChangedType**\-Eigenschaft des **ListChangedEventArgs**\-Objekts können Sie die Art der Änderung feststellen.  Wenn bei einer Änderung Zeilen hinzugefügt, gelöscht oder verschoben wurden, können Sie mit der **NewIndex**\-Eigenschaft des **ListChangedEventArgs**\-Objekts auf den neuen Index der hinzugefügten oder verschobenen Zeile und den vorherigen Index der gelöschten Zeile zugreifen.  Wenn es sich um eine verschobene Zeile handelt, können Sie mit der **OldIndex**\-Eigenschaft des **ListChangedEventArgs**\-Objekts auf den vorherigen Index der verschobenen Zeile zugreifen.  
  
 Der **DataViewManager** macht auch ein **ListChanged**\-Ereignis verfügbar, um Sie zu benachrichtigen, wenn eine Tabelle hinzugefügt oder entfernt wurde oder wenn eine Änderung an der **Relations**\-Auflistung des zugrunde liegenden **DataSet** vorgenommen wurde.  
  
 Das folgende Beispiel zeigt, wie Sie einen **ListChanged**\-Ereignishandler hinzufügen:  
  
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
  
## Siehe auch  
 <xref:System.Data.DataView>   
 <xref:System.ComponentModel.ListChangedEventHandler>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)