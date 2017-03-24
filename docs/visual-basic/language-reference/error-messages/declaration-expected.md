---
title: "Declaration expected | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30188"
  - "bc30188"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30188"
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Declaration expected
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine nicht deklarierte Anweisung, wie eine Zuweisung oder eine Schleifenanweisung, tritt außerhalb einer Prozedur auf.  Außerhalb von Prozeduren sind nur Deklarationen zulässig.  
  
 Alternativ wird ein Programmierelement ohne Deklarationsschlüsselwort, wie `Dim` oder `Const`, deklariert.  
  
 **Fehler\-ID:** BC30188  
  
### So beheben Sie diesen Fehler  
  
-   Verschieben Sie die nicht deklarierte Anweisung in den Rumpf einer Prozedur.  
  
-   Beginnen Sie die Deklaration mit einem entsprechenden Deklarationsschlüsselwort.  
  
-   Vergewissern Sie sich, dass das Deklarationsschlüsselwort korrekt geschrieben wurde.  
  
## Siehe auch  
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)