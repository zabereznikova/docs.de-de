---
title: "How to: Rename a File in Visual Basic | Microsoft Docs"
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
  - "I/O [Visual Basic], renaming files"
  - "files, renaming"
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# How to: Rename a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Verwenden Sie die `RenameFile`\-Methode des `My.Computer.FileSystem`\-Objekts zum Umbenennen von Dateien. Hierbei müssen Sie den aktuellen Speicherort, den Dateinamen und den neuen Dateinamen angeben.  Diese Methode kann nicht zum Verschieben einer Datei verwendet werden. Verwenden Sie in diesem Fall die `MoveFile`\-Methode, um die Datei zu verschieben und umzubenennen.  
  
### So benennen Sie eine Datei um  
  
-   Verwenden Sie zum Umbenennen einer Datei die `My.Computer.FileSystem.RenameFile`\-Methode.  In diesem Beispiel wird die Datei mit dem Namen `Test.txt` in `SecondTest.txt` umbenannt.  
  
     [!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  In der Codeausschnittauswahl finden Sie den Codeausschnitt unter **Dateisystem \- Verarbeiten von Laufwerken, Ordnern und Dateien**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   `newName` enthält Pfadinformationen \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   `newName` ist `Nothing` oder eine leere Zeichenfolge \(<xref:System.ArgumentNullException>\).  
  
-   Die Quelldatei ist ungültig oder nicht vorhanden \(<xref:System.IO.FileNotFoundException>\).  
  
-   Es ist eine Datei oder ein Verzeichnis mit dem in `newName` angegebenen Namen vorhanden \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
-   Der Benutzer verfügt nicht über die erforderliche Berechtigung \(<xref:System.UnauthorizedAccessException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>   
 [Gewusst wie: Verschieben von Dateien](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)   
 [Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)   
 [How to: Create a Copy of a File in the Same Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)