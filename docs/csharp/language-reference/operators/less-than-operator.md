---
title: "Operator&#160;&lt; (C#-Referenz) | Microsoft Docs"
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
  - "<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "< (Operator) [C#]"
  - "Kleiner als-Operator (<) [C#]"
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator&#160;&lt; (C#-Referenz)
Alle numerischen Typen und Enumerationstypen definieren einen relationalen Operator "kleiner als" \(`<`\), der `true` zurückgibt, wenn der erste Operand kleiner als der zweite ist. Andernfalls wird `false` zurückgegeben.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `<` überladen \(siehe [operator](../../../csharp/language-reference/keywords/operator.md)\).  Wenn `<` überladen wird, muss auch [\>](../../../csharp/language-reference/operators/greater-than-operator.md) überladen werden.  Beim Überladen eines binären Operators wird implizit auch der zugehörige Zuweisungsoperator überladen, falls vorhanden.  
  
## Beispiel  
 [!code-cs[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#24)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)