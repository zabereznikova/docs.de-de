---
title: "How to: Create a Variable that Does Not Change in Value (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], read-only"
  - "variables [Visual Basic], constant value"
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Create a Variable that Does Not Change in Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Variablen mit unveränderlichem Wert scheinen auf den ersten Blick widersinnig zu sein.  Es gibt jedoch Situationen, in denen eine Konstante nicht zulässig ist, während eine Variable mit einem festen Wert hilfreich ist.  In einem solchen Fall können Sie eine Membervariable mit dem [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)\-Schlüsselwort definieren.  
  
 In folgenden Fällen können Sie die [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) nicht zum Deklarieren und Zuweisen eines konstanten Werts verwenden:  
  
-   Die `Const`\-Anweisung übernimmt den gewünschten Datentyp nicht.  
  
-   Der Wert ist zur Kompilierungszeit nicht bekannt.  
  
-   Sie können den konstanten Wert zur Kompilierungszeit nicht berechnen.  
  
### So erstellen Sie eine Variable mit unveränderlichem Wert  
  
1.  Deklarieren Sie auf Modulebene eine Membervariable mit der [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), und fügen Sie das [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)\-Schlüsselwort ein.  
  
    ```  
  
    Dim ReadOnly timeStarted  
    ```  
  
     Sie können `ReadOnly` nur bei einer Membervariablen angeben.  Dies bedeutet, dass Sie die Variable außerhalb jeder Prozedur auf Modulebene definieren müssen.  
  
2.  Wenn Sie den Wert zur Kompilierungszeit in einer einzigen Anweisung berechnen können, verwenden Sie in der `Dim`\-Anweisung eine Initialisierungsklausel.  Fügen Sie nach der [As](../../../../visual-basic/language-reference/statements/as-clause.md)\-Klausel ein Gleichheitszeichen \(`=`\) und danach einen Ausdruck ein.  Stellen Sie sicher, dass der Compiler diesen Ausdruck als einen konstanten Wert auswerten kann.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     Einer `ReadOnly`\-Variablen können Sie einen Wert nur einmal zuweisen.  Anschließend kann dieser Wert durch keinen Code mehr geändert werden.  
  
     Wenn der Wert zur Kompilierungszeit nicht bekannt ist oder Sie ihn nicht in einer einzelnen Anweisung berechnen können, haben Sie zur Laufzeit immer noch die Möglichkeit, ihn in einem Konstruktor zuzuweisen.  Dazu müssen Sie die `ReadOnly`\-Variable auf Klassen\- oder Strukturebene deklarieren.  Berechnen Sie im Konstruktor für die betreffende Klasse oder Struktur den unveränderlichen Wert der Variablen, und weisen Sie ihn der Variablen zu, bevor Sie den Konstruktor verlassen.  
  
## Siehe auch  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)   
 [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)