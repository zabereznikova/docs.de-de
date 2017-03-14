---
title: "How to: Find Files with a Specific Pattern in Visual Basic | Microsoft Docs"
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
  - "files, finding"
  - "pattern matching"
  - "patterns, matching"
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# How to: Find Files with a Specific Pattern in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>\-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Dateien darstellen.  Sie können mithilfe des `wildCards`\-Parameters ein bestimmtes Muster angeben.  Wenn Sie Unterverzeichnisse in der Suche berücksichtigen möchten, legen Sie den `searchType`\-Parameter auf `SearchOption.SearchAllSubDirectories` fest.  
  
 Wenn keine Dateien gefunden werden, die mit dem angegebenen Muster übereinstimmen, wird eine leere Auflistung zurückgegeben.  
  
> [!NOTE]
>  Informationen zum Zurückgeben einer Dateiliste, indem Sie die `DirectoryInfo`\-Klasse des `System.IO`\-Namespace verwenden, finden Sie unter <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### So suchen Sie Dateien mit einem angegebenen Muster  
  
-   Verwenden Sie die `GetFiles`\-Methode, und geben Sie dabei den Namen und den Pfad des zu durchsuchenden Verzeichnisses sowie das gesuchte Muster an.  Im folgenden Beispiel werden alle Dateien im Verzeichnis mit der Erweiterung `.dll` zurückgegeben und `ListBox1` hinzugefügt.  
  
     [!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]  
  
## .NET Framework-Sicherheit  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   `directory` ist nicht vorhanden \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   `directory` zeigt auf eine vorhandene Datei \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Ein Datei\- oder Ordnername im Pfad enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
-   Der Benutzer verfügt nicht über die erforderlichen Berechtigungen \(<xref:System.UnauthorizedAccessException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)