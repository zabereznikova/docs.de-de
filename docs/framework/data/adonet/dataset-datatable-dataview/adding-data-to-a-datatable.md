---
title: Hinzufügen von Daten zu einer "DataTable"
description: Weitere Informationen zum Hinzufügen neuer Daten Zeilen zu einer Tabelle in ADO.net finden Sie in diesem Beispielcode, nachdem Sie eine Datentabelle erstellt und ihre Struktur mithilfe von Spalten und Einschränkungen definiert haben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 94ebc97d5f90b5bb92186ba6f33015633bd01127
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286933"
---
# <a name="adding-data-to-a-datatable"></a>Hinzufügen von Daten zu einer "DataTable"
Nachdem Sie eine <xref:System.Data.DataTable> erstellt und deren Struktur mithilfe von Spalten und Einschränkungen definiert haben, können Sie der Tabelle neue Datenzeilen hinzufügen. Dazu deklarieren Sie eine neue Variable als <xref:System.Data.DataRow>-Typ. Ein neues **DataRow** -Objekt wird zurückgegeben, wenn Sie die- <xref:System.Data.DataTable.NewRow%2A> Methode aufrufen. Die **Daten** Tabelle erstellt dann das **DataRow** -Objekt basierend auf der Struktur der Tabelle, wie im definiert <xref:System.Data.DataColumnCollection> .  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine neue Zeile durch Aufrufen der **NewRow** -Methode erstellt wird.  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 Anschließend können Sie die neu hinzugefügte Zeile mithilfe eines Indexes oder des Spaltennamens bearbeiten, wie im folgenden Beispiel gezeigt.  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 Nachdem die Daten in die neue Zeile eingefügt wurden, wird die-Methode mithilfe der **Add** -Methode der hinzugefügt <xref:System.Data.DataRowCollection> , wie im folgenden Code dargestellt.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Sie können auch die **Add** -Methode zum Hinzufügen einer neuen Zeile hinzufügen, indem Sie ein Array von Werten übergeben, die als typisiert sind <xref:System.Object> , wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Wenn Sie ein Array von Werten, die als **Object**eingegeben werden, an die **Add** -Methode übergeben, wird eine neue Zeile in der Tabelle erstellt, und die Spaltenwerte werden auf die Werte im Objekt Array festgelegt. Beachten Sie, dass Werte in dem Array nacheinander den Spalten zugeordnet werden, und zwar in der Reihenfolge, in der sie in der Tabelle vorkommen.  
  
 Im folgenden Beispiel werden der neu erstellten **Customers** -Tabelle 10 Zeilen hinzugefügt.  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Bearbeiten von Daten in einer "DataTable"](manipulating-data-in-a-datatable.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
