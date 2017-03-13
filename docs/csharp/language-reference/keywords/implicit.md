---
title: "implicit (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "implicit"
  - "implicit_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "implicit-Schlüsselwort [C#]"
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# implicit (C#-Referenz)
Das `implicit`\-Schlüsselwort wird verwendet, um einen impliziten benutzerdefinierten Typkonvertierungsoperator zu deklarieren.  Wenn durch die Konvertierung kein Datenverlust zu befürchten ist, können Sie es verwenden, um implizite Konvertierungen zwischen einem benutzerdefinierten Typ und einem anderen Typ zu ermöglichen.  
  
## Beispiel  
 [!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 Durch implizite Konvertierungen kann die Lesbarkeit des Quellcodes verbessert werden, da nicht erforderliche Typumwandlungen entfernt werden.  Da implizite Konvertierungen jedoch keine explizite Umwandlung von einem Typ in einen anderen erfordern, ist Vorsicht angebracht, um unerwartete Ergebnisse zu vermeiden.  In der Regel sollten durch implizite Konvertierungsoperatoren keine Ausnahmen ausgelöst werden oder Informationen verloren gehen, sodass sie sicher verwendet werden können, ohne dass sich der Programmierer dessen bewusst ist.  Ein Konvertierungsoperator, der diese Kriterien nicht erfüllen kann, sollte als `explicit` markiert werden.  Weitere Informationen hierzu finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Explizit](../../../csharp/language-reference/keywords/explicit.md)   
 [Operator](../../../csharp/language-reference/keywords/operator.md)   
 [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)