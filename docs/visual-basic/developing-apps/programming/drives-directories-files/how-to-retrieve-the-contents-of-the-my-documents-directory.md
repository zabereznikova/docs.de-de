---
title: "How to: Retrieve the Contents of the My Documents Directory in Visual Basic | Microsoft Docs"
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
  - "My Documents directory"
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Retrieve the Contents of the My Documents Directory in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Mit dem <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>\-Objekt können Inhalte aus vielen der **Alle Benutzer**\-Verzeichnisse gelesen werden, z. B. aus **Eigene Dateien** oder **Desktop**.  
  
### So lesen Sie Inhalte aus dem Ordner Eigene Dateien  
  
-   Mit der `ReadAllText`\-Methode können Sie den Text aus jeder Datei in einem bestimmten Verzeichnis lesen.  Im folgenden Code wird ein Verzeichnis und eine Datei angegeben und deren Inhalt mithilfe von `ReadAllText` in eine Zeichenfolge mit dem Namen `patients` eingelesen.  
  
     [!code-vb[VbVbcnMyFileSystem#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-retrieve-the-contents-of-the-my-documents-directory_1.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>