---
title: "void (C#-Referenz) | Microsoft Docs"
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
  - "void_CSharpKeyword"
  - "void"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "void-Schlüsselwort [C#]"
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# void (C#-Referenz)
Bei Verwendung als Rückgabetyp für eine Methode, `void`, gibt an, dass die Methode keinen Wert zurückgibt.  
  
 `void` wird nicht in der Parameterliste einer Methode zulässig.  Eine Methode, die keine Parameter annimmt und keinen Wert zurückgibt, wird wie folgt deklariert:  
  
```  
public void SampleMethod()  
{  
    // Body of the method.  
}  
  
```  
  
 Außerdem wird `void` in einem nicht sicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren.  Weitere Informationen finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
 `void` ist ein Alias für den <xref:System.Void?displayProperty=fullName>\-Typ von .NET Framework.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)   
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)