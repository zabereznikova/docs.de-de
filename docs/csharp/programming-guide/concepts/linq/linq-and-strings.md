---
title: LINQ und Zeichenfolgen (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 49c51595ffff45df503308b9eba55fc67b4da2e8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-strings-c"></a>LINQ und Zeichenfolgen (C#)
LINQ kann zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden. Dieses Verfahren ist bei halbstrukturierten Daten in Textdateien besonders nützlich. LINQ-Abfragen können mit herkömmlichen Zeichenfolgenfunktionen und regulären Ausdrücken verbunden werden. Beispielsweise können Sie die Methode <xref:System.String.Split%2A> oder <xref:System.Text.RegularExpressions.Regex.Split%2A> verwenden, um ein Array von Zeichenfolgen zu erstellen, das Sie anschließend mit LINQ abfragen oder ändern können. Sie können die Methode <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> in der `where`-Klausel einer LINQ-Abfrage verwenden. Sie können LINQ außerdem zum Abfragen und Ändern der <xref:System.Text.RegularExpressions.MatchCollection>-Ergebnisse, die von einem regulären Ausdruck zurückgegeben werden, verwenden.  
  
 Sie können auch die Techniken verwenden, die in diesem Abschnitt beschrieben werden, um halbstrukturierte Textdaten in XML zu transformieren. Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von XML aus CSV-Dateien](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd).  
  
 Die Beispiele in diesem Abschnitt gehören zu einer der folgenden beiden Kategorien:  
  
## <a name="querying-a-block-of-text"></a>Abfragen eines Textblocks  
 Sie können Textblöcke abfragen, analysieren und ändern, indem Sie sie mithilfe der <xref:System.String.Split%2A>- oder der <xref:System.Text.RegularExpressions.Regex.Split%2A>-Methode in ein abfragbares Array von kleineren Zeichenfolgen aufteilen. Sie können den Quelltext in Wörter, Sätze, Absätze, Paragraphen, Seiten oder andere Kriterien unterteilen und anschließend andere Unterteilungen ausführen, wenn sie in Ihrer Abfrage benötigt werden.  
  
 [Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Zeigt die Verwendung von LINQ für einfache Textabfragen.  
  
 [Vorgehensweise: Abfragen von Sätzen, die bestimmte Wörter enthalten (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)  
 Zeigt, wie Textdateien an beliebigen Grenzen unterteilt wird und wie Abfragen mit jedem Teil ausgeführt werden.  
  
 [Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-characters-in-a-string-linq.md)  
 Veranschaulicht, dass eine Zeichenfolge ein abfragbarer Typ ist.  
  
 [Vorgehensweise: Verbinden von LINQ-Abfragen mit regulären Ausdrücken (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)  
 Zeigt, wie reguläre Ausdrücke in LINQ-Abfragen für komplexe Musterabgleiche bei gefilterten Abfrageergebnissen verwendet werden.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Abfragen halbstrukturierter Daten im Textformat  
 Viele verschiedene Typen von Textdateien bestehen aus einer Reihe von Zeilen, die häufig mit ähnlicher Formatierung, z.B. durch Tabstopps oder Kommas getrennten Dateien oder Zeilen mit fester Länge. Nachdem Sie solch eine Textdatei in den Arbeitsspeicher gelesen haben, können Sie LINQ zum Abfragen bzw. Ändern der Zeilen verwenden. LINQ-Abfragen vereinfachen zudem die Aufgabe, Daten aus mehreren Quellen zu kombinieren.  
  
 [Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)  
 Zeigt, wie alle Zeichenfolgen gesucht werden, die in einer Liste, aber nicht in der anderen, vorhanden sind  
  
 [Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Zeigt, wie Textzeilen anhand eines beliebigen Worts oder Felds sortiert werden.  
  
 [Vorgehensweise: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-reorder-the-fields-of-a-delimited-file-linq.md)  
 Zeigt, wie Felder in einer Zeile in einer CSV-Datei neu angeordnet werden  
  
 [Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)  
 Zeigt, wie Zeichenfolgenlisten auf verschiedene Weise verbunden werden  
  
 [Vorgehensweise: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Zeigt, wie Auflistungen erstellt werden, indem Sie mehrere Textdateien als Datenquellen verwenden  
  
 [Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)  
 Zeigt, wie Zeichenfolgen in zwei Listen mit einem übereinstimmenden Schlüssel in einer einzigen Zeichenfolge vereint werden  
  
 [Vorgehensweise: Teilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Veranschaulicht, wie neue Dateien mithilfe einer einzelnen Datei als Datenquelle erstellt werden  
  
 [Vorgehensweise: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Zeigt, wie mathematische Berechnungen bei Textdaten in CSV-Dateien ausgeführt werden  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)   
 [Gewusst wie: Generieren von XML aus CSV-Dateien](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)

