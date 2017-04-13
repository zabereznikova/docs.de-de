---
title: "Hinzuf&#252;gen von &#39;DataRelations&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Hinzuf&#252;gen von &#39;DataRelations&#39;
In einem <xref:System.Data.DataSet> mit mehreren <xref:System.Data.DataTable>\-Objekten können Sie mithilfe von <xref:System.Data.DataRelation>\-Objekten eine Beziehung zwischen zwei Tabellen herstellen, um durch die Tabellen navigieren und untergeordnete oder übergeordnete Zeilen aus einer verknüpften Tabelle zurückgeben zu können.  
  
 Die zum Erstellen einer **DataRelation** erforderlichen Argumente sind ein Name für die zu erstellende **DataRelation** und ein Array aus einem oder mehreren <xref:System.Data.DataColumn>\-Verweisen auf die Spalten, die als übergeordnete und untergeordnete Spalten in der Beziehung vorliegen.  Nach dem Erstellen einer **DataRelation** können Sie damit zwischen den Tabellen navigieren und Werte abrufen.  
  
 Beim Hinzufügen einer **DataRelation** zu einem <xref:System.Data.DataSet> wird standardmäßig der übergeordneten Tabelle eine <xref:System.Data.UniqueConstraint> und der untergeordneten Tabelle eine <xref:System.Data.ForeignKeyConstraint> hinzugefügt.  Weitere Informationen zu diesen Standardeinschränkungen finden Sie unter ['DataTable'\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Im folgenden Codebeispiel wird eine **DataRelation** mithilfe von zwei <xref:System.Data.DataTable>\-Objekten in einem <xref:System.Data.DataSet> erstellt.  Jede <xref:System.Data.DataTable> enthält eine Spalte mit dem Namen **CustID**, die als Verknüpfung zwischen den beiden <xref:System.Data.DataTable>\-Objekten fungiert.  Im Beispiel wird der **Relations**\-Auflistung des <xref:System.Data.DataSet> eine einzelne **DataRelation** hinzugefügt.  Durch das erste Argument im Beispiel wird der Name der zu erstellenden **DataRelation** festgelegt.  Das zweite Argument legt die übergeordnete **DataColumn** fest, während das dritte Argument die untergeordnete **DataColumn** festlegt.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 Eine **DataRelation** verfügt auch über eine **Nested**\-Eigenschaft. Wenn für diese Eigenschaft **true** festgelegt ist, werden die Zeilen der untergeordneten Tabelle innerhalb der verknüpften Zeile der übergeordneten Tabelle geschachtelt, wenn sie mit <xref:System.Data.DataSet.WriteXml%2A> als XML\-Elemente geschrieben werden.  Weitere Informationen finden Sie unter [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)