---
title: "Zusammenfassung des R&#252;ckschlussprozesses von DataSet-Schemas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zusammenfassung des R&#252;ckschlussprozesses von DataSet-Schemas
Während des Rückschlussprozesses wird zunächst anhand des XML\-Dokuments bestimmt, welche Elemente als Tabellen hergeleitet werden.  Anschließend werden aus der übrigen XML die Spalten für diese Tabellen ermittelt.  Bei geschachtelten Tabellen werden beim Rückschlussprozess geschachtelte <xref:System.Data.DataRelation>\-Objekte und geschachtelte <xref:System.Data.ForeignKeyConstraint>\-Objekte erstellt.  
  
 Im Folgenden finden Sie eine kurze Zusammenfassung der Rückschlussregeln:  
  
-   Elemente mit Attributen werden als Tabellen hergeleitet.  
  
-   Elemente mit untergeordneten Elementen werden als Tabellen hergeleitet.  
  
-   Sich wiederholende Elemente werden als einzelne Tabelle hergeleitet.  
  
-   Ein Dokument\- oder Stammelement, das keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet würden, wird als <xref:System.Data.DataSet> hergeleitet.  Andernfalls wird das Dokumentelement als Tabelle hergeleitet.  
  
-   Attribute werden als Spalten hergeleitet.  
  
-   Elemente, die keine Attribute oder untergeordnete Elemente aufweisen und sich nicht wiederholen, werden als Spalten hergeleitet.  
  
-   Bei Elementen, die in anderen, ebenfalls als Tabellen hergeleiteten Elementen als geschachtelte Tabellen hergeleitet werden, wird eine geschachtelte **DataRelation** zwischen den beiden Tabellen erstellt.  	Zu beiden Tabellen wird eine neue Primärschlüsselspalte mit dem Namen **TableName\_Id** hinzugefügt, die von der **DataRelation** verwendet wird.  Anhand der Spalte **TableName\_Id** wird eine **ForeignKeyConstraint** zwischen den beiden Tabellen erstellt.  
  
-   Bei Elementen mit Text, jedoch ohne untergeordnete Elemente, die als Tabellen hergeleitet werden, wird für den Text jeweils eine neue Spalte mit dem Namen **TableName\_Text** erstellt.  Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.  
  
## Siehe auch  
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)