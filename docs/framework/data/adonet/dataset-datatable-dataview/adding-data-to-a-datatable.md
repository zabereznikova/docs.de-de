---
title: "Hinzuf&#252;gen von Daten zu einer &#39;DataTable&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Hinzuf&#252;gen von Daten zu einer &#39;DataTable&#39;
Nachdem Sie eine <xref:System.Data.DataTable> erstellt und deren Struktur mithilfe von Spalten und Einschränkungen definiert haben, können Sie der Tabelle neue Datenzeilen hinzufügen.  Dazu deklarieren Sie eine neue Variable als <xref:System.Data.DataRow>\-Typ.  Ein neues **DataRow**\-Objekt wird beim Aufrufen der <xref:System.Data.DataTable.NewRow%2A>\-Methode zurückgegeben.  In der **DataTable** wird anschließend das **DataRow**\-Objekt anhand der durch die <xref:System.Data.DataColumnCollection> definierten Tabellenstruktur erstellt.  
  
 Das folgende Beispiel veranschaulicht, wie durch Aufrufen der **NewRow**\-Methode eine neue Zeile erstellt wird.  
  
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
  
 Nach dem Einfügen von Daten in die neue Zeile wird die Zeile mithilfe der **Add**\-Methode der <xref:System.Data.DataRowCollection> hinzugefügt, wie im folgenden Codebeispiel gezeigt.  
  
```vb  
workTable.Rows.Add(workRow)  
  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 Sie können die **Add**\-Methode auch aufrufen, um eine neue Zeile hinzuzufügen, indem Sie ein Array aus Werten als <xref:System.Object>\-Typ übergeben, wie das folgende Beispiel zeigt.  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 Durch Übergeben eines Arrays aus Werten als **Object**\-Typ an die **Add**\-Methode wird eine neue Zeile innerhalb der Tabelle erstellt, und als Spaltenwerte werden die Werte in dem Objektarray festgelegt.  Beachten Sie, dass Werte in dem Array nacheinander den Spalten zugeordnet werden, und zwar in der Reihenfolge, in der sie in der Tabelle vorkommen.  
  
 Im folgenden Beispiel werden der neu erstellten **Customers**\-Tabelle zehn Zeilen hinzugefügt.  
  
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
  
## Siehe auch  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)