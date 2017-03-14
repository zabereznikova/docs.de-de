---
title: "How to: Read From Binary Files in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "binary files, reading from"
  - "I/O [Visual Basic], reading from binary files"
  - "ReadAllBytes method, reading from binary files"
  - "My.Computer.FileSystem object, reading from binary files"
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Read From Binary Files in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Das `My.Computer.FileSystem`\-Objekt stellt für das Lesen von Binärdateien die `ReadAllBytes`\-Methode bereit.  
  
### So lesen Sie eine Binärdatei  
  
-   Verwenden Sie die `ReadAllBytes`\-Methode, die den Inhalt einer Datei als Bytearray zurückgibt.  In diesem Beispiel wird aus der Datei `C:/Documents and Settings/selfportrait.jpg` gelesen.  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]  
  
-   Für große Binärdateien können Sie mit der <xref:System.IO.FileStream.Read%2A>\-Methode des <xref:System.IO.FileStream>\-Objekts jeweils nur eine bestimmte Datenmenge aus der Datei lesen.  Anschließend können Sie einschränken, welcher Anteil der Datei pro Lesevorgang in den Arbeitsspeicher geladen werden soll.  Im folgenden Codebeispiel wird eine Datei kopiert, und der Aufrufer kann angeben, welche Datenmenge der Datei pro Lesevorgang in den Arbeitsspeicher eingelesen werden soll.  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]  
  
## Robuste Programmierung  
 Die folgenden Bedingungen verursachen möglicherweise das Auslösen einer Ausnahme:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   Die Datei ist nicht vorhanden \(<xref:System.IO.FileNotFoundException>\).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E\/A\-Fehler tritt auf \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Es ist nicht genügend Arbeitsspeicher vorhanden, um die Zeichenfolge in den Puffer zu schreiben \(<xref:System.OutOfMemoryException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.  Bei der Datei Form1.vb handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic\-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Storing Data to and Reading from the Clipboard](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)