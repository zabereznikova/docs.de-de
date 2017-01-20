---
title: "partial (Methode) (C#-Referenz) | Microsoft Docs"
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
  - "partialmethod_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Partielle Methoden [C#]"
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# partial (Methode) (C#-Referenz)
Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert.  Mit partiellen Methoden können Klassen\-Designer Methoden\-Hooks bereitstellen, die Ereignis\-Handlern ähneln und die Entwickler ggf. implementieren können.  Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung.  Die folgenden Bedingungen gelten für partielle Methoden:  
  
-   Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.  
  
-   Die Methode muss "void" zurückgeben.  
  
-   Es sind keine Zugriffsmodifizierer zulässig.  Partielle Methoden sind implizit privat.  
  
 Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:  
  
 [!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [partial \(Typ\)](../../../csharp/language-reference/keywords/partial-type.md)