---
title: "Other Control Structures (Visual Basic) | Microsoft Docs"
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
  - "statements [Visual Basic], control flow"
  - "control structures"
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Other Control Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt Steuerungsstrukturen bereit, mit denen Sie eine Ressource freigeben oder die Anzahl der Wiederholungen eines Objektverweises verringern können.  
  
## Using...End Using\-Konstruktion  
 Die `Using...End Using`\-Konstruktion erstellt einen Anweisungsblock, in dem Sie eine Ressource, wie z. B. eine SQL\-Verbindung, nutzen können.  Sie können die Ressource auch mit der `Using`\-Anweisung abrufen.  Wenn Sie den `Using`\-Block verlassen, gibt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die Ressource automatisch frei, sodass sie von anderem Code verwendet werden kann.  Die Ressource muss lokal sein und freigegeben werden können.  Weitere Informationen finden Sie unter [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## With...End With\-Konstruktion  
 Mit der `With...End With`\-Konstruktion können Sie einen Objektverweis angeben und dann eine Reihe von Anweisungen ausführen, die auf seine Member zugreifen.  Dies kann zu einer Vereinfachung des Codes und zu einer Leistungssteigerung führen, da [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] den Verweis nicht für jede Anweisung, die darauf zugreift, erneut erstellen muss.  Weitere Informationen finden Sie unter [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).  
  
## Siehe auch  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)   
 [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)