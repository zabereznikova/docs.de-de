---
title: Aggregationsvorgänge (C#)
description: Hier erfahren Sie mehr über die Methoden zum Ausführen eines Aggregationsvorgangs. Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet.
ms.date: 07/20/2015
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
ms.openlocfilehash: c302667ec7f1d4ed5acb98439ea9f8f80250077d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159383"
---
# <a name="aggregation-operations-c"></a>Aggregationsvorgänge (C#)

Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet. Ein Beispiel für einen Aggregationsvorgang ist die Berechnung der durchschnittlichen Tagestemperatur aus den Tagestemperaturen eines Monats.  
  
 Die folgende Abbildung zeigt das Ergebnis von zwei verschiedenen Aggregationsvorgängen bei einer Zahlensequenz. Der erste Vorgang zählt die Zahlen zusammen. Der zweite Vorgang gibt den höchsten Wert der Sequenz zurück.  
  
 ![Abbildung der LINQ-Aggregationsvorgänge](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 Die Methoden des Standardabfrageoperators, die Aggregationsvorgänge ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Aggregat|Führt einen benutzerdefinierten Aggregationsvorgang für die Werte einer Auflistung durch.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Berechnet den Durchschnittswert einer Auflistung von Werten.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Anzahl|Zählt die Elemente einer Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Zählt die Elemente einer großen Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.|Nicht zutreffend.|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Max.|Bestimmt den Maximalwert einer Auflistung.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Min.|Bestimmt den Minimalwert einer Auflistung.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Summe|Berechnet die Summe der Werte einer Auflistung.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))](./standard-query-operators-overview.md)
- [Vorgehensweise: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (C#)](./how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#)](./how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
- [Vorgehensweise: Abfragen der Gesamtzahl an Bytes in einem Ordnersatz (LINQ) (C#)](./how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)
