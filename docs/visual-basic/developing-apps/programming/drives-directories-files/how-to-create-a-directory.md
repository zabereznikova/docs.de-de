---
title: "How to: Create a Directory in Visual Basic | Microsoft Docs"
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
  - "directories [Visual Basic], creating"
  - "folders [Visual Basic], creating"
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Create a Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Verwenden Sie die `CreateDirectory`\-Methode des `My.Computer.FileSystem`\-Objekts zum Erstellen von Verzeichnissen.  
  
 Wenn das Verzeichnis bereits vorhanden ist, wird keine Ausnahme ausgelöst.  
  
### So erstellen Sie ein Verzeichnis  
  
-   Verwenden Sie die `CreateDirectory`\-Methode, und geben Sie den vollständigen Pfad für das zu erstellende Verzeichnis an.  In diesem Beispiel wird das Verzeichnis `NewDirectory` unter `C:\Documents and Settings\All Users\Documents` erstellt.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## Robuste Programmierung  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Verzeichnisname ist falsch formatiert.  Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen \(<xref:System.ArgumentException>\).  
  
-   Das übergeordnete Verzeichnis des zu erstellenden Verzeichnisses ist schreibgeschützt \(<xref:System.IO.IOException>\).  
  
-   Der Verzeichnisname ist `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Der Verzeichnisname ist zu lang \(<xref:System.IO.PathTooLongException>\).  
  
-   Der Verzeichnisname besteht nur aus einem Doppelpunkt ":" \(<xref:System.NotSupportedException>\).  
  
-   Der Benutzer ist nicht zum Erstellen des Verzeichnisses berechtigt \(<xref:System.UnauthorizedAccessException>\).  
  
-   Dem Benutzer fehlen Berechtigungen in einer teilweise vertrauenswürdigen Situation \(<xref:System.Security.SecurityException>\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)