---
title: "How to: Append to Text Files in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "I/O [Visual Basic], appending to files"
  - "I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method"
  - "I/O [Visual Basic], WriteAllText method"
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Append to Text Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit der <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>\-Methode können Daten an eine Textdatei angefügt werden, indem der `append`\-Parameter auf `True` festgelegt wird.  
  
### So fügen Sie Daten an eine Textdatei an  
  
-   Verwenden Sie die `WriteAllText`\-Methode. Geben Sie die Zieldatei und die anzufügende Zeichenfolge an, und legen Sie den `append`\-Parameter auf `True` fest.  
  
     In diesem Beispiel wird die Zeichenfolge `"This is a test string."` in die Datei `Testfile.txt` geschrieben.  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   `File` zeigt auf einen Pfad, der nicht vorhanden ist \(<xref:System.IO.FileNotFoundException> oder <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E\/A\-Fehler tritt auf \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)