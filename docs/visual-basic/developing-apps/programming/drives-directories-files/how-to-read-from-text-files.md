---
title: 'Vorgehensweise: Lesen von Textdateien in Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- extended characters, reading
- reading text files
- reading data, text files
- examples [Visual Basic], reading text files
- text files, reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4ea4f6ebfaf06a8b2b5d161d9986eebd28f50d5b
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-from-text-files-in-visual-basic"></a>Gewusst wie: Lesen von Textdateien in Visual Basic
Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A>-Methode des `My.Computer.FileSystem`-Objekts ermöglicht das Lesen aus einer Textdatei. Die Dateicodierung kann angegeben werden, wenn beim Inhalt der Datei eine Codierung wie ASCII oder UTF-8 verwendet wird.  
  
 Wenn Sie aus einer Datei mit erweiterten Zeichen lesen, müssen Sie die Dateicodierung angeben.  
  
> [!NOTE]
>  Um in einer Datei jeweils eine einzelne Textzeile zu lesen, verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A>-Methode des `My.Computer.FileSystem`-Objekts. Die `OpenTextFileReader`-Methode gibt ein <xref:System.IO.StreamReader>-Objekt zurück. Mithilfe der <xref:System.IO.StreamReader.ReadLine%2A>-Methode des `StreamReader`-Objekts kann jeweils eine Zeile in einer Datei gelesen werden. Sie können mit der <xref:System.IO.StreamReader.EndOfStream%2A>-Methode des `StreamReader`-Objekts einen Test für das Ende der Datei ausführen.  
  
### <a name="to-read-from-a-text-file"></a>So lesen Sie eine Textdatei  
  
-   Verwenden Sie die `ReadAllText`-Methode des `My.Computer.FileSystem`-Objekts, um unter Angabe des Pfads den Inhalt einer Textdatei in eine Zeichenfolge zu lesen. Im folgenden Beispiel wird der Inhalt von test.txt in eine Zeichenfolge gelesen und anschließend in einem Meldungsfeld angezeigt.  
  
     [!code-vb[VbFileIORead#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_1.vb)]  
  
### <a name="to-read-from-a-text-file-that-is-encoded"></a>So lesen Sie aus einer codierten Textdatei  
  
-   Verwenden Sie die `ReadAllText`-Methode des `My.Computer.FileSystem`-Objekts, um unter Angabe des Pfads und der Dateicodierung den Inhalt einer Textdatei in eine Zeichenfolge zu lesen. Im folgenden Beispiel wird der Inhalt der UTF32-Datei test.txt in eine Zeichenfolge gelesen und anschließend in einem Meldungsfeld angezeigt.  
  
     [!code-vb[VbFileIORead#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_2.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad (<xref:System.ArgumentException>).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).  
  
-   Die Datei ist nicht vorhanden (<xref:System.IO.FileNotFoundException>).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E/A-Fehler tritt auf (<xref:System.IO.IOException>).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).  
  
-   Der Pfad eines Datei- oder Verzeichnisnamens enthält einen Doppelpunkt (:) oder hat ein ungültiges Format (<xref:System.NotSupportedException>).  
  
-   Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben (<xref:System.OutOfMemoryException>).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens. Bei der Datei Form1.vb handelt es sich zum Beispiel nicht unbedingt um eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden. Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>   
 [Lesen aus Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Gewusst wie: Lesen aus durch Kommas getrennten Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [Gewusst wie: Lesen aus einer Textdatei mit fester Breite](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Gewusst wie: Lesen aus Textdateien mit mehreren Formaten](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Problembehandlung: Lesen aus und Schreiben in Textdateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Dateicodierungen](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
