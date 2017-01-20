---
title: "Operator |= (C#-Referenz) | Microsoft Docs"
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
  - "|=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|=-Operator (OR-Zuweisung [C#]"
  - "OR-Zuweisungsoperator (|=) [C#]"
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator |= (C#-Referenz)
Der OR\-Zuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, der den Zuweisungsoperator `|=` verwendet, z. B.  
  
```  
x |= y  
```  
  
 der folgenden Syntax:  
  
```  
x = x | y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Der [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) führt eine bitweise logische OR\-Operation für ganzzahlige Operanden aus sowie logische OR\-Operationen für bool\-Operanden.  
  
 Der Operator `|=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator &#124;](../../../csharp/language-reference/operators/or-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  
  
## Beispiel  
 [!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#10)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)