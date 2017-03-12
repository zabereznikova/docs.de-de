---
title: "File not found (Visual Basic Run-Time Error) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID53"
dev_langs: 
  - "VB"
ms.assetid: 57addb16-6f9a-444d-8af8-dda52431daca
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# File not found (Visual Basic Run-Time Error)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Die Datei wurde nicht an der angegebenen Stelle gefunden.  Dieser Fehler hat die folgenden möglichen Ursachen:  
  
-   Eine Anweisung verweist auf eine Datei, die nicht vorhanden ist.  
  
-   Es wurde versucht, eine Prozedur in einer Dynamic Link Library \(DLL\) aufzurufen, aber die in der `Lib`\-Klausel der `Declare`\-Anweisung angegebene Bibliothek kann nicht gefunden werden.  
  
-   Sie haben versucht, ein nicht vorhandenes Projekt zu öffnen oder eine nicht vorhandene Textdatei zu laden.  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Dateinamens und der Pfadangabe.  
  
## Siehe auch  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)