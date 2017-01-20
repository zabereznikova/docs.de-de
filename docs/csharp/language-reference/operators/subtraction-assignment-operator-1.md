---
title: "Operator -= (C#-Referenz) | Microsoft Docs"
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
  - "-=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-=-Operator (Subtraktionszuweisung) [C#]"
  - "Subtraktionszuweisungsoperator (-=) [C#]"
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator -= (C#-Referenz)
Der Subtraktionszuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, in dem der Zuweisungsoperator `-=` verwendet wird, z. B.  
  
```  
x -= y  
```  
  
 der folgenden Syntax:  
  
```  
x = x - y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Die Bedeutung des [Operators \-](../../../csharp/language-reference/operators/subtraction-operator.md) hängt von den Typen von `x` und `y` ab \(Subtraktion für numerische Operanden, Delegatentfernung für Delegatoperanden und so weiter\).  
  
 Der Operator `-=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator \-](../../../csharp/language-reference/operators/subtraction-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
 Der Operator \-\= wird auch in C\# verwendet, um das Abonnement eines Ereignisses zu kündigen.  Weitere Informationen finden Sie unter [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).  
  
## Beispiel  
 [!code-cs[csRefOperators#6](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#6)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)