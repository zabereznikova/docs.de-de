---
title: LINQ und Zeichenfolgen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b615f3dc76d72e7f73146498e0143f88c52278a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="linq-and-strings-visual-basic"></a>LINQ und Zeichenfolgen (Visual Basic)
LINQ kann zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden. Dieses Verfahren ist bei halbstrukturierten Daten in Textdateien besonders nützlich. LINQ-Abfragen können mit herkömmlichen Zeichenfolgenfunktionen und regulären Ausdrücken verbunden werden. Beispielsweise können Sie die Methode <xref:System.String.Split%2A> oder <xref:System.Text.RegularExpressions.Regex.Split%2A> verwenden, um ein Array von Zeichenfolgen zu erstellen, das Sie anschließend mit LINQ abfragen oder ändern können. Sie können die Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> in der `where`-Klausel einer LINQ-Abfrage verwenden. Sie können LINQ außerdem zum Abfragen und Ändern der <xref:System.Text.RegularExpressions.MatchCollection>-Ergebnisse, die von einem regulären Ausdruck zurückgegeben werden, verwenden.  
  
 Sie können auch die Techniken verwenden, die in diesem Abschnitt beschrieben werden, um halbstrukturierte Textdaten in XML zu transformieren. Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von XML aus CSV-Dateien](how-to-generate-xml-from-csv-files.md).  
  
 Die Beispiele in diesem Abschnitt gehören zu einer der folgenden beiden Kategorien:  
  
## <a name="querying-a-block-of-text"></a>Abfragen eines Textblocks  
 Sie können Textblöcke abfragen, analysieren und ändern, indem Sie sie mithilfe der <xref:System.String.Split%2A>- oder der <xref:System.Text.RegularExpressions.Regex.Split%2A>-Methode in ein abfragbares Array von kleineren Zeichenfolgen aufteilen. Sie können den Quelltext in Wörter, Sätze, Absätze, Paragraphen, Seiten oder andere Kriterien unterteilen und anschließend andere Unterteilungen ausführen, wenn sie in Ihrer Abfrage benötigt werden.  
  
 [Vorgehensweise: zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Zeigt die Verwendung von LINQ für einfache Textabfragen.  
  
 [Vorgehensweise: Abfragen von Sätzen, die einen angegebenen Satz von Wörtern (LINQ) (Visual Basic) enthalten.](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Zeigt, wie Textdateien an beliebigen Grenzen unterteilt wird und wie Abfragen mit jedem Teil ausgeführt werden.  
  
 [Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Veranschaulicht, dass eine Zeichenfolge ein abfragbarer Typ ist.  
  
 [Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Zeigt, wie reguläre Ausdrücke in LINQ-Abfragen für komplexe Musterabgleiche bei gefilterten Abfrageergebnissen verwendet werden.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Abfragen halbstrukturierter Daten im Textformat  
 Viele verschiedene Typen von Textdateien bestehen aus einer Reihe von Zeilen, die häufig mit ähnlicher Formatierung, z.B. durch Tabstopps oder Kommas getrennten Dateien oder Zeilen mit fester Länge. Nachdem Sie solch eine Textdatei in den Arbeitsspeicher gelesen haben, können Sie LINQ zum Abfragen bzw. Ändern der Zeilen verwenden. LINQ-Abfragen vereinfachen zudem die Aufgabe, Daten aus mehreren Quellen zu kombinieren.  
  
 [Vorgehensweise: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Zeigt, wie alle Zeichenfolgen gesucht werden, die in einer Liste, aber nicht in der anderen, vorhanden sind  
  
 [Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Zeigt, wie Textzeilen anhand eines beliebigen Worts oder Felds sortiert werden.  
  
 [Vorgehensweise: Neuordnen der Felder einer durch Trennzeichen getrennten Datei (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Zeigt, wie Felder in einer Zeile in einer CSV-Datei neu angeordnet werden  
  
 [Vorgehensweise: kombinieren und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Zeigt, wie Zeichenfolgenlisten auf verschiedene Weise verbunden werden  
  
 [Vorgehensweise: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Zeigt, wie Auflistungen erstellt werden, indem Sie mehrere Textdateien als Datenquellen verwenden  
  
 [Vorgehensweise: Verknüpfen des Inhalts Unterschiedlicher Dateien (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Zeigt, wie Zeichenfolgen in zwei Listen mit einem übereinstimmenden Schlüssel in einer einzigen Zeichenfolge vereint werden  
  
 [Vorgehensweise: Teilen einer Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Veranschaulicht, wie neue Dateien mithilfe einer einzelnen Datei als Datenquelle erstellt werden  
  
 [Vorgehensweise: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Zeigt, wie mathematische Berechnungen bei Textdaten in CSV-Dateien ausgeführt werden  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Visual Basic)](index.md)  
 [Gewusst wie: Generieren von XML aus CSV-Dateien](how-to-generate-xml-from-csv-files.md)
