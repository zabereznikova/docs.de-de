---
title: Abfragen von DataSets (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783049"
---
# <a name="querying-datasets-linq-to-dataset"></a>Abfragen von DataSets (LINQ to DataSet)
Nachdem ein <xref:System.Data.DataSet>-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen. Das Formulieren von Abfragen mit LINQ to DataSet ähnelt der [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Verwendung von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]mit anderen-fähigen Datenquellen. Denken Sie jedoch daran, dass Sie bei [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] der Verwendung von <xref:System.Data.DataSet> Abfragen für ein-Objekt eine Enumeration von <xref:System.Data.DataRow> -Objekten statt einer Enumeration eines benutzerdefinierten Typs Abfragen. Dies bedeutet, dass Sie alle Member der <xref:System.Data.DataRow> -Klasse in Ihren [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Abfragen verwenden können. Auf diese Weise lassen sich umfangreiche und komplexe Abfragen erstellen.  
  
 Wie bei anderen Implementierungen von [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]können Sie LINQ to DataSet Abfragen in zwei unterschiedlichen Formen erstellen: Abfrage Ausdruckssyntax und Methoden basierte Abfrage Syntax. Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Abfragen für einzelne Tabellen](single-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von Abfragen für eine einzelne Tabelle.  
  
 [Tabellenübergreifende Abfragen](cross-table-queries-linq-to-dataset.md)  
 Beschreibt die Vorgehensweise beim Ausführen von tabellenübergreifenden Abfragen.  
  
 [Abfragen von typisierten DataSets](querying-typed-datasets.md)  
 Beschreibt die Vorgehensweise beim Abfragen von typisierten <xref:System.Data.DataSet>-Objekten.  
  
## <a name="see-also"></a>Siehe auch

- [Beispiele für LINQ to DataSet](linq-to-dataset-examples.md)
- [Laden von Daten in ein DataSet](loading-data-into-a-dataset.md)
