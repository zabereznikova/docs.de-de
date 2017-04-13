---
title: "Erstellen einer DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Erstellen einer DataView
Es gibt zwei Möglichkeiten zum Erstellen einer <xref:System.Data.DataView>:  Sie können den **DataView**\-Konstruktor verwenden, oder Sie können einen Verweis auf die <xref:System.Data.DataTable.DefaultView%2A>\-Eigenschaft der <xref:System.Data.DataTable> erstellen.  Der **DataView**\-Konstruktor kann leer sein oder akzeptiert entweder eine **DataTable** als einzelnes Argument oder eine **DataTable** zusammen mit Filterkriterien, Sortierkriterien und einem Zeilenstatusfilter.  Weitere Informationen zu zusätzlichen Argumenten, die mit der **DataView** verwendet werden können, finden Sie unter [Sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Weil der Index für eine **DataView** sowohl bei der Erstellung der **DataView** als auch bei Änderung einer der Eigenschaften **Sort**, **RowFilter** oder **RowStateFilter** aufgebaut wird, erzielen Sie bei der Erstellung der **DataView** die beste Leistung, wenn alle anfänglichen Sortierreihenfolge\- oder Filterkriterien als Konstruktorargumente bereitgestellt werden.  Wenn eine **DataView** ohne Angabe von Sortierungs\- oder Filterkriterien erstellt und die Eigenschaften **Sort**, **RowFilter** oder **RowStateFilter** später festgelegt werden, wird der Index mindestens zweimal erstellt: einmal, wenn der **DataView** erstellt wird, und dann erneut, wenn eine Sortierungs\- oder Filtereigenschaft bearbeitet wird.  
  
 Beachten Sie Folgendes: Wenn eine **DataView** mithilfe des Konstruktors erstellt wird, der keine Argumente akzeptiert, können Sie die **DataView** erst verwenden, wenn die **Table**\-Eigenschaft festgelegt wurde.  
  
 Im folgenden Beispiel wird das Erstellen einer **DataView** mithilfe des **DataView**\-Konstruktors veranschaulicht.  Eine **RowFilter**\-Spalte, eine **Sort**\-Spalte sowie **DataViewRowState** werden gemeinsam mit **DataTable** bereitgestellt.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie einen Verweis auf eine Standard\-**DataView** einer **DataTable** mithilfe der **DefaultView**\-Eigenschaft der Tabelle erhalten.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## Siehe auch  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)