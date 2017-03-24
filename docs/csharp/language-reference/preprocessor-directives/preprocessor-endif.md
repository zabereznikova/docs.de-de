---
title: "#endif (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#endif"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#endif-Direktive [C#]"
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# #endif (C#-Referenz)
`#endif` gibt das Ende einer bedingten Direktive an, die mit der [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)\-Direktive begann.  Beispiel:  
  
```  
  
      #define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## Hinweise  
 Eine bedingte Direktive, die mit einer `#if`\-Direktive beginnt, muss explizit mit einer `#endif`\-Direktive beendet werden.  Unter [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)