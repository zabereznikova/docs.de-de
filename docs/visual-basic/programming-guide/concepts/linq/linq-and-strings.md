---
title: LINQ und Zeichenfolgen
ms.date: 07/20/2015
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
ms.openlocfilehash: ee2a44175e8546f879473a3af6bf1a2de92d2501
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549848"
---
# <a name="linq-and-strings-visual-basic"></a>LINQ und Zeichenfolgen (Visual Basic)
LINQ kann zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden. Dieses Verfahren ist bei halbstrukturierten Daten in Textdateien besonders nützlich. LINQ-Abfragen können mit herkömmlichen Zeichenfolgenfunktionen und regulären Ausdrücken verbunden werden. Beispielsweise können Sie die Methode <xref:System.String.Split%2A> oder <xref:System.Text.RegularExpressions.Regex.Split%2A> verwenden, um ein Array von Zeichenfolgen zu erstellen, das Sie anschließend mit LINQ abfragen oder ändern können. Sie können die Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> in der `where`-Klausel einer LINQ-Abfrage verwenden. Sie können LINQ außerdem zum Abfragen und Ändern der <xref:System.Text.RegularExpressions.MatchCollection>-Ergebnisse, die von einem regulären Ausdruck zurückgegeben werden, verwenden.  
  
 Sie können auch die Techniken verwenden, die in diesem Abschnitt beschrieben werden, um halbstrukturierte Textdaten in XML zu transformieren. Weitere Informationen finden Sie unter Gewusst [wie: Generieren von XML aus CSV-Dateien](../../../../standard/linq/generate-xml-csv-files.md).  
  
 Die Beispiele in diesem Abschnitt gehören zu einer der folgenden beiden Kategorien:  
  
## <a name="querying-a-block-of-text"></a>Abfragen eines Textblocks  
 Sie können Textblöcke abfragen, analysieren und ändern, indem Sie sie mithilfe der <xref:System.String.Split%2A>- oder der <xref:System.Text.RegularExpressions.Regex.Split%2A>-Methode in ein abfragbares Array von kleineren Zeichenfolgen aufteilen. Sie können den Quelltext in Wörter, Sätze, Absätze, Paragraphen, Seiten oder andere Kriterien unterteilen und anschließend andere Unterteilungen ausführen, wenn sie in Ihrer Abfrage benötigt werden.  
  
 [Gewusst wie: zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Zeigt die Verwendung von LINQ für einfache Textabfragen.  
  
 [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic) (Gewusst wie: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#))](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Zeigt, wie Textdateien an beliebigen Grenzen unterteilt wird und wie Abfragen mit jedem Teil ausgeführt werden.  
  
 [Gewusst wie: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Veranschaulicht, dass eine Zeichenfolge ein abfragbarer Typ ist.  
  
 [Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Zeigt, wie reguläre Ausdrücke in LINQ-Abfragen für komplexe Musterabgleiche bei gefilterten Abfrageergebnissen verwendet werden.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Abfragen halbstrukturierter Daten im Textformat  
 Viele verschiedene Typen von Textdateien bestehen aus einer Reihe von Zeilen, die häufig mit ähnlicher Formatierung, z.B. durch Tabstopps oder Kommas getrennten Dateien oder Zeilen mit fester Länge. Nachdem Sie solch eine Textdatei in den Arbeitsspeicher gelesen haben, können Sie LINQ zum Abfragen bzw. Ändern der Zeilen verwenden. LINQ-Abfragen vereinfachen zudem die Aufgabe, Daten aus mehreren Quellen zu kombinieren.  
  
 [Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Zeigt, wie alle Zeichenfolgen gesucht werden, die in einer Liste, aber nicht in der anderen, vorhanden sind  
  
 [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Zeigt, wie Textzeilen anhand eines beliebigen Worts oder Felds sortiert werden.  
  
 [Vorgehensweise: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Zeigt, wie Felder in einer Zeile in einer CSV-Datei neu angeordnet werden  
  
 [Vorgehensweise: kombinieren und Vergleichen von Zeichen folgen Auflistungen (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Zeigt, wie Zeichenfolgenlisten auf verschiedene Weise verbunden werden  
  
 [Gewusst wie: Auffüllen von Objekt Auflistungen aus mehreren Quellen (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Zeigt, wie Auflistungen erstellt werden, indem Sie mehrere Textdateien als Datenquellen verwenden  
  
 [Vorgehensweise: Verknüpfen von Inhalten aus unterschiedlichen Dateien (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Zeigt, wie Zeichenfolgen in zwei Listen mit einem übereinstimmenden Schlüssel in einer einzigen Zeichenfolge vereint werden  
  
 [Vorgehensweise: Aufteilen einer Datei in viele Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Veranschaulicht, wie neue Dateien mithilfe einer einzelnen Datei als Datenquelle erstellt werden  
  
 [Gewusst wie: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Zeigt, wie mathematische Berechnungen bei Textdaten in CSV-Dateien ausgeführt werden  
  
## <a name="see-also"></a>Siehe auch

- [Language Integrated Query (LINQ) (Visual Basic)](index.md)
- [Gewusst wie: Generieren von XML aus CSV-Dateien](../../../../standard/linq/generate-xml-csv-files.md)
