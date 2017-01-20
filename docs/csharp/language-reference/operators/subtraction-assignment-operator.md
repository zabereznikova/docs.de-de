---
title: "Operator /= (C#-Referenz) | Microsoft Docs"
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
  - "/=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/= (Divisionszuweisungsoperator) [C#]"
  - "Divisionszuweisungsoperator (/=) [C#]"
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator /= (C#-Referenz)
Der Divisionszuweisungsoperator.  
  
## Hinweise  
 Ein Ausdruck, in dem der Zuweisungsoperator `/=` verwendet wird, z. B.  
  
```  
x /= y  
```  
  
 der folgenden Syntax:  
  
```  
x = x / y  
```  
  
 mit der Ausnahme, dass `x` nur einmal ausgewertet wird.  Der [Operator \/](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen so definiert, dass er eine Division ausführt.  
  
 Der Operator `/=` kann nicht direkt überladen werden. Benutzerdefinierte Typen können jedoch den [Operator \/](../../../csharp/language-reference/operators/division-operator.md) überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Bei allen Verbundzuweisungsoperatoren wird durch das Überladen des binären Operators die entsprechende Verbundzuweisung implizit überladen.  
  
## Beispiel  
 [!code-cs[csRefOperators#5](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#5)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)