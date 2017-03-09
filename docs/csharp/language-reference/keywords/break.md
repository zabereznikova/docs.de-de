---
title: "break (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "break"
  - "break_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "break-Schlüsselwort [C#]"
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# break (C#-Referenz)
Mit der `break`\-Anweisung wird die direkt umschließende Schleife oder die [switch](../../../csharp/language-reference/keywords/switch.md)\-Anweisung, in der sie auftritt, beendet.  Die Steuerung wird an die Anweisung übergeben, die auf die beendete Anweisung folgt, falls vorhanden.  
  
## Beispiel  
 In diesem Beispiel enthält die Bedingungsanweisung einen Zähler, der von 1 bis 100 zählen soll. Die `break`\-Anweisung beendet die Schleife jedoch nach 4 Durchläufen.  
  
 [!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/csharp/break_1.cs)]  
  
## Beispiel  
 In diesem Beispiel wird die `break`\-Anweisung verwendet, um aus einer inneren geschachtelten Schleife auszubrechen und die Kontrolle an das Rückgabesteuerelement zurückzugeben.  
  
 [!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/csharp/break_2.cs)]  
  
## Beispiel  
 In diesem Beispiel wird die Verwendung von `break` in einer [switch](../../../csharp/language-reference/keywords/switch.md)\-Anweisung veranschaulicht.  
  
 [!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/csharp/break_3.cs)]  
  
 Bei Eingabe von `4` sähe die Ausgabe wie folgt aus:  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [switch](../../../csharp/language-reference/keywords/switch.md)   
 [Sprunganweisungen](../../../csharp/language-reference/keywords/jump-statements.md)   
 [Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)