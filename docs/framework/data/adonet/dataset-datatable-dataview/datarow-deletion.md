---
title: "\"DataRow\"-Löschung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 57f51ada00bf24617ca3e295a010aae64f0aa849
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196137"
---
# <a name="datarow-deletion"></a>"DataRow"-Löschung
Stehen zwei Methoden Sie löschen können eine <xref:System.Data.DataRow> -Objekt aus einer <xref:System.Data.DataTable> Objekt: die **entfernen** -Methode der der <xref:System.Data.DataRowCollection> -Objekt, und die <xref:System.Data.DataRow.Delete%2A> -Methode der der **DataRow**Objekt. Während der <xref:System.Data.DataRowCollection.Remove%2A> Methode löscht eine **DataRow** aus der **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> Methode wird nur die Zeile zum Löschen gekennzeichnet. Die tatsächlich entfernt, wenn die Anwendung ruft die **AcceptChanges** Methode. Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen. Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.  
  
 Beim Durchlaufen eines <xref:System.Data.DataRow.Delete%2A>-Objekts sollten weder <xref:System.Data.DataRowCollection.Remove%2A> noch <xref:System.Data.DataRowCollection> in einer foreach-Schleife aufgerufen werden. Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.  
  
 Bei Verwendung einer <xref:System.Data.DataSet> oder **DataTable** in Verbindung mit einer **DataAdapter** und einer relationalen Datenquelle, verwenden Sie die **löschen** -Methode der der  **DataRow** auf die Zeile zu entfernen. Die **löschen** Methode kennzeichnet die Zeile als **gelöschte** in die **DataSet** oder **DataTable** jedoch nicht entfernt. Stattdessen, wenn die **DataAdapter** findet eine Zeile, die als **gelöschte**, Ausführen der **DeleteCommand** Methode, um die Zeile in der Datenquelle zu löschen. Die Zeile kann dann dauerhaft entfernt werden mithilfe der **AcceptChanges** Methode. Bei Verwendung von **entfernen** zum Löschen der zeilenupdates die Zeile wird vollständig aus der Tabelle entfernt jedoch **DataAdapter** die Zeile in der Datenquelle werden nicht gelöscht.  
  
 Die **entfernen** Methode der **DataRowCollection** akzeptiert eine **DataRow** als Argument und entfernt sie aus der Auflistung, wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Im Gegensatz dazu wird im folgenden Beispiel wird veranschaulicht, wie zum Aufrufen der **löschen** Methode für eine **DataRow** so ändern Sie seine **RowState** zu **gelöschte** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Wenn eine Zeile zum Löschen markiert ist, und Sie rufen die **AcceptChanges** Methode der **DataTable** Objekt ist, wird die Zeile wurde aus entfernt die **DataTable**. Im Gegensatz dazu sind Aufrufen **RejectChanges**, **RowState** wiederhergestellt, bevor Sie als markiert wird, was sie die Zeile **gelöschte**.  
  
> [!NOTE]
>  Wenn die **RowState** von eine **DataRow** ist **Added**, d. h. sie gerade hinzugefügt wurde, in der Tabelle und wird dann als markiert **gelöschte**, ist aus der Tabelle entfernt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
