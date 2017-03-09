---
title: "How to: Find Subdirectories with a Specific Pattern in Visual Basic | Microsoft Docs"
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
  - "pattern matching"
  - "folders, finding"
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Find Subdirectories with a Specific Pattern in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>\-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Unterverzeichnisse in einem Verzeichnis darstellen.  Sie können mithilfe des `wildCards`\-Parameters ein bestimmtes Muster angeben.  Wenn Sie den Inhalt von Unterverzeichnissen in die Suche einbeziehen möchten, legen Sie den `searchType`\-Parameter auf `SearchOption.SearchAllSubDirectories` fest.  
  
 Wenn keine Verzeichnisse gefunden werden, die mit dem angegebenen Muster übereinstimmen, wird eine leere Auflistung zurückgegeben.  
  
### So suchen Sie Unterverzeichnisse mit einem bestimmten Muster  
  
-   Verwenden Sie die `GetDirectories`\-Methode, und geben Sie dabei den Namen und den Pfad des zu durchsuchenden Verzeichnisses an.  Im folgenden Beispiel werden alle Verzeichnisse in der Verzeichnisstruktur zurückgegeben, deren Name das Wort "Logs" enthält, und die Verzeichnisse werden `ListBox1` hinzugefügt.  
  
     [!code-vb[VbVbcnFileAccess#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-find-subdirectori_1.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   Mindestens eines der angegebenen Platzhalterzeichen ist `Nothing`, eine leere Zeichenfolge oder enthält nur Leerzeichen \(<xref:System.ArgumentNullException>\).  
  
-   `directory` ist nicht vorhanden \(<xref:System.IO.DirectoryNotFoundException>\).  
  
-   `directory` zeigt auf eine vorhandene Datei \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Ein Datei\- oder Ordnername im Pfad enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
-   Der Benutzer verfügt nicht über die erforderlichen Berechtigungen \(<xref:System.UnauthorizedAccessException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>   
 [How to: Find Files with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)