---
title: Abfragen von DataSets (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: ec4ee345835294499f7ac9f665a9b79e2efc0f64
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504662"
---
# <a name="querying-datasets-linq-to-dataset"></a>Abfragen von DataSets (LINQ to DataSet)
Nachdem ein <xref:System.Data.DataSet>-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen. Formulieren von Abfragen mit LINQ to DataSet entspricht dem verwenden [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Abfrage anderer [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]--fähiger Datenquellen. Beachten Sie, allerdings, dass bei Verwendung von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen eine <xref:System.Data.DataSet> Objekt, die Sie eine Enumeration von Abfragen <xref:System.Data.DataRow> Objekte statt einer Enumeration eines benutzerdefinierten Typs. Dies bedeutet, dass Sie jedes der Elemente verwenden können die <xref:System.Data.DataRow> -Klasse in Ihrem [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen. Auf diese Weise lassen sich umfangreiche und komplexe Abfragen erstellen.  
  
 Wie bei anderen Implementierungen von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], Sie können LINQ to DataSet-Abfragen auf zwei verschiedene Arten erstellen: Abfrageausdrucksyntax und mit der methodenbasierten Abfragesyntax. Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Abfragen für einzelne Tabellen](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von Abfragen für eine einzelne Tabelle.  
  
 [Tabellenübergreifende Abfragen](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von tabellenübergreifenden Abfragen.  
  
 [Abfragen von typisierten DataSets](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Beschreibt die Vorgehensweise beim Abfragen von typisierten <xref:System.Data.DataSet>-Objekten.  
  
## <a name="see-also"></a>Siehe auch

- [Beispiele für LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [Laden von Daten in ein DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
