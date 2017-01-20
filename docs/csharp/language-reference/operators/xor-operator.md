---
title: "Operator&#160;^ (C#-Referenz) | Microsoft Docs"
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
  - "^_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^ (Operator) [C#]"
  - "Bitweiser exklusiver OR-Operator [C#]"
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator&#160;^ (C#-Referenz)
Binäre Operatoren `^` sind für Ganzzahltypen und `bool` vordefiniert.  Für Ganzzahltypen berechnet `^` das bitweise XOR seiner Operanden.  Für `bool`\-Operanden berechnet `^` das logische XOR seiner Operanden. Dies bedeutet, dass das Ergebnis genau dann `true` lautet, wenn genau einer von beiden Operanden den Wert `true` aufweist.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `^` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Operationen mit Ganzzahltypen sind bei der Enumeration grundsätzlich zulässig.  
  
## Beispiel  
 [!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#30)]  
  
 Bei der Berechnung von `0xf8 ^ 0x3f` im vorherigen Beispiel wird ein bitweises XOR der folgenden zwei Binärwerte entsprechend den Hexadezimalwerten F8 und 3F ausgeführt:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 Das Ergebnis des XOR ist `1100 0111` bzw. C7 im hexadezimalen Format.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)