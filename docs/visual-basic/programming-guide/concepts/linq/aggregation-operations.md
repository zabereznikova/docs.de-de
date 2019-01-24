---
title: Aggregationsvorgänge (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 7daf4f653d3796eaa3ae426fdbf86a89ebdd2dc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735382"
---
# <a name="aggregation-operations-visual-basic"></a>Aggregationsvorgänge (Visual Basic)
Während eines Aggregationsvorgangs wird aus einer Auflistung von Werten ein einzelner Wert berechnet. Ein Beispiel für einen Aggregationsvorgang ist die Berechnung der durchschnittlichen Tagestemperatur aus den Tagestemperaturen eines Monats.  
  
 Die folgende Abbildung zeigt das Ergebnis von zwei verschiedenen Aggregationsvorgängen bei einer Zahlensequenz. Der erste Vorgang zählt die Zahlen zusammen. Der zweite Vorgang gibt den höchsten Wert der Sequenz zurück.  
  
 ![LINQ-Aggregationsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")  
  
 Die Methoden des Standardabfrageoperators, die Aggregationsvorgänge ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Aggregat|Führt einen benutzerdefinierten Aggregationsvorgang für die Werte einer Auflistung durch.|Nicht zutreffend.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Berechnet den Durchschnittswert einer Auflistung von Werten.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Anzahl|Zählt die Elemente einer Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Zählt die Elemente einer großen Auflistung, optional auch nur die Elemente, die eine Prädikatfunktion erfüllen.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Max.|Bestimmt den Maximalwert einer Auflistung.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Min.|Bestimmt den Minimalwert einer Auflistung.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Summe|Berechnet die Summe der Werte einer Auflistung.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="average"></a>Average  
 Im folgenden Codebeispiel wird die `Aggregate Into Average` -Klausel in Visual Basic, um die Durchschnittstemperatur in ein Array von Zahlen berechnet, die Temperaturen darstellen.  
  
 [!code-vb[CsLINQAggregating#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a>Anzahl  
 Im folgenden Codebeispiel wird die `Aggregate Into Count` -Klausel in Visual Basic, um die Anzahl der Werte in einem Array zu zählen, die größer als oder gleich 80.  
  
 [!code-vb[CsLINQAggregating#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a>LongCount  
 Im folgenden Codebeispiel wird die `Aggregate Into LongCount` -Klausel, um die Anzahl der Werte in einem Array zählen.  
  
 [!code-vb[CsLINQAggregating#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a>Max.  
 Im folgenden Codebeispiel wird die `Aggregate Into Max` -Klausel, um die maximale Temperatur in ein Array von Zahlen zu berechnen, die Temperaturen darstellen.  
  
 [!code-vb[CsLINQAggregating#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a>Min.  
 Im folgenden Codebeispiel wird die `Aggregate Into Min` -Klausel, um die niedrigste Temperatur in ein Array von Zahlen zu berechnen, die Temperaturen darstellen.  
  
 [!code-vb[CsLINQAggregating#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a>Summe  
 Im folgenden Codebeispiel wird die `Aggregate Into Sum` -Klausel, um die Gesamtausgaben aus einem Array von Werten zu berechnen, die Ausgaben darstellen.  
  
 [!code-vb[CsLINQAggregating#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Vorgehensweise: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Vorgehensweise: Anzahl, Summen oder Durchschnittswerten von Daten](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Vorgehensweise: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [Vorgehensweise: Abfragen der größten Datei oder Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Vorgehensweise: Abfrage für die Gesamtzahl der Bytes in einem Ordnersatz (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
