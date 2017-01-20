---
title: "#undef (C#-Referenz) | Microsoft Docs"
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
  - "#undef"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#undef-Direktive [C#]"
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #undef (C#-Referenz)
Mit `#undef` kann die Definition eines Symbols aufgehoben werden, sodass beim Verwenden des Symbols als Ausdruck in einer [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)\-Direktive der Ausdruck als `false` ausgewertet wird.  
  
 Ein Symbol kann entweder mit der [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)\-Direktive oder mit der [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)\-Compileroption definiert werden.  Die `#undef`\-Direktive muss in einer Datei vor allen Anweisungen, die keine Direktiven darstellen, verwendet werden.  
  
## Beispiel  
  
```  
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
  **DEBUG ist nicht definiert**   
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)