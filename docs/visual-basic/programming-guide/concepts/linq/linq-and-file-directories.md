---
title: LINQ und Dateiverzeichnisse (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5536ae95b42cdaddda2c4cae97a114681e94b0ab
ms.lasthandoff: 03/13/2017

---
# <a name="linq-and-file-directories-visual-basic"></a>LINQ und Dateiverzeichnisse (Visual Basic)
Viele Dateisystemvorgänge sind im Wesentlichen Abfragen und sind daher für die LINQ-Ansatz gut geeignet.  
  
 Beachten Sie, dass die Abfragen in diesem Abschnitt nicht destruktiv sind. Sie werden nicht verwendet, um den Inhalt der ursprünglichen Dateien oder Ordner ändern. Dies entspricht die Regel, dass Abfragen keine Nebeneffekte auftreten soll. Im Allgemeinen sollten Code (einschließlich Abfragen, erstellen, Update- und delete-Operatoren), der Quelldaten modifiziert getrennt vom Code beibehalten werden, die die Daten lediglich Abfragen.  
  
 Dieser Abschnitt enthält die folgenden Themen:  
  
 [Gewusst wie: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 Veranschaulicht, wie zur Suche nach Dateien anhand einer oder mehrerer Eigenschaften seiner <xref:System.IO.FileInfo>Objekt.</xref:System.IO.FileInfo>  
  
 [Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 Zeigt, wie Gruppen zurückzugeben <xref:System.IO.FileInfo>-Objekt auf Grundlage ihrer Erweiterung.</xref:System.IO.FileInfo>  
  
 [Gewusst wie: Abfragen der Gesamtzahl von Bytes in einem Ordnersatz (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 Zeigt, wie die Gesamtanzahl der Bytes in allen Dateien in einer angegebenen Verzeichnisstruktur zurückgegeben.  
  
 [Gewusst wie: Vergleichen des Inhalts von zwei Ordnern (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s  
 Zeigt, wie alle Dateien, die in zwei angegebenen Ordnern vorhanden sind, und auch alle Dateien, die in einem Ordner, aber nicht in der anderen vorhanden sind.  
  
 [Gewusst wie: Abfragen der größten Datei oder Dateien in einer Verzeichnisstruktur (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 Zeigt, wie die größten oder kleinsten Datei oder eine angegebene Anzahl von Dateien in einer Verzeichnisstruktur zurückgegeben.  
  
 [Gewusst wie: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 Zeigt, wie alle Dateinamen gruppiert, die in mehr als einer Position in einer angegebenen Verzeichnisstruktur auftreten. Außerdem veranschaulicht, wie komplexere Vergleiche basierend auf einem benutzerdefinierten Vergleich ausgeführt.  
  
 [Gewusst wie: Abfragen des Inhalts von Dateien in einem Ordner (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 Zeigt, wie Ordner in einer Struktur durchlaufen, öffnen jede Datei und Inhalt der Datei abgefragt.  
  
## <a name="comments"></a>Kommentare  
 Es ist recht aufwändig in Erstellen einer Datenquelle, die genau stellt den Inhalt des Dateisystems und Ausnahmen ordnungsgemäß behandelt. In den Beispielen in diesem Abschnitt erstellen Sie eine Snapshot-Auflistung von <xref:System.IO.FileInfo>-Objekten, die alle Dateien in einem angegebenen Stammordner und allen Unterordnern darstellt.</xref:System.IO.FileInfo> Der aktuelle Status der einzelnen <xref:System.IO.FileInfo>ändert sich die Zeit zwischen den Sie starten und Beenden einer Abfrage möglicherweise.</xref:System.IO.FileInfo> Sie können z. B. eine Liste der erstellen <xref:System.IO.FileInfo>Objekte, die als Datenquelle verwendet.</xref:System.IO.FileInfo> Wenn Sie versuchen, Zugriff auf die `Length` Eigenschaft in einer Abfrage, die <xref:System.IO.FileInfo>Objekt versucht, Zugriff auf das Dateisystem, um den Wert der aktualisieren `Length`.</xref:System.IO.FileInfo> Wenn die Datei nicht mehr vorhanden ist, erhalten Sie eine <xref:System.IO.FileNotFoundException>in einer Abfrage, auch wenn nicht abgefragt werden das Dateisystem direkt.</xref:System.IO.FileNotFoundException> Einige Abfragen in diesem Abschnitt verwenden Sie eine separate Methode, die diese bestimmten Ausnahmen in bestimmten Fällen nutzt. Eine weitere Option ist die Datenquelle dynamisch aktualisiert werden, mithilfe der <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher> beizubehalten  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
