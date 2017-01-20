---
title: "while (C#-Referenz) | Microsoft Docs"
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
  - "while_CSharpKeyword"
  - "while"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "while-Schlüsselwort [C#]"
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# while (C#-Referenz)
Mit der `while`\-Anweisung wird eine Anweisung oder ein Anweisungsblock ausgeführt, bis ein bestimmter Ausdruck den Wert `false` liefert.  
  
## Beispiel  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## Beispiel  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## Beispiel  
 Da der Test des `while`\-Ausdrucks jedes Mal stattfindet, bevor die Schleife durchlaufen wird, wird eine `while`\-Anweisung keinmal, einmal oder häufiger ausgeführt.  Hierbei besteht ein Unterschied zur [do](../../../csharp/language-reference/keywords/do.md)\-Schleife, die mindestens einmal ausgeführt wird.  
  
 Eine `while`\-Schleife kann beendet werden, wenn eine der Anweisungen [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) der Schleife die Steuerung entzieht.  Verwenden Sie die [continue](../../../csharp/language-reference/keywords/continue.md)\-Anweisung, um die Steuerung an die nächste Iteration zu übergeben, ohne die Schleife zu verlassen.  Beachten Sie, wie sich die Ausgabe der drei oben gezeigten Beispiele abhängig davon unterscheidet, an welcher Stelle `int n` inkrementiert wird.  Im Beispiel unten wird keine Ausgabe generiert.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [while\-Anweisung \(C\+\+\)](/visual-cpp/cpp/while-statement-cpp)   
 [Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)