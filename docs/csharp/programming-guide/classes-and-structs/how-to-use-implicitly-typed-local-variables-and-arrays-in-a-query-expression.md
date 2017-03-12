---
title: "Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Implizit typisierte lokale Variablen [C#], Verwendung"
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck (C#-Programmierhandbuch)
Sie können immer implizit typisierte lokale Variablen verwenden, wenn der Compiler den Typ einer lokalen Variablen bestimmen soll.  Sie müssen implizit typisierte lokale Variablen verwenden, um anonyme Typen zu speichern, die häufig in Abfrageausdrücken verwendet werden.  Die folgenden Beispiele veranschaulichen die optionale und die erforderliche Verwendung von implizit typisierten lokalen Variablen in Abfragen.  
  
 Implizit typisierte lokale Variablen werden mit dem [var](../../../csharp/language-reference/keywords/var.md)\-Kontextschlüsselwort deklariert.  Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt ein typisches Szenario, in dem das `var`\-Schlüsselwort erforderlich ist: Ein Abfrageausdruck, der eine Sequenz anonymer Typen erzeugt.  In diesem Szenario müssen die Abfragevariable und die Iterationsvariable in der `foreach`\-Anweisung mithilfe von `var` implizit typisiert werden, da Sie keinen Zugriff auf einen Typnamen für den anonymen Typ haben.  Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
 [!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#32)]  
  
## Beispiel  
 Im folgenden Beispiel wird das `var`\-Schlüsselwort in einer ähnlichen Situation verwendet, in der jedoch die Verwendung von `var` optional ist.  Da `student.LastName` eine Zeichenfolge ist, gibt die Ausführung der Abfrage eine Sequenz von Zeichenfolgen zurück.  Daher kann der Typ von `queryID` als `System.Collections.Generic.IEnumerable<string>` statt als `var` deklariert werden.  Das Schlüsselwort `var` wird aus praktischen Gründen verwendet.  Im Beispiel wird die Iterationsvariable in der `foreach`\-Anweisung explizit als string typisiert, sie kann jedoch stattdessen auch mit `var` deklariert werden.  Da der Typ der Iterationsvariablen kein anonymer Typ ist, ist die Verwendung von `var` optional und nicht erforderlich.  Denken Sie daran, dass `var` kein eigener Typ ist, sondern eine Anweisung an den Compiler, den Typ abzuleiten und zuzuweisen.  
  
 [!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#33)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)