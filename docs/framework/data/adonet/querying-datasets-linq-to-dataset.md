---
title: Abfragen von DataSets (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4f1b1a70025dc81bdf99c636b65c23d373e73a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="querying-datasets-linq-to-dataset"></a>Abfragen von DataSets (LINQ to DataSet)
Nachdem ein <xref:System.Data.DataSet>-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen. Das Formulieren von Abfragen mit [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] ähnelt der Verwendung von [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] zur Abfrage anderer [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-fähiger Datenquellen. Bedenken Sie jedoch, die bei der Verwendung [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen im Verlauf einer <xref:System.Data.DataSet> eine Enumeration des abgefragten Objekts <xref:System.Data.DataRow> Objekte, statt einer Enumeration eines benutzerdefinierten Typs. Dies bedeutet, dass Sie eines der Elemente verwenden können die <xref:System.Data.DataRow> -Klasse in Ihrem [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen. Auf diese Weise lassen sich umfangreiche und komplexe Abfragen erstellen.  
  
 Wie bei anderen Implementierungen von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], Sie können erstellen [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfragen in zwei verschiedenen Formen: Abfrageausdruckssyntax und mit methodenbasierter Abfragesyntax. Weitere Informationen zu diesen beiden Formen finden Sie unter [erste Schritte mit LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Abfragen für einzelne Tabellen](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von Abfragen für eine einzelne Tabelle.  
  
 [Tabellenübergreifende Abfragen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von tabellenübergreifenden Abfragen.  
  
 [Abfragen von typisierten DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Beschreibt die Vorgehensweise beim Abfragen von typisierten <xref:System.Data.DataSet>-Objekten.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to DataSet-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Laden von Daten in einem DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
