---
title: "Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36635"
  - "vbc36635"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36635"
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Sie können keinen Lambda\-Ausdruck für den Testausdruck in einer `Select Case`\-Anweisung verwenden.  Definitionen von Lambda\-Ausdrücken geben Funktionen zurück, und der Testausdruck einer `Select Case`\-Anweisung muss einem elementaren Datentyp entsprechen.  
  
 Im folgenden Code wird dieser Fehler verursacht:  
  
```vb#  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Fehler\-ID:** BC36635  
  
### So beheben Sie diesen Fehler  
  
-   Überprüfen Sie den Code, und ermitteln Sie, ob eine andere bedingte Konstruktion, z. B. eine `If...Then...Else`\-Anweisung, in diesem Fall funktioniert.  
  
-   Möglicherweise hatten Sie beabsichtigt, die Funktionen aufzurufen, wie im folgenden Code dargestellt:  
  
    ```vb#  
    Dim num? As Integer  
    Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
        ' List of the cases  
    End Select  
    ```  
  
## Siehe auch  
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [If...Then...Else Statement](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md)