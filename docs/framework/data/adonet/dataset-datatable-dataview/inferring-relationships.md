---
title: "Herleiten von Beziehungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Herleiten von Beziehungen
Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt.  Sowohl der für das übergeordnete Element als auch der für das untergeordnete Element erstellten Tabelle wird eine neue Spalte mit dem Namen **ParentTableName\_Id** hinzugefügt.  Die **ColumnMapping**\-Eigenschaft dieser Identitätsspalte wird auf **MappingType.Hidden** festgelegt.  Diese Spalte stellt einen sich automatisch erhöhenden Primärschlüssel für die übergeordnete Tabelle dar und wird für die **DataRelation** zwischen den beiden Tabellen verwendet.  Im Gegensatz zum Datentyp aller anderen hergeleiteten Spalten \(**System.String**\) lautet der Datentyp der hinzugefügten Identitätsspalte **System.Int32**.  Außerdem wird anhand der neuen Spalte in der übergeordneten und der untergeordneten Tabelle eine <xref:System.Data.ForeignKeyConstraint> mit **DeleteRule** \= **Cascade** erstellt.  
  
 Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten werden zwei Tabellen erstellt: **Element1** und **ChildElement1**.  
  
 Die Tabelle **Element1** enthält zwei Spalten: **Element1\_Id** und **ChildElement2**.  Die **ColumnMapping**\-Eigenschaft der **Element1\_Id**\-Spalte wird auf **MappingType.Hidden** festgelegt.  Die **ColumnMapping**\-Eigenschaft der **ChildElement2**\-Spalte wird auf **MappingType.Element** festgelegt.  Die **Element1\_Id**\-Spalte wir als Primärschlüssel der **Element1**\-Tabelle festgelegt.  
  
 Die Tabelle **ChildElement1** enthält drei Spalten: **attr1**, **attr2** und **Element1\_Id**.  Die **ColumnMapping**\-Eigenschaft der **attr1**\-Spalte und der **attr2**\-Spalte wird auf **MappingType.Attribute** festgelegt.  Die **ColumnMapping**\-Eigenschaft der **Element1\_Id**\-Spalte wird auf **MappingType.Hidden** festgelegt.  
  
 Unter Verwendung der **Element1\_Id**\-Spalten beider Tabellen wird eine **DataRelation** und eine **ForeignKeyConstraint** erstellt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|Element1\_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabelle:** ChildElement1  
  
|attr1|attr2|Element1\_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1\_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1\_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1\_Id  
  
 **Nested:** True  
  
 **ForeignKeyConstraint:** Element1\_ChildElement1  
  
 **Column:** Element1\_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** None  
  
## Siehe auch  
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Schachteln von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)