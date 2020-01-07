---
title: Abfragen von DataSets (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: bb64abcffdbbcd46dfb11b2564619c565e461436
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634780"
---
# <a name="querying-datasets-linq-to-dataset"></a>Abfragen von DataSets (LINQ to DataSet)
Nachdem ein <xref:System.Data.DataSet>-Objekt mit Daten aufgefüllt wurde, können Sie anfangen, es abzufragen. Das Formulieren von Abfragen mit LINQ to DataSet ähnelt der Verwendung von LINQ (Language-Integrated Query) mit anderen LINQ-fähigen Datenquellen. Beachten Sie jedoch, dass Sie bei der Verwendung von LINQ-Abfragen für ein <xref:System.Data.DataSet> Objekt eine Enumeration von <xref:System.Data.DataRow> Objekten statt einer Enumeration eines benutzerdefinierten Typs Abfragen. Dies bedeutet, dass Sie jedes der Member der <xref:System.Data.DataRow>-Klasse in den LINQ-Abfragen verwenden können. Auf diese Weise können Sie umfangreiche, komplexe Abfragen erstellen.  
  
 Wie bei anderen Implementierungen von LINQ können Sie LINQ to DataSet Abfragen in zwei unterschiedlichen Formen erstellen: Abfrage Ausdruckssyntax und Methoden basierte Abfrage Syntax. Sie können mit der Abfrageausdruckssyntax oder der methodenbasierten Abfragesyntax Daten aus nur einer Tabelle in einem <xref:System.Data.DataSet>, aus mehreren Tabellen in einem <xref:System.Data.DataSet> oder aus Tabellen in einem typisierten <xref:System.Data.DataSet> abrufen.  
  
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
