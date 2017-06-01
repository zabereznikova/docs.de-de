---
title: "Herleiten der relationalen DataSet-Struktur aus XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Herleiten der relationalen DataSet-Struktur aus XML
Die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet> besteht aus Tabellen, Spalten, Einschränkungen und Beziehungen.  Beim Laden eines <xref:System.Data.DataSet> aus XML kann das Schema vordefiniert sein oder explizit bzw. durch Rückschluss aus dem geladenen XML erstellt werden.  Weitere Informationen zum Laden des Schemas und Inhalts eines <xref:System.Data.DataSet> aus XML finden Sie unter [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) und [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
 Wenn das Schema eines <xref:System.Data.DataSet> von XML erstellt wird, wird es in der Regel mit XSD \(XML Schema Definition Language\) \(wie unter [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md) beschrieben\) oder mit XDR \(XML Data Reduced\) explizit angegeben.  Falls in XML kein XML\-Schema oder XDR\-Schema verfügbar ist, kann das Schema des <xref:System.Data.DataSet> aus der Struktur der XML\-Elemente und \-Attribute hergeleitet werden.  
  
 In diesem Abschnitt werden anhand von XML\-Elementen und \-Attributen, ihrer Struktur und dem daraus hergeleiteten <xref:System.Data.DataSet>\-Schema die Herleitungsregeln für <xref:System.Data.DataSet>\-Schemata erläutert.  
  
 Nicht alle in einem XML\-Dokument vorhandenen Attribute sollten in den Rückschlussprozess einbezogen werden.  Namespace\-qualifizierte Attribute enthalten häufig Metadaten, die zwar für das XML\-Dokument wichtig sind, nicht jedoch für das <xref:System.Data.DataSet>\-Schema.  Mithilfe von <xref:System.Data.DataSet.InferXmlSchema%2A> legen Sie fest, dass bestimmte Namespaces beim Rückschlussprozess ignoriert werden.  Weitere Informationen finden Sie unter [Laden von DataSet\-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
## In diesem Abschnitt  
 [Zusammenfassung des Rückschlussprozesses von DataSet\-Schemas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 Enthält eine Zusammenfassung der Regeln zur Herleitung des Schemas eines <xref:System.Data.DataSet> aus XML.  
  
 [Herleiten von Tabellen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 Beschreibt die XML\-Elemente, die als Tabellen in einem <xref:System.Data.DataSet> hergeleitet werden.  
  
 [Herleiten von Spalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 Beschreibt die XML\-Elemente und \-Attribute, die als Tabellenspalten hergeleitet werden.  
  
 [Herleiten von Beziehungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 Beschreibt das <xref:System.Data.DataRelation>\-Objekt und das <xref:System.Data.ForeignKeyConstraint>\-Objekt, die beide für geschachtelte, hergeleitete Tabellen erstellt werden.  
  
 [Herleiten von Elementtext](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 Beschreibt die für den Text in XML\-Elementen erstellten Spalten und erläutert, wann der Text in XML\-Elementen ignoriert wird.  
  
 [Einschränkungen bei der Herleitung](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 Behandelt die Einschränkungen der Schemaherleitung.  
  
## Verwandte Abschnitte  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt die Interaktion zwischen dem <xref:System.Data.DataSet>\-Objekt und XML\-Daten.  
  
 [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Beschreibt die relationale Struktur bzw. das Schema eines <xref:System.Data.DataSet>, das aus einem XSD\-Schema \(XML Schema Definition Language\) erstellt wird.  
  
 [Übersicht über ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Beschreibt die ADO.NET\-Architektur und \-Komponenten und wie diese verwendet werden, um auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)