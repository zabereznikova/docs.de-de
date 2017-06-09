---
title: "DataRow-L&#246;schung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# DataRow-L&#246;schung
Es gibt zwei Methoden zum Löschen eines <xref:System.Data.DataRow>\-Objekts aus einem <xref:System.Data.DataTable>\-Objekt: die **Remove**\-Methode des <xref:System.Data.DataRowCollection>\-Objekts und die <xref:System.Data.DataRow.Delete%2A>\-Methode des **DataRow**\-Objekts.  Während die <xref:System.Data.DataRowCollection.Remove%2A>\-Methode eine **DataRow** aus der **DataRowCollection** löscht, wird die Zeile mit der <xref:System.Data.DataRow.Delete%2A>\-Methode lediglich zum Löschen markiert.  Das eigentliche Löschen erfolgt, wenn die Anwendung die **AcceptChanges**\-Methode aufruft.  Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen.  Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>\-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.  
  
 Beim Durchlaufen eines <xref:System.Data.DataRowCollection>\-Objekts sollten weder <xref:System.Data.DataRow.Delete%2A> noch <xref:System.Data.DataRowCollection.Remove%2A> in einer foreach\-Schleife aufgerufen werden.  Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.  
  
 Bei Verwendung eines <xref:System.Data.DataSet> oder einer **DataTable** in Verbindung mit einem **DataAdapter** und einer relationalen Datenquelle entfernen Sie die Zeile mithilfe der **Delete**\-Methode der **DataRow**.  Mit der **Delete**\-Methode wird die Zeile als **Deleted** im **DataSet** oder in der **DataTable** markiert, aber sie wird nicht entfernt.  Wenn stattdessen der **DataAdapter** eine als **Deleted** markierte Zeile vorfindet, führt er die **DeleteCommand**\-Methode aus, um die Zeile in der Datenquelle zu löschen.  Anschließend kann die Zeile mit der **AcceptChanges**\-Methode dauerhaft entfernt werden.  Wenn Sie zum Löschen der Zeile **Remove** verwenden, wird die Zeile zwar vollständig aus der Tabelle entfernt, vom **DataAdapter** jedoch nicht aus der Datenquelle gelöscht.  
  
 Die **Remove**\-Methode der **DataRowCollection** akzeptiert eine **DataRow** als Argument und entfernt sie aus der Auflistung, wie im folgenden Beispiel dargestellt.  
  
```vb  
workTable.Rows.Remove(workRow)  
  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Im Gegensatz dazu zeigt das folgende Beispiel, wie Sie die **Delete**\-Methode für eine **DataRow** aufrufen, um deren **RowState** auf **Deleted** zu ändern.  
  
```vb  
workRow.Delete  
  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Wenn eine Zeile zum Löschen markiert ist und Sie die **AcceptChanges**\-Methode des **DataTable**\-Objekts aufrufen, wird die Zeile aus der **DataTable** entfernt.  	Im Gegensatz dazu wird beim Aufrufen von **RejectChanges** der **RowState** der Zeile wiederhergestellt, der gültig war, bevor die Zeile als **Deleted** markiert wurde.  
  
> [!NOTE]
>  Wenn der **RowState** einer **DataRow** **Added** lautet, in dem Sinne, dass sie gerade der Tabelle hinzugefügt wurde, und dann als **Deleted** markiert wurde, wird sie aus der Tabelle entfernt.  
  
## Siehe auch  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)