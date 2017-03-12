---
title: "#define (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#define-Direktive [C#]"
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# #define (C#-Referenz)
Mit `#define` wird ein Symbol definiert.  Wenn Sie das Symbol als Ausdruck verwenden, der an die [\#if\-](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)\-Direktive übergeben wird, wird der Ausdruck als `true` ausgewertet, wie in folgendem Beispiel dargestellt:  
  
 `#`  `define`   `DEBUG`  
  
## Hinweise  
  
> [!NOTE]
>  Die `#define`\-Direktive kann nicht zur Deklaration konstanter Werte wie in C und C\+\+ verwendet werden.  Definieren Sie Konstanten in C\# als statische Member einer Klasse oder einer Struktur.  Wenn Sie über mehrere solcher Konstanten verfügen, erwägen Sie, eine separate "Constants"\-Klasse zu erstellen.  
  
 Symbole können verwendet werden, um Bedingungen für die Kompilierung anzugeben.  Ein Symbol kann entweder mit [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) oder mit [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) überprüft werden.  Für bedingte Kompilierung kann auch das `conditional`\-Attribut verwendet werden.  
  
 Ein Symbol kann zwar definiert werden, aber es kann ihm kein Wert zugewiesen werden.  Die `#define`\-Direktive muss in einer Datei vor allen Anweisungen, bei denen es sich nicht um Präprozessordirektiven handelt, verwendet werden.  
  
 Ein Symbol kann auch mit der [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)\-Compileroption definiert werden.  Die Definition eines Symbols kann mit [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) aufgehoben werden.  
  
 Zwischen einem Symbol, das mit `/define` oder mit `#define` definiert wird, und einer Variablen mit dem gleichen Namen kommt es zu keinem Konflikt.  Das bedeutet, dass ein Variablenname nicht an eine Präprozessordirektive übergeben werden sollte und ein Symbol nur von einer Präprozessordirektive ausgewertet werden kann.  
  
 Bei dem Gültigkeitsbereich eines mit `#define` erstellten Symbols handelt es sich um die Datei, in der es definiert wurde.  
  
 Wie im folgenden Beispiel dargestellt, müssen Sie die `#define`\-Direktive am Anfang der Datei eingeben.  
  
```c#  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 Ein Beispiel dafür, wie eine Symboldefinition aufgehoben wird, finden Sie unter [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [How to: Compile Conditionally with Trace and Debug](../Topic/How%20to:%20Compile%20Conditionally%20with%20Trace%20and%20Debug.md)   
 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)   
 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)