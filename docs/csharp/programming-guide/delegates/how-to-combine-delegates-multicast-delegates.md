---
title: "Gewusst wie: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Delegaten [C#], Kombinieren"
  - "Multicastdelegaten [C#]"
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Gewusst wie: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)
In diesem Beispiel wird das Erstellen von Multicastdelegaten veranschaulicht.  Eine nützliche Eigenschaft von [delegate](../../../csharp/language-reference/keywords/delegate.md)\-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können.  Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten.  Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf.  Es können nur Delegaten desselben Typs kombiniert werden.  
  
 Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#11)]  
  
## Siehe auch  
 <xref:System.MulticastDelegate>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)