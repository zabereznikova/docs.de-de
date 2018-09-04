---
title: Hinzufügen von Daten zu einer "DataTable"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: c1ebe2d735924c559f450f4041884dc9845e4fe0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514514"
---
# <a name="adding-data-to-a-datatable"></a>Hinzufügen von Daten zu einer "DataTable"
Nachdem Sie eine <xref:System.Data.DataTable> erstellt und deren Struktur mithilfe von Spalten und Einschränkungen definiert haben, können Sie der Tabelle neue Datenzeilen hinzufügen. Dazu deklarieren Sie eine neue Variable als <xref:System.Data.DataRow>-Typ. Ein neues **DataRow** Objekt wird zurückgegeben, beim Aufrufen der <xref:System.Data.DataTable.NewRow%2A> Methode. Die **DataTable** erstellt dann die **DataRow** Objekt entsprechend der Struktur der Tabelle gemäß den <xref:System.Data.DataColumnCollection>.  
  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen einer neuen Zeile durch Aufrufen der **NewRow** Methode.  
  
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
  
 Nachdem die Daten in der neuen Zeile eingefügt werden die **hinzufügen** Methode dient zum Hinzufügen der Zeile, die <xref:System.Data.DataRowCollection>, wie im folgenden Code gezeigt.  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Sie können auch aufrufen, die **hinzufügen** Methode, um eine neue Zeile hinzuzufügen, durch die Übergabe in einem Array von Werten, die als typisierte <xref:System.Object>, wie im folgenden Beispiel gezeigt.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Übergibt ein Array von Werten als **Objekt**, zu der **hinzufügen** Methode erstellt eine neue Zeile in der Tabelle und als Spaltenwerte werden auf die Werte im Objektarray. Beachten Sie, dass Werte in dem Array nacheinander den Spalten zugeordnet werden, und zwar in der Reihenfolge, in der sie in der Tabelle vorkommen.  
  
 Im folgenden Beispiel wird 10 Zeilen, auf das neu erstellte **Kunden** Tabelle.  
  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
