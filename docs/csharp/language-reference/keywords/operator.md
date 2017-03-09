---
title: "operator (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "operator_CSharpKeyword"
  - "operator"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "operator-Schlüsselwort [C#]"
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# operator (C#-Referenz)
Verwenden Sie das `operator`\-Schlüsselwort, um einen integrierten Operator zu überladen oder eine benutzerdefinierte Konvertierung in eine Klassen\- oder Strukturdeklaration bereitzustellen.  
  
## Beispiel  
 Im Folgenden handelt es sich um eine stark vereinfachte Klasse für Dezimalzahlen.  Der Operator \+ und der Operator \* werden überladen, um Addition und Multiplikation von Brüchen durchzuführen. Weiterhin wird ein Konvertierungsoperator bereitgestellt, der Brüche in Werte vom Typ double konvertiert.  
  
 [!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/csharp/operator_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Implizite](../../../csharp/language-reference/keywords/implicit.md)   
 [Explizit](../../../csharp/language-reference/keywords/explicit.md)   
 [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)