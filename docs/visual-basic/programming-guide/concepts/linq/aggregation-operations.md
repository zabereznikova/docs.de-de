---
title: Aggregationsvorgänge
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 8e2c9698de67dc4def348a03c9d69713a6130f31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383792"
---
# <a name="aggregation-operations-visual-basic"></a>Aggregations Vorgänge (Visual Basic)
Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet. Ein Beispiel für einen Aggregationsvorgang ist die Berechnung der durchschnittlichen Tagestemperatur aus den Tagestemperaturen eines Monats.  
  
 Die folgende Abbildung zeigt das Ergebnis von zwei verschiedenen Aggregationsvorgängen bei einer Zahlensequenz. Der erste Vorgang zählt die Zahlen zusammen. Der zweite Vorgang gibt den höchsten Wert der Sequenz zurück.  
  
 ![Abbildung der LINQ-Aggregationsvorgänge](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 Die Methoden des Standardabfrageoperators, die Aggregationsvorgänge ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Aggregat|Führt einen benutzerdefinierten Aggregationsvorgang für die Werte einer Auflistung durch.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Berechnet den Durchschnittswert einer Auflistung von Werten.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Anzahl|Zählt die Elemente einer Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Zählt die Elemente einer großen Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Max|Bestimmt den Maximalwert einer Auflistung.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Min|Bestimmt den Minimalwert einer Auflistung.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|SUM|Berechnet die Summe der Werte einer Auflistung.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="average"></a>Average  
 Im folgenden Codebeispiel wird die- `Aggregate Into Average` Klausel in Visual Basic verwendet, um die Durchschnittstemperatur in einem Array von Zahlen zu berechnen, die Temperaturen darstellen.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Anzahl  
 Im folgenden Codebeispiel wird die- `Aggregate Into Count` Klausel in Visual Basic verwendet, um die Anzahl von Werten in einem Array zu zählen, die größer oder gleich 80 sind.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  
 Im folgenden Codebeispiel wird die- `Aggregate Into LongCount` Klausel verwendet, um die Anzahl von Werten in einem Array zu zählen.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Max  
 Im folgenden Codebeispiel wird die- `Aggregate Into Max` Klausel verwendet, um die maximale Temperatur in einem Array von Zahlen zu berechnen, die Temperaturen darstellen.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Min  
 Im folgenden Codebeispiel wird die- `Aggregate Into Min` Klausel verwendet, um die minimale Temperatur in einem Array von Zahlen zu berechnen, die Temperaturen darstellen.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>SUM  
 Im folgenden Codebeispiel wird die- `Aggregate Into Sum` Klausel verwendet, um die Gesamtkosten eines Arrays von Werten zu berechnen, die Ausgaben darstellen.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](standard-query-operators-overview.md)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [Gewusst wie: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic) (Gewusst wie: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic))](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Gewusst wie: Abfragen der Gesamtanzahl von Bytes in einem Ordner Satz (LINQ) (Visual Basic)](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
