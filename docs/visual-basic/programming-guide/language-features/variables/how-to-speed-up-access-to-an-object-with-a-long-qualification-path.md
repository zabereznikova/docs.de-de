---
title: "How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], accessing"
  - "variables [Visual Basic], object"
  - "With statement"
  - "With block"
  - "object variables, accessing"
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie häufig auf ein Objekt zugreifen, dessen vollständiger Name \(Qualifizierungspfad\) verschiedene Methoden und Eigenschaften umfasst, können Sie die Ausführungsgeschwindigkeit des Codes beschleunigen, indem Sie den Qualifizierungspfad nicht erneut angeben.  
  
 Eine Wiederholung des Qualifizierungspfads lässt sich auf zwei Arten vermeiden.  Sie können das Objekt einer Variablen zuweisen oder es in einem `With`...`End With`\-Block verwenden.  
  
### So beschleunigen Sie den Zugriff auf Objekt mit einem langen Qualifizierungspfad, indem Sie es einer Variablen zuweisen  
  
1.  Deklarieren Sie eine Variable mit dem Typ des Objekts, auf das Sie häufig zugreifen.  Geben Sie den Qualifizierungspfad im Initialisierungsteil der Deklaration an.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Greifen Sie unter Verwendung der Variablen auf die Member des Objekts zu.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### So beschleunigen Sie den Zugriff auf ein Objekt mit langem Qualifizierungspfad mithilfe eines With...End With\-Blocks  
  
1.  Geben Sie den Qualifizierungspfad in einer `With`\-Anweisung an.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Rufen Sie im `With`\-Block vor der `End With`\-Anweisung die Member des Objekts auf.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## Siehe auch  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)