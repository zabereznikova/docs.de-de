---
title: "#warning (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#warning-Direktive [C#]"
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# #warning (C#-Referenz)
Mit `#warning` kann eine Warnung der Stufe 1 an einer bestimmten Stelle des Codes generiert werden.  Beispiele:  
  
```  
#warning Deprecated code in this method.  
```  
  
## Hinweise  
 `#warning` wird häufig in bedingten Direktiven verwendet.  Es ist ebenfalls möglich, einen benutzerdefinierten Fehler mit [\#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) zu generieren.  
  
## Beispiel  
  
```  
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)