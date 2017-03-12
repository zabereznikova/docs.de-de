---
title: "How to: Write Text to Files in Visual Basic | Microsoft Docs"
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
  - "files, writing to"
  - "text, writing to files"
  - "writing to files"
  - "examples [Visual Basic], text files"
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Write Text to Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>\-Methode kann verwendet werden, um Text in Dateien zu schreiben.  Wenn die angegebene Datei nicht vorhanden ist, wird diese erstellt.  
  
## Verfahren  
  
#### So schreiben Sie Text in eine Datei  
  
-   Verwenden Sie die `WriteAllText`\-Methode, um Text in eine Datei zu schreiben. Geben Sie dabei die Datei und den gewünschten Text an.  In diesem Beispiel wird die Zeile `"This is new text."` in die Datei mit dem Namen `test.txt` geschrieben, wobei der Text an bereits bestehenden Text in der Datei angehängt wird.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-files_1.vb)]  
  
#### So schreiben Sie eine Reihe von Zeichenfolgen in eine Datei  
  
-   Durchlaufen Sie die Zeichenfolgenauflistung.  Verwenden Sie die `WriteAllText`\-Methode, um Text in eine Datei zu schreiben. Geben Sie dabei die Zieldatei und die hinzuzufügende Zeichenfolge an, und legen Sie `append` auf `True` fest.  
  
     In diesem Beispiel werden die Namen der Dateien im Verzeichnis `Documents and Settings` in die Datei `FileList.txt` geschrieben. Zur besseren Lesbarkeit wird jeweils ein Wagenrücklaufzeichen eingefügt.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-files_2.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Pfad ist aus einem der folgenden Gründe ungültig: Es handelt sich um eine Zeichenfolge der Länge 0, der Pfad enthält nur Leerzeichen, er enthält ungültige Zeichen, oder es handelt sich um einen Gerätepfad \(beginnt mit \\\\.  \\\) \(<xref:System.ArgumentException>\).  
  
-   Der Pfad ist ungültig, da er `Nothing` ist \(<xref:System.ArgumentNullException>\).  
  
-   `File` zeigt auf einen Pfad, der nicht vorhanden ist \(<xref:System.IO.FileNotFoundException> oder <xref:System.IO.DirectoryNotFoundException>\).  
  
-   Die Datei wird von einem anderen Prozess verwendet, oder ein E\/A\-Fehler tritt auf \(<xref:System.IO.IOException>\).  
  
-   Der Pfad überschreitet die im System definierte maximale Länge \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Pfad eines Datei\- oder Verzeichnisnamens enthält einen Doppelpunkt \(:\) oder hat ein ungültiges Format \(<xref:System.NotSupportedException>\).  
  
-   Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades \(<xref:System.Security.SecurityException>\).  
  
-   Der Datenträger ist voll, und der Aufruf von `WriteAllText` schlägt fehl \(<xref:System.IO.IOException>\).  
  
 Bei Ausführung in einem teilweise vertrauenswürdigen Kontext kann der Code aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen finden Sie unter [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 [How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)