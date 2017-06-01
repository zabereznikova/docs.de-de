---
title: "DataTables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTables
Ein <xref:System.Data.DataSet> besteht aus einer Auflistung von Tabellen, Beziehungen und Einschränkungen.  In ADO.NET werden <xref:System.Data.DataTable>\-Objekte dazu verwendet, Tabellen in einem **DataSet** darzustellen.  Eine **DataTable** stellt eine Tabelle mit relationalen Daten im Speicher dar. Die Daten sind für die .NET\-basierte Anwendung, in der sich die Datentabelle befindet, lokal verfügbar, können jedoch mithilfe eines **DataAdapter** aus einer Datenquelle wie Microsoft SQL Server gefüllt werden. Weitere Informationen finden Sie unter [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).  
  
 Die **DataTable**\-Klasse ist ein Member des **System.Data**\-Namespaces innerhalb der .NET Framework\-Klassenbibliothek.  Eine **DataTable** kann unabhängig oder als Member eines **DataSet** erstellt und verwendet werden. **DataTable**\-Objekte können auch in Verbindung mit anderen .NET Framework\-Objekten, einschließlich <xref:System.Data.DataView>, verwendet werden.  Auf die Auflistung von Tabellen in einem **DataSet** kann über die **Tables**\-Eigenschaft des **DataSet**\-Objekts zugegriffen werden.  
  
 Das Schema oder die Struktur einer Tabelle wird durch Spalten und Einschränkungen dargestellt.  Das Schema einer **DataTable** wird mit <xref:System.Data.DataColumn>\-Objekten sowie mit <xref:System.Data.ForeignKeyConstraint>\-Objekten und <xref:System.Data.UniqueConstraint>\-Objekten definiert.  Die Spalten einer Tabelle können Spalten in einer Datenquelle zugeordnet sein, berechnete Werte aus Ausdrücken enthalten, Werte automatisch erhöhen oder primäre Schlüsselwerte enthalten.  
  
 Zusätzlich zu einem Schema muss eine **DataTable** über Zeilen zum Aufnehmen und Sortieren von Daten verfügen.  Die <xref:System.Data.DataRow>\-Klasse stellt die tatsächlich in einer Tabelle enthaltenen Daten dar.  Die Eigenschaften und Methoden von **DataRow** werden dazu verwendet, Daten in einer Tabelle abzurufen, auszuwerten und zu bearbeiten.  Wenn auf Daten in einer Zeile zugegriffen oder diese verändert werden, behält das **DataRow**\-Objekt sowohl den aktuellen als auch den ursprünglichen Status bei.  
  
 Sie können mithilfe einer oder mehrerer zugehöriger Spalten in Tabellen diese Tabellen als über\- und untergeordnete Tabellen in Beziehung zueinander setzen.  Sie können mithilfe von <xref:System.Data.DataRelation> Beziehungen zwischen **DataTable**\-Objekten erstellen.  **DataRelation**\-Objekte können dann die entsprechenden untergeordneten oder übergeordneten Zeilen für eine bestimmte Zeile zurückgeben.  Weitere Informationen finden Sie unter [Hinzufügen von 'DataRelations'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## In diesem Abschnitt  
 [Erstellen einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Erläutert, wie eine **DataTable** erstellt und einem **DataSet** hinzugefügt wird.  
  
 ['DataTable'\-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Stellt Informationen zum Erstellen und Verwenden von **DataColumn**\-Objekten und Einschränkungen bereit.  
  
 [Bearbeiten von Daten in einer DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Erläutert, wie Daten in einer Tabelle hinzugefügt, bearbeitet oder gelöscht werden.  Erläutert außerdem, wie mithilfe von **DataTable**\-Ereignissen Änderungen an den Daten in einer Tabelle überprüft werden können.  
  
 [Behandlung von DataTable\-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Stellt Informationen zu den Ereignissen bereit, die für die Verwendung in einer **DataTable** verfügbar sind, z. B. für das Ändern von Spaltenwerten oder das Hinzufügen oder Löschen von Zeilen.  
  
## Verwandte Abschnitte  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Beschreibt die ADO.NET\-Architektur und \-Komponenten und wie diese dazu verwendet werden, auf vorhandene Datenquellen zuzugreifen und Anwendungsdaten zu verwalten.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Stellt Informationen zum ADO.NET\-**DataSet** bereit, einschließlich Informationen zum Erstellen von Beziehungen zwischen Tabellen.  
  
 [Einschränkungsklasse](frlrfSystemDataConstraintClassTopic)  
 Stellt Referenzinformationen zum **Constraint**\-Objekt bereit.  
  
 [DataColumn\-Klasse](frlrfSystemDataDataColumnClassTopic)  
 Stellt Referenzinformationen zum **DataColumn**\-Objekt bereit.  
  
 [DataSet\-Klasse](frlrfSystemDataDataSetClassTopic)  
 Stellt Referenzinformationen zum **DataSet**\-Objekt bereit.  
  
 [DataTable\-Klasse](frlrfSystemDataDataTableClassTopic)  
 Stellt Referenzinformationen zum **DataTable**\-Objekt bereit.  
  
 [Übersicht über die Klassenbibliothek](../../../../../docs/standard/class-library-overview.md)  
 Stellt eine Übersicht über die .NET Framework\-Klassenbibliothek mit Informationen zum **System**\-Namespace und dessen untergeordnetem **System.Data**\-Namespace bereit.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)