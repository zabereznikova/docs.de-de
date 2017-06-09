---
title: "DataViews | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataViews
Mit einer <xref:System.Data.DataView> können Sie verschiedene Ansichten der in einer <xref:System.Data.DataTable> gespeicherten Daten erstellen. Diese Funktion wird oft in Datenbindungsanwendungen verwendet.  Mit einer **DataView** können Sie Daten in einer Tabelle mit verschiedenen Sortierreihenfolgen verfügbar machen und nach Zeilenstatus oder basierend auf einem Filterausdruck filtern.  
  
 Ein **DataView** enthält eine dynamische Ansicht der Daten in der zugrunde liegenden **DataTable**: Inhalt, Reihenfolge und Mitgliedschaft reflektieren auftretende Änderungen.  Dieses Verhalten unterscheidet sich von der **Select**\-Methode der **DataTable**, bei der ein <xref:System.Data.DataRow>\-Array auf Grundlage eines bestimmten Filters und\/oder einer Sortierreihenfolge einer Tabelle zurückgegeben wird. Dieser Inhalt berücksichtigt Änderungen in der zugrunde liegenden Tabelle, die Mitgliedschaft und Reihenfolge bleiben jedoch statisch.  Aufgrund der dynamischen Funktionen ist die **DataView** ideal für Datenbindungsanwendungen.  
  
 Eine **DataView** stellt eine dynamische Ansicht eines einzelnen Datensatzes bereit \(ähnlich einer Datenbankansicht\), auf den Sie verschiedene Sortier\- und Filterkriterien anwenden können.  Im Gegensatz zu einer Datenbankansicht kann eine **DataView** jedoch nicht als Tabelle behandelt werden und kann auch keine Ansicht von verknüpften Tabellen bereitstellen.  Außerdem können Sie keine Spalten ausschließen, die in der Quelltabelle vorhanden sind, und auch keine Spalten \(z. B. berechnete Spalten\) anhängen, die nicht in der Quelltabelle vorliegen.  
  
 Mit einem <xref:System.Data.DataView.DataViewManager%2A> können Sie die Ansichtseinstellungen für alle Tabellen in einem **DataSet** verwalten.  Der **DataViewManager** bietet eine praktische Möglichkeit zum Verwalten von Standardansichtseinstellungen für die einzelnen Tabellen.  Wenn Sie ein Steuerelement an mehrere Tabellen eines **DataSet** binden möchten, stellt das Binden an einen **DataViewManager** die optimale Möglichkeit dar.  
  
## In diesem Abschnitt  
 [Erstellen einer DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Beschreibt das Erstellen einer **DataView** für eine **DataTable**.  
  
 [Sortieren und Filtern von Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Beschreibt das Festlegen der Eigenschaften einer **DataView**, um Teilmengen von Datenzeilen zurückzugeben, die bestimmten Filterkriterien entsprechen, oder um Daten in einer bestimmten Sortierreihenfolge zurückzugeben.  
  
 ['DataRows' und 'DataRowViews'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Beschreibt den Zugriff auf Daten, die durch die **DataView** verfügbar gemacht werden.  
  
 [Suchen nach Zeilen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Beschreibt die Suche nach einer bestimmten Zeile in einer **DataView**.  
  
 ['ChildViews' und Beziehungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Beschreibt das Erstellen von Datenansichten aus einer Beziehung zwischen einem übergeordneten und einem untergeordneten Element mithilfe einer **DataView**.  
  
 [Bearbeiten von 'DataViews'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Beschreibt das Ändern der Daten in der zugrunde liegenden **DataTable** mithilfe der **DataView**, einschließlich dem Aktivieren oder Deaktivieren von Updates.  
  
 [Behandlung von DataView\-Ereignissen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Beschreibt die Verwendung des **ListChanged**\-Ereignisses, um eine Benachrichtigung zu erhalten, sobald der Inhalt oder die Sortierung einer **DataView** aktualisiert wird.  
  
 [Verwalten von 'DataViews'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Beschreibt die Verwendung eines **DataViewManager** zum Verwalten der **DataView**\-Einstellungen für die einzelnen Tabellen im **DataSet**.  
  
## Verwandte Abschnitte  
 [ASP.NET Web Applications](http://msdn.microsoft.com/de-de/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 Stellt Übersichten und ausführliche schrittweise Anleitungen zum Erstellen von ASP.NET\-Anwendungen, Web Forms und Web Services bereit.  
  
 [Windows Applications](http://msdn.microsoft.com/de-de/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Stellt ausführliche Informationen zum Arbeiten mit Windows Forms und Konsolenanwendungen bereit.  
  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt das **DataSet**\-Objekt und dessen Verwendung beim Verwalten von Anwendungsdaten.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Beschreibt das **DataTable**\-Objekt und dessen Verwendung zum eigenständigen Verwalten von Anwendungsdaten oder zum Verwalten von Anwendungsdaten als Teil eines **DataSet**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Beschreibt die ADO.NET\-Architektur und \-Komponenten und die Verwendung von ADO.NET zum Zugriff auf vorhandene Datenquellen und zum Verwalten von Anwendungsdaten.  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)