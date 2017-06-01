---
title: "Abfragen von &#39;DataSets&#39; (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Abfragen von &#39;DataSets&#39; (LINQ to DataSet)
Nachdem ein <xref:System.Data.DataSet>\-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen.  Das Formulieren von Abfragen mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ähnelt der Verwendung von [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] zur Abfrage anderer [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-fähiger Datenquellen.  Bedenken Sie jedoch, dass Sie beim Abfragen eines <xref:System.Data.DataSet>\-Objekts mit [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] statt einer Enumeration eines benutzerdefinierten Typs eine Enumeration von <xref:System.Data.DataRow>\-Objekten abfragen.  Das heißt, dass Sie in Ihren [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]\-Abfragen jedes Element der <xref:System.Data.DataRow>\-Klasse verwenden können.  Auf diese Weise lassen sich umfangreiche und komplexe Abfragen erstellen.  
  
 Wie auch bei anderen Implementierungen von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] können Sie [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Abfragen in zwei verschiedenen Formen erstellen: mit der Abfrageausdruckssyntax und mit der methodenbasierten Abfragesyntax.  Weitere Informationen zu diesen beiden Formen finden Sie unter [Getting Started with LINQ](http://msdn.microsoft.com/de-de/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.  
  
## In diesem Abschnitt  
 [Abfragen für eine einzelne Tabelle](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von Abfragen für eine einzelne Tabelle.  
  
 [Abfragen für mehrere Tabellen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von tabellenübergreifenden Abfragen.  
  
 [Abfragen von typisierten DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Beschreibt die Vorgehensweise beim Abfragen von typisierten <xref:System.Data.DataSet>\-Objekten.  
  
## Siehe auch  
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)