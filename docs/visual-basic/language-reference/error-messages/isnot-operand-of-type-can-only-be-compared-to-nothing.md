---
title: "&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc32128"
  - "vbc32128"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32128"
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# &#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Variable, die als auf NULL festlegbar deklariert wurde, wurde mithilfe des Operators `IsNot` mit einem anderen Ausdruck als `Nothing` verglichen.  
  
 **Fehler\-ID:** BC32128  
  
### So beheben Sie diesen Fehler  
  
1.  Um einen Typ, der NULL\-Werte zulässt, mithilfe des Operators `IsNot` mit einem anderen Ausdruck als `Nothing` zu vergleichen, rufen Sie die `GetType`\-Methode für den Typ auf, der NULL\-Werte zulässt, und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel dargestellt.  
  
    ```vb#  
    Dim number? As Integer = 5  
  
    If number IsNot Nothing Then  
      If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
      End If  
    End If  
    ```  
  
## Siehe auch  
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)