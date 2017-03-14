---
title: "Sub or Function not defined (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID35"
dev_langs: 
  - "VB"
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Sub or Function not defined (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Für einen Aufruf muss `Sub` oder `Function` zunächst definiert werden.  Dieser Fehler kann folgende Ursachen haben:  
  
-   Der Prozedurname wurde falsch geschrieben.  
  
-   Versuch, eine Prozedur aus einem anderen Projekt aufzurufen, ohne einen Verweis auf das Projekt explizit in das Dialogfeld **Verweise** einzufügen.  
  
-   Angabe einer Prozedur, die für die aufrufende Prozedur nicht sichtbar ist.  
  
-   Deklarieren einer Windows\-Dynamic Link Library\(DLL\)\-Routine oder einer Macintosh\-Coderessourcen\-Routine, die sich nicht in der angegebenen Bibliothek oder Coderessource befindet.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der Prozedurname richtig geschrieben ist.  
  
2.  Suchen Sie den Namen des Projekts mit der Prozedur, die im Dialogfeld **Verweise** aufgerufen werden soll.  Wenn der Name nicht angezeigt wird, klicken Sie auf die Schaltfläche **Durchsuchen**, um ihn zu suchen.  Klicken Sie zuerst auf das Kontrollkästchen links neben dem Projektnamen und dann auf **OK**.  
  
3.  Überprüfen Sie den Namen der Routine.  
  
## Siehe auch  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)