---
title: "How to: Read From Comma-Delimited Text Files in Visual Basic | Microsoft Docs"
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
  - "files, parsing"
  - "text files, tasks"
  - "reading text files, comma-delimited"
  - "text files, reading"
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Read From Comma-Delimited Text Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit dem `TextFieldParser`\-Objekt können strukturierte Textdateien, z. B. Protokolle, leicht und effizient analysiert werden.  Die `TextFieldType`\-Eigenschaft definiert, ob es sich um eine Datei mit Trennzeichen oder um eine Datei mit Textfeldern fester Breite handelt.  
  
### So analysieren Sie eine durch Kommas getrennte Textdatei  
  
1.  Erstellen Sie einen neuen `TextFieldParser`.  Im folgenden Code wird ein `TextFieldParser` mit dem Namen `MyReader` erstellt und die Datei `test.txt` geöffnet.  
  
     [!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-deli_1.vb)]  
  
2.  Definieren Sie den `TextField`\-Typ und das Trennzeichen.  Im folgenden Code wird die `TextFieldType`\-Eigenschaft als `Delimited` festgelegt und das Trennzeichen "," definiert.  
  
     [!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-deli_2.vb)]  
  
3.  Die Felder in der Datei werden durchlaufen.  Falls eine beschädigte Zeile gefunden wird, wird ein Fehler gemeldet und die Analyse fortgesetzt.  Im folgenden Code wird die Datei durchlaufen, jedes Feld angezeigt und alle Felder ausgegeben, die nicht korrekt formatiert sind.  
  
     [!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-deli_3.vb)]  
  
4.  Der `While`\-Block und der `Using`\-Block werden mit `End While` und `End Using` geschlossen.  
  
     [!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-deli_4.vb)]  
  
## Beispiel  
 In diesem Beispiel wird aus der Datei `test.txt` gelesen.  
  
 [!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-comma-deli_5.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Eine Zeile kann nicht mit dem angegebenen Format analysiert werden \(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  In der Ausnahmemeldung wird die Nummer der Zeile angegeben, die die Ausnahme verursacht hat. Der in der Zeile enthaltene Text wird der <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>\-Eigenschaft zugewiesen.  
  
-   Die angegebene Datei ist nicht vorhanden \(<xref:System.IO.FileNotFoundException>\).  
  
-   Es besteht eine teilweise vertrauenswürdige Situation, in der der Benutzer nicht über ausreichende Berechtigungen für den Zugriff auf die Datei verfügt.  \(<xref:System.Security.SecurityException>\).  
  
-   Der Pfad ist zu lang \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Benutzer verfügt nicht über ausreichende Berechtigungen für den Zugriff auf die Datei \(<xref:System.UnauthorizedAccessException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [Problembehandlung bei Ausnahmen: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)