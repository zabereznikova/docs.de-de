---
title: "Bad file name or number | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID52"
dev_langs: 
  - "VB"
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Bad file name or number
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Beim Versuch, auf die angegebene Datei zuzugreifen, ist ein Fehler aufgetreten.  Dieser Fehler kann folgende Ursachen haben:  
  
-   Eine Anweisung verweist auf eine Datei mit einem Dateinamen oder einer Nummer, der bzw. die nicht in der `FileOpen`\-Anweisung angegeben ist oder der bzw. die in einer `FileOpen`\-Anweisung angegeben ist, aber später geschlossen wurde.  
  
-   Eine Anweisung verweist auf eine Datei mit einer Nummer, die nicht im Bereich der Dateinummern liegt.  
  
-   Eine Anweisung verweist auf einen Dateinamen oder eine Nummer, der bzw. die ungültig ist.  
  
### So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass der Dateiname in einer `FileOpen`\-Anweisung angegeben ist.  Wenn Sie die `FileClose`\-Anweisung ohne Argumente aufgerufen haben, haben Sie möglicherweise versehentlich alle geöffneten Dateien geschlossen.  
  
2.  Wenn der Code Dateinummern algorithmisch generiert, vergewissern Sie sich, dass die Nummern gültig sind.  
  
3.  Überprüfen Sie die Dateinamen, um sicherzustellen, dass sie den Konventionen des Betriebssystems entsprechen.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)