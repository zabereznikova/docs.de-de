---
title: "Einschr&#228;nkungen bei der Herleitung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Einschr&#228;nkungen bei der Herleitung
Beim Herleiten eines <xref:System.Data.DataSet>\-Schemas aus XML können sich in Abhängigkeit von den XML\-Elementen jedes Dokuments verschiedene Schemata ergeben.  Betrachten Sie beispielsweise den folgenden XML\-Code:  
  
 Document1:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Für "Document1" ergibt die Herleitung ein **DataSet** mit dem Namen "DocumentElement" und eine Tabelle mit dem Namen "Element1", da "Element1" ein sich wiederholendes Element ist.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Für "Document2" ergibt die Herleitung dagegen ein **DataSet** mit dem Namen "NewDataSet" und eine Tabelle mit dem Namen "DocumentElement". "Element1" wird als Spalte hergeleitet, da es keine Attribute und keine untergeordneten Elemente hat.  
  
 **DataSet:** NewDataSet  
  
 **Tabelle:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Es war möglicherweise beabsichtigt, dass sich für beide XML\-Dokumente dasselbe XML\-Schema ergibt, aber die Herleitung führt aufgrund der in den Dokumenten enthaltenen Elemente zu sehr verschiedenen Ergebnissen.  
  
 Zur Vermeidung von Abweichungen, die beim Generieren eines Schemas aus einem XML\-Dokument auftreten können, wird empfohlen, beim Laden eines **DataSet** aus XML explizit ein Schema in XSD \(XML Schema Definition Language\) oder XDR \(XML\-Data Reduced\) anzugeben.  Weitere Informationen zum expliziten Angeben eines **DataSet**\-Schemas mit XML\-Schema finden Sie unter [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## Siehe auch  
 [Herleiten der relationalen DataSet\-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)