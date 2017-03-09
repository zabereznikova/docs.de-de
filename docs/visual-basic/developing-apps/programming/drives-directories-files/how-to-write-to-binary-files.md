---
title: "How to: Write to Binary Files in Visual Basic | Microsoft Docs"
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
  - "files, binary access"
  - "WriteAllBytes method"
  - "binary files, writing in Visual Basic"
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Write to Binary Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>\-Methode schreibt Daten in eine Binärdatei.  Wenn der `append`\-Parameter `True` ist, werden die Daten an die Datei angefügt, andernfalls werden die Daten in der Datei überschrieben.  
  
 Wenn der angegebene Pfad ohne den Dateinamen ungültig ist, wird eine <xref:System.IO.DirectoryNotFoundException>\-Ausnahme ausgelöst.  Wenn der Pfad gültig ist, die Datei aber nicht vorhanden ist, wird die Datei erstellt.  
  
### So schreiben Sie in eine Binärdatei  
  
-   Verwenden Sie die `WriteAllBytes`\-Methode, und geben Sie dabei den Dateipfad und den Namen sowie die Bytes an, die geschrieben werden sollen.  In diesem Beispiel wird das Datenarray `CustomerData` an die Datei `CollectedData.dat` angefügt.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-to-binary-f_1.vb)]  
  
## Robuste Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, oder er enthält ungültige Zeichen.  \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   `File` zeigt auf einen Pfad, der nicht vorhanden ist \(<xref:System.IO.FileNotFoundException> oder <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E\/A\-Fehler tritt auf \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [How to: Write Text to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)