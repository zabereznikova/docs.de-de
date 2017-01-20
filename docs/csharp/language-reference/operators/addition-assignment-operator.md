---
title: "Operator&#160;+= (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "+=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+= (Operator) [C#]"
  - "Additionszuweisungsoperator (+=) [C#]"
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator&#160;+= (C#-Referenz)
Der Additionszuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, in dem der Zuweisungsoperator `+=` verwendet wird, z. B.  
  
```  
x += y  
```  
  
 der folgenden Syntax:  
  
```  
x = x + y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Die Bedeutung des [Operators \+](../../../csharp/language-reference/operators/addition-operator.md) hängt von den Typen von `x` und `y` ab \(Addition für numerische Operanden, Verkettung für Zeichenfolgenoperanden und so weiter\).  
  
 Der Operator `+=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator \+](../../../csharp/language-reference/operators/addition-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
 Der Operator `+=` wird auch verwendet, um eine Methode anzugeben, die als Reaktion auf ein Ereignis aufgerufen wird. Derartige Methoden werden als Ereignishandler bezeichnet.  Die Verwendung des `+=`\-Operators in diesem Kontext wird als *Abonnieren eines Ereignisses* bezeichnet.  Weitere Informationen finden Sie unter [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  und [Delegaten](../../../csharp/programming-guide/delegates/index.md).  
  
## Beispiel  
 [!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#35)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)