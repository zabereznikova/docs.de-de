---
title: "How to: Refer to the Current Instance of an Object (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], object"
  - "objects [Visual Basic], referring to current instance"
  - "instances, referring to current"
  - "current instance"
  - "object variables"
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Refer to the Current Instance of an Object (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die *aktuelle Instanz* eines Objekts ist die Instanz, in der der Code gegenwärtig ausgeführt wird.  
  
 Mit dem `Me` \-Schlüsselwort verweisen Sie auf die aktuelle Instanz.  
  
### So verweisen Sie auf die aktuelle Instanz  
  
-   Verwenden Sie das `Me`\-Schlüsselwort an der Stelle, an der Sie normalerweise den Namen einer Objektvariablen verwenden würden.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Obwohl sich `Me` wie eine Objektvariable verhält, können Sie das Schlüsselwort nicht deklarieren oder ihm ein Element zuweisen.  `Me` verweist immer auf die aktuelle Instanz.  
  
## Siehe auch  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)