---
title: "Object variable or With block variable not set | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID91"
dev_langs: 
  - "VB"
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Object variable or With block variable not set
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Es ist ein Verweis auf eine ungültige Variable vorhanden.  Wenn Sie eine Objektvariable erstellen möchten, müssen Sie die Objektvariable deklarieren und anschließend mithilfe der `Set`\-Anweisung einen gültigen Verweis auf die Objektvariable zuweisen.  Außerdem muss ein `With...End With`\-Block initialisiert werden, indem der Einstiegspunkt der `With`\-Anweisung ausgeführt wird.  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Objektvariable auf ein gültiges Objekt verweist, und geben Sie \(erneut\) einen Verweis für das Objekt an.  
  
2.  Stellen Sie sicher, dass Sie keine Objektvariable mit der Einstellung `Nothing` verwendet haben.  
  
3.  Stellen Sie außerdem sicher, dass die Objektbibliothek, in der das Objekt beschrieben wird, im Dialogfeld `Add References` ausgewählt wurde.  
  
4.  Außerdem muss der `With`\-Block initialisiert werden, indem der Einstiegspunkt für die `With`\-Anweisung ausgeführt wird.  
  
## Siehe auch  
 [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)