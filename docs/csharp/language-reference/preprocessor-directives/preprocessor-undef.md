---
title: '#undef (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 870b78580e5350f06fae33f2ac107dc3968b2c6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="undef-c-reference"></a>#undef (C#-Referenz)
Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) ausgewertet.  
  
 Ein Symbol kann entweder mit der [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)-Anweisung oder der Compileroption [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden. Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.  
  
## <a name="example"></a>Beispiel  
  
```csharp
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
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
