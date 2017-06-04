---
title: "DataSets, DataTables und DataViews | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSets, DataTables und DataViews
ADO.NET <xref:System.Data.DataSet> ist eine speicherresidente Darstellung von Daten, die – unabhängig von der darin enthaltenen Datenquelle – ein konsistentes relationales Programmiermodell bereitstellt.  Ein <xref:System.Data.DataSet> stellt einen kompletten Satz aus Daten dar, einschließlich der Tabellen, die die Daten enthalten, ordnen und einschränken, sowie der Beziehungen zwischen den Tabellen.  
  
 Es gibt verschiedene Möglichkeiten, mit einem <xref:System.Data.DataSet> zu arbeiten, die unabhängig voneinander oder kombiniert angewendet werden können.  Sie haben folgende Möglichkeiten:  
  
-   Sie können eine <xref:System.Data.DataTable>, eine <xref:System.Data.DataRelation> und eine <xref:System.Data.Constraint> innerhalb eines <xref:System.Data.DataSet> programmgesteuert erstellen und die Tabellen mit Daten füllen.  
  
-   Sie können das <xref:System.Data.DataSet> mithilfe eines `DataAdapter` mit Tabellen von Daten aus einer vorhandenen relationalen Datenquelle füllen.  
  
-   Sie können den Inhalt des <xref:System.Data.DataSet> mithilfe von XML laden und beibehalten.  Weitere Informationen finden Sie unter [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
 Bei einem <xref:System.Data.DataSet> mit strikter Typbindung besteht auch die Möglichkeit, es mit einem XML\-Webdienst zu übertragen.  Durch seinen Aufbau ist das <xref:System.Data.DataSet> ideal für die Übertragung von Daten mithilfe von XML\-Webdiensten geeignet.  Eine Übersicht über die XML\-Webdienste finden Sie unter [XML Web Services Overview](http://msdn.microsoft.com/de-de/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).  Ein Beispiel für die Verwendung eines <xref:System.Data.DataSet> aus einem XML\-Webdienst finden Sie unter [Verwenden eines DataSet aus einem XML\-Webdienst](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).  
  
## In diesem Abschnitt  
 [Erstellen eines DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 Beschreibt die Syntax zum Erstellen einer Instanz eines <xref:System.Data.DataSet>.  
  
 [Hinzufügen einer DataTable zu einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 Beschreibt das Erstellen sowie das Hinzufügen von Tabellen und Spalten zu einem <xref:System.Data.DataSet>.  
  
 [Hinzufügen von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 Beschreibt das Erstellen von Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet>.  
  
 [Navigieren in 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 Beschreibt, wie die Beziehungen zwischen Tabellen in einem <xref:System.Data.DataSet> dazu verwendet werden, untergeordnete oder übergeordnete Zeilen einer Beziehung zwischen über\- und untergeordneten Tabellen zurückzugeben.  
  
 [Zusammenführen von DataSet\-Inhalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 Beschreibt, wie der Inhalt eines <xref:System.Data.DataSet>\-Arrays, <xref:System.Data.DataTable>\-Arrays oder <xref:System.Data.DataRow>\-Arrays mit einem anderen <xref:System.Data.DataSet> zusammengeführt wird.  
  
 [Kopieren von DataSet\-Inhalten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 Beschreibt das Erstellen einer Kopie eines <xref:System.Data.DataSet>, die ein Schema sowie angegebene Daten enthalten kann.  
  
 [Behandeln von DataSet\-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 Beschreibt die Ereignisse eines <xref:System.Data.DataSet> und wie diese verwendet werden.  
  
 [Typisierte 'DataSets'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 Erläutert, was ein typisiertes <xref:System.Data.DataSet> ist, und wie es erstellt und verwendet wird.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Beschreibt das Erstellen einer <xref:System.Data.DataTable>, das Definieren des zugehörigen Schemas und das Bearbeiten von Daten.  
  
 ['DataTableReaders'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 Beschreibt das Erstellen und Verwenden eines <xref:System.Data.DataTableReader>.  
  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 Beschreibt das Erstellen von und Arbeiten mit `DataViews` sowie das Arbeiten mit <xref:System.Data.DataView>\-Ereignissen.  
  
 [Verwenden von XML in einem DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Beschreibt, wie das <xref:System.Data.DataSet> mit XML als Datenquelle interagiert, einschließlich des Ladens und Beibehaltens des Inhalts eines <xref:System.Data.DataSet> als XML\-Daten.  
  
 [Verwenden eines DataSet aus einem XML\-Webdienst](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 Beschreibt, wie ein XML\-Webdienst erstellt wird, der für die Übertragung von Daten ein <xref:System.Data.DataSet> verwendet.  
  
## Verwandte Abschnitte  
 [Neues in ADO.NET](../../../../../docs/framework/data/adonet/whats-new.md)  
 Enthält eine Einführung in neue Funktionen von ADO.NET.  
  
 [Übersicht über ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Bietet eine Einführung in das Design und die Komponenten von ADO.NET.  
  
 [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Beschreibt das Laden eines **DataSet** mit Daten aus einer Datenquelle.  
  
 [Aktualisieren von Datenquellen mit DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Beschreibt, wie Änderungen an Daten in einem **DataSet** auch in der Datenquelle vorgenommen werden können.  
  
 [Hinzufügen vorhandener Einschränkungen zu einem DataSet](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Beschreibt das Auffüllen eines **DataSet** mit Primärschlüsselinformationen aus einer Datenquelle.  
  
## Siehe auch  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)