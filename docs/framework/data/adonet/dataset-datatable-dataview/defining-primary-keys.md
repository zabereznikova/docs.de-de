---
title: "Definieren von Prim&#228;rschl&#252;sseln | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Definieren von Prim&#228;rschl&#252;sseln
Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert.  Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.  
  
 Wenn Sie eine einzelne <xref:System.Data.DataColumn> als <xref:System.Data.DataTable.PrimaryKey%2A> für eine <xref:System.Data.DataTable> festlegen, setzt die Tabelle automatisch die <xref:System.Data.DataColumn.AllowDBNull%2A>\-Eigenschaft der Spalte auf **false** und die <xref:System.Data.DataColumn.Unique%2A>\-Eigenschaft auf **true**.  Bei Primärschlüsseln aus mehreren Spalten wird nur die **AllowDBNull**\-Eigenschaft automatisch auf **false** festgelegt.  
  
 Die **PrimaryKey**\-Eigenschaft einer <xref:System.Data.DataTable> erhält als Wert ein Array aus einem oder mehreren **DataColumn**\-Objekten. Dies wird in den folgenden Beispielen dargestellt.  Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 Im folgenden Beispiel werden zwei Spalten als Primärschlüssel definiert.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## Siehe auch  
 <xref:System.Data.DataTable>   
 ['DataTable'\-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)