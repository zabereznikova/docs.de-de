---
title: "goto (C#-Referenz) | Microsoft Docs"
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
  - "goto_CSharpKeyword"
  - "goto"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "goto-Schlüsselwort [C#]"
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# goto (C#-Referenz)
Mit der `goto`\-Anweisung wird die Programmsteuerung direkt an eine Anweisung mit Marke übergeben.  
  
 `goto` wird häufig verwendet, um die Steuerung an eine bestimmte switch\-case\-Marke oder die default\-Marke in einer `switch`\-Anweisung zu übergeben.  
  
 Die `goto`\-Anweisung ist auch nützlich, um tief geschachtelte Schleifen zu verlassen.  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung von `goto` in einer [switch](../../../csharp/language-reference/keywords/switch.md)\-Anweisung veranschaulicht.  
  
 [!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## Beispiel  
 Im folgenden Beispiel wird demonstriert, wie `goto` verwendet werden kann, um geschachtelte Schleifen zu verlassen.  
  
 [!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [goto\-Anweisung](/visual-cpp/cpp/goto-statement-cpp)   
 [Sprunganweisungen](../../../csharp/language-reference/keywords/jump-statements.md)