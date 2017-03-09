---
title: "&#39;AddressOf&#39; operand must be the name of a method (without parentheses) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30577"
  - "bc30577"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30577"
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &#39;AddressOf&#39; operand must be the name of a method (without parentheses)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Operator `AddressOf` erstellt eine Instanz eines Prozedurdelegaten, die auf eine bestimmte Prozedur verweist.  Die Syntax lautet wie folgt:  
  
 `AddressOf` `procedurename`  
  
 Das Argument nach `AddressOf` steht in runden Klammern. An dieser Stelle sind keine Klammern erforderlich.  
  
 **Fehler\-ID:** BC30577  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die runden Klammern, die das Argument hinter `AddressOf` umschließen.  
  
2.  Stellen Sie sicher, dass das Argument ein Methodenname ist.  
  
## Siehe auch  
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)