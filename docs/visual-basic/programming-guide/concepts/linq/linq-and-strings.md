---
title: LINQ und Zeichenfolgen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a79d1427331070da9c545fdd3175115fe187e879
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-strings-visual-basic"></a>LINQ und Zeichenfolgen (Visual Basic)
LINQ kann Abfragen und Umwandeln von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden. Es kann besonders bei halbstrukturierten Daten in Textdateien sein. LINQ-Abfragen können mit herkömmlichen Zeichenfolgenfunktionen und regulären Ausdrücken kombiniert werden. Beispielsweise können Sie die <xref:System.String.Split%2A>oder <xref:System.Text.RegularExpressions.Regex.Split%2A>Methode, um ein Array von Zeichenfolgen zu erstellen, die Sie dann Abfragen oder ändern, indem Sie mithilfe von LINQ.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> Sie können die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>-Methode in der `where` -Klausel einer LINQ-Abfrage.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A> Und Sie können LINQ zum Abfragen und Ändern der <xref:System.Text.RegularExpressions.MatchCollection>von einem regulären Ausdruck zurückgegebenen Ergebnisse.</xref:System.Text.RegularExpressions.MatchCollection>  
  
 In diesem Abschnitt beschriebenen Techniken können auch teilweise strukturierten Textdaten in XML transformieren. Weitere Informationen finden Sie unter [Gewusst wie: Generieren von XML aus CSV-Dateien](how-to-generate-xml-from-csv-files.md).  
  
 In den Beispielen in diesem Abschnitt werden in zwei Kategorien unterteilt:  
  
## <a name="querying-a-block-of-text"></a>Abfragen eines Textblocks  
 Können Sie Abfragen, analysieren und Ändern von Textblöcken durch Aufteilen des Vorgangs in ein abfragbares Array kleinerer Zeichenfolgen mithilfe der <xref:System.String.Split%2A>-Methode oder die <xref:System.Text.RegularExpressions.Regex.Split%2A>-Methode.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A> Sie können den Quelltext Wörtern, Sätzen, Absätzen, Seiten oder andere Kriterien aufteilen und dann zusätzliche Teilungen ausführen, wenn sie in der Abfrage erforderlich sind.  
  
 [Gewusst wie: zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (Visual Basic)](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 Zeigt die Verwendung von LINQ für einfache Abfragen von Text.  
  
 [Gewusst wie: Abfragen von Sätzen, die eine angegebene Gruppe von Wörtern (LINQ) (Visual Basic) enthalten.](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 Erfahren, wie Textdateien an willkürlichen Grenzen geteilt und zum Ausführen von Abfragen für jeden Teil.  
  
 [Gewusst wie: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)](how-to-query-for-characters-in-a-string-linq.md)  
 Veranschaulicht, dass eine Zeichenfolge ein abfragbarer Typ ist.  
  
 [Gewusst wie: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md)  
 Zeigt, wie reguläre Ausdrücke in LINQ-Abfragen für komplexe Mustervergleiche auf gefilterte Abfrageergebnisse verwenden.  
  
## <a name="querying-semi-structured-data-in-text-format"></a>Abfragen halbstrukturierter Daten im Text-Format  
 Viele verschiedene Typen von Textdateien bestehen aus einer Reihe von Zeilen, die häufig mit ähnlicher Formatierung, z. B. durch Tabstopps oder Kommas getrennten Dateien oder Zeilen von fester Länge. Nachdem Sie solch eine Textdatei in den Arbeitsspeicher gelesen haben, können Sie LINQ Abfragen und/oder ändern die Zeilen. LINQ-Abfragen vereinfachen zudem die Aufgabe, Daten aus mehreren Quellen zu kombinieren.  
  
 [Gewusst wie: Suchen der festgelegten Differenz zwischen zwei Listen (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)  
 Zeigt, wie alle Zeichenfolgen suchen, die in einer Liste, aber nicht in der anderen vorhanden sind.  
  
 [Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 Zeigt, wie Textzeilen basierend auf einem beliebigen Wort oder Feld sortieren.  
  
 [Gewusst wie: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (Visual Basic)](how-to-reorder-the-fields-of-a-delimited-file.md)  
 Zeigt, wie Felder in einer Zeile in eine CSV-Datei neu angeordnet.  
  
 [Gewusst wie: kombinieren und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)  
 Zeigt, wie Zeichenfolgenlisten auf verschiedene Weise zu kombinieren.  
  
 [Gewusst wie: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 Zeigt, wie Auflistungen zu erstellen, indem Sie mehrere Textdateien als Datenquellen verwenden.  
  
 [Gewusst wie: Verknüpfen des Inhalts von unähnlichen Dateien (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)  
 Zeigt, wie Zeichenfolgen in zwei Listen mit einem übereinstimmenden Schlüssel in einer einzigen Zeichenfolge zu kombinieren.  
  
 [Gewusst wie: Teilen eine Datei in mehrere Dateien mithilfe von Gruppen (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 Veranschaulicht das Erstellen neuer Dateien mithilfe einer einzigen Datei als Datenquelle.  
  
 [Gewusst wie: Berechnen von Spaltenwerten in einer CSV-Textdatei (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 Zeigt, wie mathematische Berechnungen auf Text-Daten in CSV-Dateien ausführen.  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Visual Basic)](index.md)   
 [Gewusst wie: Generieren von XML aus CSV-Dateien](how-to-generate-xml-from-csv-files.md)

