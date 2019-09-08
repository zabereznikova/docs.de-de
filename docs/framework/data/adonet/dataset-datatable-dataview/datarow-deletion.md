---
title: "\"DataRow\"-Löschung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 3f48339539f08bbc1c2c15035741375bd9ade553
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784724"
---
# <a name="datarow-deletion"></a>"DataRow"-Löschung
Es gibt zwei Methoden zum <xref:System.Data.DataRow> Löschen eines-Objekts aus einem <xref:System.Data.DataTable> -Objekt: <xref:System.Data.DataRowCollection> die **Remove** -Methode des-Objekts und die <xref:System.Data.DataRow.Delete%2A> -Methode des **DataRow** -Objekts. Während die <xref:System.Data.DataRowCollection.Remove%2A> -Methode eine **DataRow** aus der **DataRowCollection**löscht, <xref:System.Data.DataRow.Delete%2A> markiert die Methode nur die Zeile zum Löschen. Das eigentliche Entfernen tritt auf, wenn die Anwendung die Methode " **akzeptchanges** " aufruft. Mithilfe von <xref:System.Data.DataRow.Delete%2A> können Sie programmgesteuert überprüfen, welche Zeilen zum Löschen markiert sind, bevor Sie sie tatsächlich entfernen. Wenn eine Zeile zum Löschen markiert ist, wird deren <xref:System.Data.DataRow.RowState%2A>-Eigenschaft auf <xref:System.Data.DataRow.Delete%2A> festgelegt.  
  
 Beim Durchlaufen eines <xref:System.Data.DataRow.Delete%2A>-Objekts sollten weder <xref:System.Data.DataRowCollection.Remove%2A> noch <xref:System.Data.DataRowCollection> in einer foreach-Schleife aufgerufen werden. Der Auflistungszustand wird durch <xref:System.Data.DataRow.Delete%2A> und <xref:System.Data.DataRowCollection.Remove%2A> nicht geändert.  
  
 Wenn Sie eine <xref:System.Data.DataSet> -oder- **Daten** Tabelle zusammen mit einem **DataAdapter** und einer relationalen Datenquelle verwenden, verwenden Sie die **Delete** -Methode der **DataRow** , um die Zeile zu entfernen. Die **Delete** -Methode markiert die Zeile als **gelöscht** im **DataSet** oder **in der Datentabelle** , entfernt Sie jedoch nicht. Wenn der **DataAdapter** auf eine Zeile stößt, die als **gelöscht**markiert ist, führt er stattdessen seine **DeleteCommand** -Methode aus, um die Zeile in der Datenquelle zu löschen. Die Zeile kann dann mithilfe der Methode " **Accept tchanges** " dauerhaft entfernt werden. Wenn Sie zum Löschen der Zeile " **Entfernen** " verwenden, wird die Zeile vollständig aus der Tabelle entfernt, aber der **DataAdapter** löscht die Zeile nicht in der Datenquelle.  
  
 Die **Remove** -Methode der **DataRowCollection** übernimmt eine **DataRow** als Argument und entfernt Sie aus der Auflistung, wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Im Gegensatz dazu wird im folgenden Beispiel veranschaulicht, wie die **Delete** -Methode für eine **DataRow** aufgerufen wird, um den **RowState** in " **deleted**" zu ändern.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Wenn eine Zeile zum Löschen markiert ist und Sie die **Accept-Changes** -Methode des **datbare** -Objekts aufzurufen, wird die Zeile aus der **Daten**Tabelle entfernt. Wenn Sie dagegen **RejectChanges**aufrufen, wird der **RowState** der Zeile auf den Wert zurückgesetzt, der vor der Markierung als **gelöscht**markiert wurde.  
  
> [!NOTE]
> Wenn der **RowState** einer **DataRow** **hinzugefügt**wird, was bedeutet, dass Sie der Tabelle soeben hinzugefügt wurde und dann als **gelöscht**markiert ist, wird Sie aus der Tabelle entfernt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Bearbeiten von Daten in einer DataTable](manipulating-data-in-a-datatable.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
