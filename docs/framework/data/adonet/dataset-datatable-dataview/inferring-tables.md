---
title: "Herleiten von Tabellen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Herleiten von Tabellen
Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML\-Dokument wird in ADO.NET zunächst bestimmt, welche XML\-Elemente Tabellen darstellen.  Die folgenden XML\-Strukturen ergeben eine Tabelle für das **DataSet**\-Schema:  
  
-   Elemente mit Attributen  
  
-   Elemente mit untergeordneten Elementen  
  
-   Sich wiederholende Elemente  
  
## Elemente mit Attributen  
 Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## Elemente mit untergeordneten Elementen  
 Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 Das Dokument\- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden.  Wenn das Dokumentelement keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet werden, wird das Element als **DataSet** hergeleitet.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".  
  
 **DataSet:** NewDataSet  
  
 **Tabelle:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 Betrachten Sie alternativ dazu den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich ein **DataSet** "DocumentElement", das eine Tabelle mit dem Namen "Element1" enthält.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## Sich wiederholende Elemente  
 Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## Siehe auch  
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)