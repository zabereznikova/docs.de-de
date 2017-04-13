---
title: "Herleiten von Elementtext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Herleiten von Elementtext
Bei einem Element mit Text, jedoch ohne als Tabellen herzuleitende untergeordnete Elemente \(z. B. Elemente mit Attributen oder sich wiederholende Elemente\), wird der Tabelle, die für das Element hergeleitet wird, eine neue Spalte mit dem Namen **TableName\_Text** hinzugefügt.  Der in dem Element enthaltene Text wird einer Tabellenzeile hinzugefügt und in der neuen Spalte gespeichert.  Die **ColumnMapping**\-Eigenschaft der neuen Spalte wird auf **MappingType.SimpleContent** festgelegt.  
  
 Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 Durch die Herleitung wird eine Tabelle mit dem Namen **Element1** und den zwei Spalten **attr1** und **Element1\_Text** erstellt.  Die **ColumnMapping**\-Eigenschaft der **attr1**\-Spalte wird auf **MappingType.Attribute** festgelegt.  Die **ColumnMapping**\-Eigenschaft der **Element1\_Text**\-Spalte wird auf **MappingType.SimpleContent** festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Bei einem Element mit Text und untergeordneten Elementen, die ebenfalls Text enthalten, wird der Tabelle keine Spalte zum Speichern des Elementtexts hinzugefügt.  Der in dem Element enthaltene Text wird ignoriert, während der Text in den untergeordneten Elementen in eine Tabellenzeile eingefügt wird.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
```  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 Durch die Herleitung wird eine Tabelle mit dem Namen **Element1** und der Spalte **ChildElement1** erstellt.  Der Text für das **ChildElement1**\-Element wird in eine Zeile der Tabelle eingefügt.  Der restliche Text wird ignoriert.  Die **ColumnMapping**\-Eigenschaft der **ChildElement1**\-Spalte wird auf **MappingType.Element** festgelegt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## Siehe auch  
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)