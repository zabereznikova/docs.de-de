---
title: "do (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "do_CSharpKeyword"
  - "do"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "do-Schlüsselwort [C#]"
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# do (C#-Referenz)
Mit der `do`\-Anweisung wird eine Anweisung oder ein Anweisungsblock wiederholt ausgeführt, bis ein bestimmter Ausdruck den Wert `false` liefert.  Der Text der Schleife muss in Klammern eingeschlossen werden, `{}`, außer er besteht aus einer einzelnen Anweisung.  In diesem Fall sind die Klammern optional.  
  
## Beispiel  
 Im folgenden Beispiel werden die Anweisungen in der `do-while`\-Schleife solange ausgeführt, solange die Variable `x` kleiner als 5 ist.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 Im Gegensatz zur [while](../../../csharp/language-reference/keywords/while.md)\-Anweisung wird eine `do-while`\-Schleife einmal ausgeführt, bevor der bedingte Ausdruck ausgewertet wird.  
  
 Mit der [break](../../../csharp/language-reference/keywords/break.md)\-Anweisung können Sie die Schleife an jedem Punkt im `do-while`\-Block unterbrechen.  Sie können direkt zur `while`\-Ausdrucksauswertungsanweisung wechseln, indem Sie die [continue](../../../csharp/language-reference/keywords/continue.md)\-Anweisung verwenden.  Wenn der `while`\-Ausdruck true ergibt, wird die Ausführung bei der ersten Anweisung in der Schleife fortgesetzt.  Wenn der Ausdruck false ergibt, wird die Ausführung bei der ersten Anweisung nach der `do-while`\-Schleife fortgesetzt.  
  
 Eine `do-while`\-Schleife kann durch die Anweisungen [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) oder [throw](../../../csharp/language-reference/keywords/throw.md) beendet werden.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [do\-while\-Anweisung \(C\+\+\)](/visual-cpp/cpp/do-while-statement-cpp)   
 [Iterationsanweisungen](../../../csharp/language-reference/keywords/iteration-statements.md)