---
title: "Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis in Visual Basic | Microsoft Docs"
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
  - "My.Computer.FileSystem.CopyFile-Methode, Kopieren von Dateien [Visual Basic]"
  - "Dateien, Kopieren"
  - "CopyFile-Methode, Kopieren von Dateien in Visual Basic"
  - "E/A [Visual Basic], Kopieren von Dateien"
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Gewusst wie: Kopieren von Dateien mit einem bestimmten Muster in ein Verzeichnis in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>\-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen. Sie können den `wildCards`\-Parameter verwenden, um ein bestimmtes Muster anzugeben.  
  
 Wenn keine übereinstimmenden Dateien gefunden werden, wird eine leere Auflistung zurückgegeben.  
  
 Mit der <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>\-Methode können Sie die Dateien in ein Verzeichnis kopieren.  
  
### So kopieren Sie Dateien mit einem bestimmten Muster in ein Verzeichnis  
  
1.  Verwenden Sie die `GetFiles`\-Methode, um die Liste der Dateien zurückzugeben. In diesem Beispiel werden alle RTF\-Dateien im angegebenen Verzeichnis zurückgegeben.  
  
     [!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]  
  
2.  Verwenden Sie die `CopyFile`\-Methode, um die Dateien zu kopieren. In diesem Beispiel werden die Dateien in das Verzeichnis `testdirectory` kopiert.  
  
     [!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]  
  
3.  Schließen Sie die `For`\-Anweisung mit einer `Next`\-Anweisung.  
  
     [!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]  
  
## Beispiel  
 Im folgenden Beispiel, das der vollständigen Fassung der oben aufgeführten Codeausschnitte entspricht, werden alle RTF\-Dateien im angegebenen Verzeichnis in das Verzeichnis `testdirectory` kopiert.  
  
 [!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]  
  
## .NET Framework-Sicherheit  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad \(beginnt mit \\\\.\\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   Das Verzeichnis ist nicht vorhanden \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   Das Verzeichnis verweist auf eine vorhandene Datei \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\). Der Benutzer verfügt nicht über die erforderlichen Berechtigungen \(<xref:System.UnauthorizedAccessException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)