---
title: "How to: Move Data Into and Out of a Variable (Visual Basic) | Microsoft Docs"
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
  - "variables [Visual Basic], retrieving values"
  - "variables [Visual Basic], storing data"
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Move Data Into and Out of a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Um einen Wert in einer Variablen zu speichern, fügen Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung ein.  
  
## Einfügen von Daten in eine Variable  
  
#### So speichern Sie einen Wert in einer Variablen  
  
-   Verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung.  
  
     Im folgenden Beispiel wird der Wert der `alpha`\-Variablen festgelegt.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Der Wert, der auf der rechten Seite der Zuweisungsanweisung generiert wird, wird in der Variablen gespeichert.  
  
## Abrufen von Daten aus einer Variablen  
 Sie rufen den Wert einer Variablen ab, indem Sie den Variablennamen in einen Ausdruck einfügen.  
  
#### So rufen Sie einen Wert aus einer Variablen ab  
  
-   Verwenden Sie den Variablennamen in einem Ausdruck.  Sie können eine Variable überall verwenden, wo auch Konstanten oder Literale zulässig sind, außer in einem Ausdruck, der den Wert einer Konstante definiert.  
  
     \- oder \-  
  
-   Fügen Sie den Variablennamen hinter dem Gleichheitszeichen \(`=`\) in einer Zuweisungsanweisung ein.  
  
     Im folgenden Beispiel wird der Wert der `startValue`\-Variablen gelesen, anschließend wird der Wert der `counter`\-Variablen in einem Ausdruck verwendet.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Der Wert der Variablen hat im Ausdruck dieselbe Funktion wie eine Konstante und wird anschließend in der Variablen oder Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.  
  
## Siehe auch  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)