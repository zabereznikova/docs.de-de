---
title: "var (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "var"
  - "var_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "var-Schlüsselwort [C#]"
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# var (C#-Referenz)
Variablen, die im Methodenbereich deklariert werden, können ab Visual C\# 3.0 den impliziten Typ `var` aufweisen.  Eine implizit typisierte lokale Variable ist stark typisiert, so als hätten Sie den Typ selbst deklariert. In diesem Fall hat jedoch der Compiler den Typ bestimmt.  Die folgenden beiden Deklarationen von `i` sind funktional äquivalent:  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Abfrageausdrücke veranschaulicht.  Im ersten Ausdruck ist der Gebrauch von `var` zulässig, jedoch nicht erforderlich, da der Typ des Abfrageergebnisses explizit als `IEnumerable<string>` angegeben werden kann.  Im zweiten Ausdruck hingegen muss `var` verwendet werden, da das Ergebnis eine Auflistung von anonymen Typen ist und der Name des Typs nur für den Compiler selbst zugänglich ist.  Beachten Sie, dass in Beispiel 2 die `foreach`\-Iterationsvariable `item` ebenfalls implizit typisiert sein muss.  
  
 [!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)