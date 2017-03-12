---
title: "Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30220"
  - "bc30220"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30220"
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Delegate class &#39;&lt;classname&gt;&#39; has no Invoke method, so an expression of this type cannot be the target of a method call
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein Aufruf von `Invoke` durch einen Delegaten ist fehlgeschlagen, weil `Invoke` nicht in der Delegatklasse implementiert ist.  
  
 **Fehler\-ID:** BC30220  
  
### So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass eine Instanz der Delegatklasse mit einer `Dim`\-Anweisung erstellt wurde und dass eine Prozedur der Delegatinstanz mit dem Operator `AddressOf` zugewiesen wurde.  
  
2.  Suchen Sie den Code, der die Delegatklasse implementiert, und vergewissern Sie sich, dass er die `Invoke`\-Prozedur implementiert.  
  
## Siehe auch  
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)