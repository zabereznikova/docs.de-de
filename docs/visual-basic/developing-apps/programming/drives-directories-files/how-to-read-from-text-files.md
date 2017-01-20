---
title: "How to: Read From Text Files in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "extended characters, reading"
  - "reading text files"
  - "reading data, text files"
  - "examples [Visual Basic], reading text files"
  - "text files, reading"
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Read From Text Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A>\-Methode des `My.Computer.FileSystem`\-Objekts ermöglicht das Lesen aus einer Textdatei.  Die Dateicodierung kann angegeben werden, wenn beim Inhalt der Datei eine Codierung wie ASCII oder UTF\-8 verwendet wird.  
  
 Wenn Sie aus einer Datei mit erweiterten Zeichen lesen, müssen Sie die Dateicodierung angeben.  
  
> [!NOTE]
>  Um in einer Datei jeweils eine einzelne Textzeile zu lesen, verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A>\-Methode des `My.Computer.FileSystem`\-Objekts.  Die `OpenTextFileReader`\-Methode gibt ein <xref:System.IO.StreamReader>\-Objekt zurück.  Mithilfe der <xref:System.IO.StreamReader.ReadLine%2A>\-Methode des `StreamReader`\-Objekts kann jeweils eine Zeile in einer Datei gelesen werden.  Sie können mit der <xref:System.IO.StreamReader.EndOfStream%2A>\-Methode des `StreamReader`\-Objekts einen Test für das Ende der Datei ausführen.  
  
### So lesen Sie eine Textdatei  
  
-   Verwenden Sie die `ReadAllText`\-Methode des `My.Computer.FileSystem`\-Objekts, um unter Angabe des Pfads den Inhalt einer Textdatei in eine Zeichenfolge zu lesen.  Im folgenden Beispiel wird der Inhalt von test.txt in eine Zeichenfolge gelesen und anschließend in einem Meldungsfeld angezeigt.  
  
     [!code-vb[VbFileIORead#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-fi_1_1.vb)]  
  
### So lesen Sie aus einer codierten Textdatei  
  
-   Verwenden Sie die `ReadAllText`\-Methode des `My.Computer.FileSystem`\-Objekts, um unter Angabe des Pfads und der Dateicodierung den Inhalt einer Textdatei in eine Zeichenfolge zu lesen.  Im folgenden Beispiel wird der Inhalt der UTF32\-Datei test.txt in eine Zeichenfolge gelesen und anschließend in einem Meldungsfeld angezeigt.  
  
     [!code-vb[VbFileIORead#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-fi_1_2.vb)]  
  
## Robuste Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   Die Datei ist nicht vorhanden \(<xref:System.IO.FileNotFoundException>\).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E\/A\-Fehler tritt auf \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben \(<xref:System.OutOfMemoryException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.  Bei der Datei Form1.vb handelt es sich zum Beispiel nicht unbedingt um eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [How to: Read From Comma\-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)