---
title: "Erstellen von AutoIncrement-Spalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Erstellen von AutoIncrement-Spalten
Um sicherzustellen, dass die Werte in einer Spalte eindeutig sind, können Sie festlegen, dass die Spaltenwerte automatisch erhöht werden, wenn der Tabelle neue Zeilen hinzugefügt werden.  Um eine <xref:System.Data.DataColumn> mit automatischer Inkrementierung zu erstellen, legen Sie die <xref:System.Data.DataColumn.AutoIncrement%2A>\-Eigenschaft der Spalte auf **true** fest.  Die <xref:System.Data.DataColumn> beginnt dann mit dem Wert, der in der <xref:System.Data.DataColumn.AutoIncrementSeed%2A>\-Eigenschaft definiert wurde, und mit jeder hinzugefügten Zeile erhöht sich der Wert der **AutoIncrement**\-Spalte um den Wert, der in der <xref:System.Data.DataColumn.AutoIncrementStep%2A>\-Eigenschaft der Spalte definiert wurde.  
  
 Für **AutoIncrement**\-Spalten wird empfohlen, dass die <xref:System.Data.DataColumn.ReadOnly%2A>\-Eigenschaft der **DataColumn** auf **true** festgelegt wird.  
  
 Im folgenden Beispiel wird veranschaulicht, wie eine Spalte erstellt wird, die mit dem Wert 200 beginnt und deren Werte inkrementell jeweils um 3 erhöht werden.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## Siehe auch  
 <xref:System.Data.DataColumn>   
 ['DataTable'\-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)