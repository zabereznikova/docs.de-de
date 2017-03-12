---
title: "How to: Write Text to Files with a StreamWriter in Visual Basic | Microsoft Docs"
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
  - "writing to files, StreamWriter"
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Write Text to Files with a StreamWriter in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Beispiel wird mit der `My.Computer.FileSystem.OpenTextFileWriter`\-Methode ein <xref:System.IO.StreamWriter>\-Objekt geöffnet, und dieses wird zum Schreiben einer Zeichenfolge in eine Textdatei mithilfe der <xref:System.IO.TextWriter.WriteLine%2A>\-Methode der <xref:System.IO.StreamWriter>\-Klasse verwendet.  
  
## Beispiel  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_0_1.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Die Datei ist bereits vorhanden und schreibgeschützt \(<xref:System.IO.IOException>\).  
  
-   Der Datenträger ist voll \(<xref:System.IO.IOException>\).  
  
-   Der Pfadname ist zu lang \(<xref:System.IO.PathTooLongException>\).  
  
## .NET Framework-Sicherheit  
 Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.  Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`\-Berechtigung für den Ordner.  Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`\-Zugriff, also eine geringere Berechtigung.  Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`\-Berechtigung für eine einzelne Datei erteilt werden \(anstatt `Create`\-Berechtigungen für den gesamten Ordner zu gewähren\).  
  
## Siehe auch  
 <xref:System.IO.StreamWriter>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 [How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)