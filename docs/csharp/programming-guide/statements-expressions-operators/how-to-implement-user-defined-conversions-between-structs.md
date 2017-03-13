---
title: "Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Benutzerdefinierte Konvertierungen [C#]"
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen (C#-Programmierhandbuch)
In diesem Beispiel werden die beiden Strukturen `RomanNumeral` und `BinaryNumeral` definiert, und es werden die Konvertierungen zwischen diesen Strukturen veranschaulicht.  
  
## Beispiel  
 [!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## Robuste Programmierung  
  
-   Im vorherigen Beispiel wird durch die Anweisung  
  
     [!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     eine Konvertierung von `RomanNumeral` in `BinaryNumeral` durchgeführt.  Da es keine direkte Konvertierung von `RomanNumeral` in `BinaryNumeral` gibt, wird `RomanNumeral` mithilfe einer Typumwandlung in einen `int`\-Typ konvertiert und mit einer weiteren Typumwandlung von `int` in `BinaryNumeral` konvertiert.  
  
-   Auch durch die Anweisung  
  
     [!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     wird eine Konvertierung von `BinaryNumeral` in `RomanNumeral` durchgeführt.  Da durch `RomanNumeral` eine implizite Konvertierung von `BinaryNumeral` definiert wird, ist keine Typumwandlung erforderlich.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)