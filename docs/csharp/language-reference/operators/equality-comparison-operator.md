---
title: "Operator&#160;== (C#-Referenz) | Microsoft Docs"
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
  - "==_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "== (Operator) [C#]"
  - "Gleichheitsoperator [C#]"
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator&#160;== (C#-Referenz)
Für vordefinierte Werttypen gibt der Gleichheitsoperator \(`==`\) true zurück, wenn die Werte seiner Operanden gleich sind. Andernfalls gibt er `false` zurück.  Für andere Referenztypen als [string](../../../csharp/language-reference/keywords/string.md) gibt `==` dann `true` zurück, wenn seine zwei Operanden auf dasselbe Objekt verweisen.  Beim `string`\-Typ vergleicht `==` die Werte der Zeichenfolgen.  
  
## Hinweise  
 Benutzerdefinierte Werttypen können den Operator `==` überladen \(siehe [operator](../../../csharp/language-reference/keywords/operator.md)\).  Dies ist auch bei benutzerdefinierten Referenztypen möglich, obwohl sich `==` standardmäßig sowohl bei vordefinierten als auch bei benutzerdefinierten Referenztypen wie oben beschrieben verhält.  Wenn `==` überladen wird, muss auch [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) überladen werden.  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#36)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)