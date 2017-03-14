---
title: "try-finally (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "finally"
  - "finally_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "finally-Schlüsselwort [C#]"
  - "try-finally-Anweisung [C#]"
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# try-finally (C#-Referenz)
Mit einem `finally`\-Block können Sie alle Ressourcen bereinigen, die in einem [try](../../../csharp/language-reference/keywords/try-catch.md)\-Block belegt sind, und Sie können Code selbst dann ausführen, wenn eine Ausnahme im `try`\-Block auftritt.  In der Regel werden die Anweisungen eines `finally`\-Blocks ausgeführt, wenn die Steuerung eine `try`\-Anweisung verlässt.  Die Übertragung eines Steuerelements kann infolge einer normalen Ausführung, der Ausführung einer `break`\-, `continue`\-, `goto`\- oder `return`\-Anweisung oder der Weitergabe einer Ausnahme aus der `try`\-Anweisung auftreten.  
  
 Innerhalb einer behandelten Ausnahme ist sichergestellt, dass der zugeordnete `finally`\-Block ausgeführt wird.  Wenn die Ausnahme jedoch nicht behandelt wird, erfolgt die Ausführung des `finally`\-Blocks je nachdem, wie der Entladevorgang für die Ausnahme ausgelöst wird.  Das hängt wiederum davon ab, wie der Computer eingerichtet ist.  Weitere Informationen finden Sie unter [Ausnahmefehlerverarbeitung in der CLR](http://go.microsoft.com/fwlink/?LinkId=128371).  
  
 Wenn eine Anwendung durch einen Ausnahmefehler beendet wird, ist es in der Regel nicht wichtig, ob der `finally`\-Block ausgeführt wird.  Wenn der `finally`\-Block jedoch Anweisungen aufweist, die auch in dieser Situation ausgeführt werden müssen, kann als Lösung ein `catch`\-Block der `try`\-`finally`\-Anweisung hinzugefügt werden.  Sie können auch die Ausnahme abfangen, die möglicherweise im `try`\-Block einer `try`\-`finally`\-Anweisung weiter oben in der Aufrufliste ausgelöst wird.  Die Ausnahme kann also in der Methode abgefangen werden, mit der die Methode aufgerufen wird, in der die `try`\-`finally`\-Anweisung enthalten ist. Die Ausnahme kann aber auch in der Methode abgefangen werden, mit der diese Methode aufgerufen wird, oder in einer beliebigen Methode in der Aufrufliste.  Wenn die Ausnahme nicht abgefangen wird, wird der `finally`\-Block je nachdem, ob vom Betriebssystem ein Entladevorgang für die Ausnahme ausgelöst wird, ausgeführt.  
  
## Beispiel  
 Im folgenden Beispiel wird eine `System.InvalidCastException` Ausnahme durch eine ungültige Konvertierungsanweisung verursacht.  Die Ausnahme wird nicht behandelt.  
  
 [!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 Im folgenden Beispiel wird eine Ausnahme von der `TryCast`\-Methode in einer Methode weiter oben in der Aufrufliste abgefangen.  
  
 [!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 Weitere Informationen zu `finally` finden Sie unter [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
 C\# enthält auch die [Using\-Anweisung](../../../csharp/language-reference/keywords/using-statement.md), die ähnliche Funktionalität für <xref:System.IDisposable>\-Objekte in einer zweckmäßigen Syntax bereitstellt.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [try\-, throw\- und catch\-Anweisungen \(C\+\+\)](/visual-cpp/cpp/try-throw-and-catch-statements-cpp)   
 [Ausnahmebehandlungsanweisungen](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Gewusst wie: Explizites Auslösen von Ausnahmen](../Topic/How%20to:%20Explicitly%20Throw%20Exceptions.md)