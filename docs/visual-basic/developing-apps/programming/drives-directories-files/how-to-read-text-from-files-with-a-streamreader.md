---
title: "How to: Read Text from Files with a StreamReader (Visual Basic) | Microsoft Docs"
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
  - "reading files, text"
  - "text, reading from files"
  - "reading text from files"
  - "files, reading"
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Read Text from Files with a StreamReader (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Das `My.Computer.FileSystem`\-Objekt stellt Methoden bereit, mit denen ein <xref:System.IO.TextReader> und ein <xref:System.IO.TextWriter> geöffnet werden kann.  Die `OpenTextFileWriter`\-Methode und die `OpenTextFileReader`\-Methode sind erweiterte Methoden, die in IntelliSense nur dann angezeigt werden, wenn Sie die Registerkarte **Alle** auswählen.  
  
### So lesen mit einem Textreader eine Zeile aus einer Datei  
  
-   Verwenden Sie die `OpenTextFileReader`\-Methode, um den <xref:System.IO.TextReader> unter Angabe einer Datei zu öffnen.  In diesem Beispiel wird die Datei `testfile.txt` geöffnet, es wird eine Zeile aus der Datei gelesen, und die Zeile wird in einem Meldungsfeld angezeigt.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## Robuste Programmierung  
 Bei der zu lesenden Datei muss es sich um eine Textdatei handeln.  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.  Bei der Datei Form1.vb handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic\-Quelldatei.  
  
 Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.  
  
## .NET Framework-Sicherheit  
 Zum Lesen einer Datei benötigt die Assembly eine Berechtigungsebene, die von der <xref:System.Security.Permissions.FileIOPermission>\-Klasse gewährt werden muss.  Bei Ausführung in einem teilweise vertrauenswürdigen Kontext kann der Code aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen finden Sie unter [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  Der Benutzer muss außerdem über ausreichende Berechtigungen für den Zugriff auf die Datei verfügen.  Weitere Informationen finden Sie unter [ACL Technology Overview](http://msdn.microsoft.com/de-de/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:System.Windows.Forms.OpenFileDialog>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>   
 [SaveFileDialog\-Komponente](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md)   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)