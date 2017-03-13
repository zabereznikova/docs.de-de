---
title: "private (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "private_CSharpKeyword"
  - "private"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "private-Schlüsselwort [C#]"
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# private (C#-Referenz)
Bei dem `private`\-Schlüsselwort handelt es sich um einen Zugriffsmodifizierer für Member.  Der Zugriff vom Typ private stellt die am meisten eingeschränkte Zugriffsebene dar.  Private Member sind nur innerhalb des Klassen\- oder Strukturtexts zugreifbar, in dem sie deklariert wurden, wie das Beispiel zeigt:  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  
  
 Geschachtelte Typen im gleichen Textbereich können ebenfalls auf Member mit dem Zugriffsmodifizierer private zugreifen.  
  
 Ein Verweis auf einen Member mit dem Zugriffsmodifizierer private außerhalb der Klasse oder Struktur, in der er deklariert wurde, verursacht einen Fehler während der Kompilierung.  
  
 Einen Vergleich von `private` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md) und [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## Beispiel  
 In diesem Beispiel enthält die `Employee`\-Klasse zwei private Datenmember, `name` und `salary`.  Da es sich um private Member handelt, ist der Zugriff nur über Membermethoden möglich.  Die öffentlichen Methoden `GetName` und `Salary` werden hinzugefügt, um den gesteuerten Zugriff auf die privaten Member zu ermöglichen.  Auf den `name`\-Member wird über eine öffentliche Methode zugegriffen, und auf den `salary`\-Member wird über eine öffentliche schreibgeschützte Eigenschaft zugegriffen.  \(Weitere Informationen finden Sie unter [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md).\)  
  
 [!code-cs[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [interne](../../../csharp/language-reference/keywords/internal.md)