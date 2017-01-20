---
title: "Troubleshooting: Reading from and Writing to Text Files (Visual Basic) | Microsoft Docs"
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
  - "troubleshooting file I/O"
  - "writing text to files, troubleshooting"
  - "troubleshooting Visual Basic, text files"
  - "I/O [Visual Basic], troubleshooting text files"
  - "writing to files, troubleshooting"
  - "reading text files, troubleshooting"
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Troubleshooting: Reading from and Writing to Text Files (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In diesem Thema werden allgemeine Probleme erläutert, die im Zusammenhang mit der Arbeit mit Textdateien auftreten können, und entsprechende Lösungsvorschläge angegeben.  
  
## Allgemeine Probleme  
 Zu den häufigsten Problemen beim Arbeiten mit Textdateien zählen Sicherheitsausnahmen, falsche Dateicodierungen und ungültige Pfade.  
  
### Sicherheitsausnahmen  
 Beim Auftreten eines Sicherheitsfehlers wird eine <xref:System.Security.SecurityException> ausgelöst.  Dies ist oft auf ungenügende Berechtigungen eines Benutzers zurückzuführen und kann durch das Hinzufügen von Berechtigungen oder das Arbeiten mit Dateien in isoliertem Speicher behoben werden.  Weitere Informationen finden Sie unter [Problembehandlung bei Ausnahmen: System.Security.SecurityException](../Topic/Troubleshooting%20Exceptions:%20System.Security.SecurityException.md).  
  
### Dateicodierungen  
 Dateicodierungen, auch als Zeichencodierungen bezeichnet, geben an, wie Zeichen bei der Textverarbeitung dargestellt werden.  Unerwartete Zeichen in einer Textdatei sind möglicherweise auf eine falsche Codierung zurückzuführen.  Codierungen können sich in Bezug auf die Unterstützung einzelner sprachspezifischer Zeichen unterscheiden. Im Allgemeinen empfiehlt sich jedoch die Verwendung von Unicode.  Weitere Informationen finden Sie unter [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) und unter <xref:System.Text.Encoding>.  
  
### Falsche Pfade  
 Beim Analysieren von Dateipfaden, insbesondere relativen Pfaden, werden oft falsche Daten bereitgestellt.  Meist kann dieses Problem durch Bereitstellung des korrekten Pfades behoben werden.  Weitere Informationen finden Sie unter [Gewusst wie: Analysieren von Dateipfaden](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)