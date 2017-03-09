---
title: "#region (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#region"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#region-Direktive [C#]"
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #region (C#-Referenz)
Mit `#region` kann ein Codeblock angegeben werden, der erweitert oder reduziert werden kann, wenn das [Gliederungsfeature](/visual-studio/ide/outlining) des Code\-Editors von Visual Studio verwendet wird.  In umfangreicheren Codedateien ist es hilfreich, einzelne Bereiche ein\- oder ausblenden zu können, um sich auf den Teil einer Datei zu konzentrieren, der gerade bearbeitet wird.  Im folgenden Beispiel wird das Definieren eines Bereichs veranschaulicht:  
  
```  
  
      #region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## Hinweise  
 Ein `#region`\-Block muss mit einer [\#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)\-Direktive beendet werden.  
  
 Ein `#region`\-Block darf einen [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)\-Block nicht überlappen.  Ein `#region`\-Block kann jedoch in einen `#if`\-Block geschachtelt sein, und ein `#if`\-Block kann in einen `#region`\-Block geschachtelt sein.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)