---
title: "Resume without error | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID20"
dev_langs: 
  - "VB"
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Resume without error
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Es wurde eine `Resume`\-Anweisung außerhalb des Fehlerbehandlungscodes gefunden, oder die Codeausführung ist in einen Fehlerhandler gesprungen, obwohl kein Fehler aufgetreten war.  
  
### So beheben Sie diesen Fehler  
  
1.  Verschieben Sie die `Resume`\-Anweisung in einen Fehlerhandler, oder löschen Sie sie.  
  
2.  Da Sprünge in Bezeichnungen nicht prozedurübergreifend erfolgen können, sollten Sie in der Prozedur nach der Bezeichnung suchen, durch die der Fehlerhandler identifiziert wird.  Falls Sie zwei Bezeichnungen finden, die das Ziel einer `GoTo`\-Anweisung darstellen, die jedoch keine `On Error GoTo`\-Anweisung ist, ändern Sie die Zeilenbezeichnung in das beabsichtigte Ziel.  
  
## Siehe auch  
 [Resume Statement](../../../visual-basic/language-reference/statements/resume-statement.md)   
 [On Error Statement](../../../visual-basic/language-reference/statements/on-error-statement.md)