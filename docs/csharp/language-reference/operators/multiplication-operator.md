---
title: "Operator&#160;* (C#-Referenz) | Microsoft Docs"
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
  - "*_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "* (Operator) [C#]"
  - "Multiplikationsoperator (*) [C#]"
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator&#160;* (C#-Referenz)
Der Multiplikationsoperator \(`*`\) berechnet das Produkt seiner Operanden.  Wird auch verwendet als Dereferenzierungsoperator, der einem Zeiger das Lesen und Schreiben ermöglicht.  
  
## Hinweise  
 Für alle numerischen Typen sind Multiplikationsoperatoren vordefiniert.  
  
 Mithilfe des Operators `*` können auch Zeigertypen deklariert und Zeiger dereferenziert werden.  Dieser Operator kann nur in nicht sicheren Kontexten verwendet werden, die durch das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)\-Schlüsselwort gekennzeichnet sind und die [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)\-Compileroption erfordern.  Der Dereferenzierungsoperator ist auch als Operator "Indirection" bekannt.  
  
 Benutzerdefinierte Typen können den binären Operator `*` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Beim Überladen eines binären Operators wird implizit auch der zugehörige Zuweisungsoperator überladen, falls vorhanden.  
  
## Beispiel  
 [!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#50)]  
  
## Beispiel  
 [!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#51)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)