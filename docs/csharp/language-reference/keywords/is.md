---
title: "is (C#-Referenz) | Microsoft Docs"
ms.date: "2017-02-17"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "is_CSharpKeyword"
  - "is"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "is-Schlüsselwort [C#]"
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# is (C#-Referenz)
Überprüft, ob ein Objekt mit einem bestimmten Typ kompatibel ist.  Der folgende Code kann beispielsweise feststellen, ob ein Objekt eine Instanz des `MyObject`\-Typs ist oder ein Typ, der von `MyObject` abgeleitet wird:  
  
```  
if (obj is MyObject)  
{  
}  
```  
  
 Ein `is`\-Ausdruck wird mit `true` ausgewertet, wenn der bereitgestellte Ausdruck nicht NULL ist und das bereitgestellte Objekt in den bereitgestellten Typ umgewandelt werden kann, ohne dass eine Ausnahme ausgelöst wird.  
  
 Das `is`\-Schlüsselwort führt zur Kompilierzeit zu einer Warnung, wenn der Ausdruck bekanntermaßen immer `true` ist oder wenn er immer `false` ist, zur Laufzeit aber in der Regel das Ergebnis der Typkompatibilität liefert.  
  
 Der Operator `is` kann nicht überladen werden.  
  
 Beachten Sie, dass der Operator `is` nur Verweis\-, Boxing\- und Unboxingkonvertierungen berücksichtigt.  Andere Konvertierungen, z. B. benutzerdefinierte Konvertierungen, werden nicht berücksichtigt.  
  
 Anonyme Methoden werden nicht auf der linken Seite des Operators `is` zugelassen.  Diese Ausnahme schließt Lambda\-Ausdrücke ein.  
  
## Beispiel  
 [!code-cs[csrefKeywordsOperator#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/is_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)