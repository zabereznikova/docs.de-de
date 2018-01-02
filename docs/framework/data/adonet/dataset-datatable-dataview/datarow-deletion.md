---
title: "\"DataRow\"-Löschung"
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
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7f20fdebe101665e681597db0c55b7ced7853f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="datarow-deletion"></a>"DataRow"-Löschung
Stehen zwei Methoden, die Sie löschen können eine <xref:System.Data.DataRow> -Objekt aus einer <xref:System.Data.DataTable> Objekt: der **entfernen** Methode der <xref:System.Data.DataRowCollection> -Objekt, und die <xref:System.Data.DataRow.Delete%2A> Methode der **DataRow**Objekt. Während der <xref:System.Data.DataRowCollection.Remove%2A> -Methode löscht eine **DataRow** aus der **DataRowCollection**, die <xref:System.Data.DataRow.Delete%2A> Methode nur die Zeile zum Löschen markiert. Das eigentliche löschen erfolgt, wenn die Anwendung aufruft, die **AcceptChanges** Methode. Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen. Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.  
  
 Beim Durchlaufen eines <xref:System.Data.DataRow.Delete%2A>-Objekts sollten weder <xref:System.Data.DataRowCollection.Remove%2A> noch <xref:System.Data.DataRowCollection> in einer foreach-Schleife aufgerufen werden. Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.  
  
 Bei Verwendung einer <xref:System.Data.DataSet> oder **DataTable** in Verbindung mit einer **"DataAdapter"** und einer relationalen Datenquelle verwenden die **löschen** Methode der  **DataRow** zum Entfernen der Zeile. Die **löschen** Methode markiert die Zeile als **gelöschte** in der **DataSet** oder **DataTable** jedoch nicht entfernt. Stattdessen, wenn die **"DataAdapter"** als markierte Zeile stößt **gelöschte**, führt er seine **DeleteCommand** Methode, um die Zeile in der Datenquelle zu löschen. Die Zeile kann dann dauerhaft entfernt mithilfe der **AcceptChanges** Methode. Bei Verwendung von **entfernen** um die Zeile zu löschen, wird die Zeile entfernt, vollständig aus der Tabelle, aber die **"DataAdapter"** löscht die Zeile in der Datenquelle.  
  
 Die **entfernen** Methode der **DataRowCollection** nimmt eine **DataRow** als Argument und entfernt es aus der Auflistung, wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Im Gegensatz dazu das folgende Beispiel veranschaulicht das Aufrufen der **löschen** Methode auf eine **DataRow** so ändern Sie die **RowState** auf **gelöschte** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Wenn eine Zeile zum Löschen markiert ist, und Sie rufen die **AcceptChanges** Methode der **DataTable** -Objekt, aus der Zeile entfernt die **DataTable**. Im Gegensatz dazu sind beim Aufrufen **RejectChanges**, **RowState** der Zeile wird zurückgesetzt, bevor als markiert war **gelöschte**.  
  
> [!NOTE]
>  Wenn die **RowState** von einer **DataRow** ist **Added**, d. h. sie hat gerade der Tabelle hinzugefügt wurde, und wird dann als markiert **gelöschte**, ist aus der Tabelle entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
