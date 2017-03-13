---
title: "Delegat (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "delegate_CSharpKeyword"
  - "delegate"
  - "CS0123"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "delegate-Schlüsselwort [C#]"
  - "Funktionszeiger [C#]"
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Delegat (C#-Referenz)
Die Deklaration eines Delegattyps ist einer Methodensignatur ähnlich.  Sie weist einen Rückgabewert und eine beliebige Anzahl Parameter eines beliebigen Typs auf:  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 `delegate` ist ein Referenztyp, mit dem eine benannte oder anonyme Methode gekapselt werden kann.  Delegaten entsprechen den Funktionszeigern in C\+\+, sie sind jedoch typsicher und geschützt.  Anwendungsmöglichkeiten von Delegaten finden Sie unter [Delegaten](../../../csharp/programming-guide/delegates/index.md) und [Generische Delegaten](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
## Hinweise  
 Delegaten bilden die Grundlage für [Ereignisse](../../../csharp/programming-guide/events/index.md).  
  
 Ein Delegat kann instanziiert werden, indem er entweder einer benannten oder einer anonymen Methode zugeordnet wird.  Weitere Informationen finden Sie unter [Benannte Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) und [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
 Der Delegat muss mit einer Methode oder einem Lambda\-Ausdruck instanziiert werden, der einen kompatiblen Rückgabewert und kompatible Eingabeparameter aufweist.  Weitere Informationen zum Grad der zulässigen Varianz bei der Methodensignatur finden Sie unter [Varianz bei Delegaten](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  Zur Verwendung mit anonymen Methoden werden der Delegat und der Code, dem er zugeordnet werden soll, zusammen deklariert.  Beide Methoden zur Instanziierung von Delegaten werden in diesem Abschnitt erläutert.  
  
## Beispiel  
 [!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [Delegaten mit benannten im Vergleich zu anonymen Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)   
 [Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)