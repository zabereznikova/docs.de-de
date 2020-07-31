---
title: LINQ und Dateiverzeichnisse (C#)
description: Diese C#-LINQ-Ressourcen für Dateisystemvorgänge werden nicht zum Ändern des Inhalts der Dateien oder Ordner verwendet.
ms.date: 07/20/2015
ms.assetid: b66c55e4-0f72-44e5-b086-519f9962335c
ms.openlocfilehash: ac00e29f90ee1c04ab9978b6ada3ae5f28991a1c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165664"
---
# <a name="linq-and-file-directories-c"></a>LINQ und Dateiverzeichnisse (C#)

Viele Dateisystemvorgänge sind im Wesentlichen Abfragen und sind deshalb für die LINQ-Vorgehensweise gut geeignet.  
  
 Die Abfragen in diesem Abschnitt sind nicht destruktiv. Sie werden nicht verwendet, um den Inhalt der ursprünglichen Dateien und Ordner zu ändern. Dies entspricht der Regel, nach der Abfragen keine Nebeneffekte haben sollen. Allgemein gilt, dass jeder Code (einschließlich Abfragen, die Operatoren zum Erstellen/Aktualisieren/Löschen ausführen), der Quelldaten modifiziert, von Code getrennt sein sollte, der Daten lediglich abfragt.  
  
 Dieser Abschnitt enthält die folgenden Themen:  
  
 [Vorgehensweise: Abfragen von Dateien mit einem angegebenen Attribut oder Namen (C#)](./how-to-query-for-files-with-a-specified-attribute-or-name.md)\
 Hier erfahren Sie, wie Sie nach Dateien suchen, indem Sie eine oder mehrere Eigenschaften des Objekts <xref:System.IO.FileInfo> betrachten.  
  
 [Vorgehensweise: Gruppieren von Dateien nach Erweiterung (LINQ) (C#)](./how-to-group-files-by-extension-linq.md)\
 Hier erfahren Sie, wie Sie Gruppen des Objekts <xref:System.IO.FileInfo> nach deren Dateinamenerweiterung zurückgeben.  
  
 [Vorgehensweise: Abfragen der Gesamtzahl an Bytes in einem Ordnersatz (LINQ) (C#)](./how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)\
 Hier erfahren Sie, wie Sie die Gesamtzahl von Bytes in allen Dateien einer angegebenen Verzeichnisstruktur zurückgeben.  
  
 [Vorgehensweise: Vergleichen des Inhalts von zwei Ordnern (LINQ) (C#)](./how-to-compare-the-contents-of-two-folders-linq.md)  
 Hier erfahren Sie, wie Sie alle Dateien, die sich ein zwei angegebenen Ordnern befinden, zurückgeben können; ebenso erfahren Sie, wie Sie die Dateien, die sich nur in einem der zwei Ordner befinden, zurückgeben können.  
  
 [Vorgehensweise: Abfragen der größten Datei oder der größten Dateien in einer Verzeichnisstruktur (LINQ) (C#)](./how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)\
 Hier erfahren Sie, wie Sie die größte oder kleinste Datei oder eine angegebene Anzahl von Dateien in einer Verzeichnisstruktur zurückgeben können.  
  
 [Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur (LINQ) (C#)](./how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)\
 Hier erfahren Sie, wie Sie die Dateien nach Dateinamen gruppieren können, die an mehr als einer Stelle in einer angegebenen Verzeichnisstruktur vorkommen. Ebenfalls lernen Sie, wie sie komplexere Vergleiche mit einer benutzerdefinierten Vergleichsfunktion durchführen können.  
  
 [Vorgehensweise: Abfragen des Inhalts von Dateien in einem Ordner (LINQ) (C#)](./how-to-query-the-contents-of-files-in-a-folder-lin.md)\
 Hier erfahren Sie, wie Sie Ordner in einer Struktur durchlaufen, jede Datei öffnen und die Inhalte der Datei abfragen können.  
  
## <a name="comments"></a>Kommentare  
 Das Erstellen einer Datenquelle, die die Inhalte des Dateisystems angemessen repräsentieren, kommt mit einer gewissen Komplexität. Die Beispiele in diesem Abschnitt geben Ihnen einen ersten Überblick über <xref:System.IO.FileInfo>-Objekte, der alle Dateien in einem angegebenen Stammordner mit all seinen Unterordnern repräsentiert. Der tatsächliche Zustand jedes <xref:System.IO.FileInfo> verändert sich möglicherweise in der Zeit zwischen Beginn und Ende der Ausführung einer Abfrage. Sie können beispielsweise eine Liste von <xref:System.IO.FileInfo>-Objekten erstellen, um diese als Datenquelle zu verwenden. Wenn Sie versuchen, auf die Eigenschaft `Length` einer Abfrage zuzugreifen, versucht das <xref:System.IO.FileInfo>-Objekt, auf das Dateisystem zuzugreifen, um den Wert von `Length` zu aktualisieren. Wenn die Datei nicht mehr existiert, erhalten Sie eine <xref:System.IO.FileNotFoundException> in Ihrer Abfrage, obwohl Sie keine direkte Abfrage an das Dateisystem vornehmen. Einige Abfragen in diesem Bereich verwenden eine getrennte Methode, die diese bestimmten Ausnahmen in gewissen Fällen verarbeitet. Des Weiteren können Sie Ihre Datenquelle auf dem neuesten Stand halten, indem Sie den <xref:System.IO.FileSystemWatcher> verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (C#)](./linq-to-objects.md)
