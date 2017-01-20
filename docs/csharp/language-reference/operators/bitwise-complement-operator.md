---
title: "Operator ~ (C#-Referenz) | Microsoft Docs"
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
  - "~_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~ [C#], Bitweiser Komplementoperator"
  - "~ (Operator) [C#]"
  - "Bitweiser Komplementoperator [C#]"
  - "Tildeoperator (~) für Einerkomplement [C#]"
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator ~ (C#-Referenz)
Der Operator `~` führt eine bitweise Komplementoperation für seine Operanden aus, mit der alle Bits umgekehrt werden.  Bitweise Komplementoperatoren sind für [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) und [ulong](../../../csharp/language-reference/keywords/ulong.md) vordefiniert.  
  
> [!NOTE]
>  Das Symbol `~` wird auch verwendet, um Destruktoren zu deklarieren.  Weitere Informationen finden Sie unter [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `~`  überladen.  Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#25)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Destruktoren](../../../csharp/programming-guide/classes-and-structs/destructors.md)