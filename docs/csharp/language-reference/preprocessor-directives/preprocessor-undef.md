---
title: '#undef (C#-Referenz)'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 3957d58f61e51fab01618f5e1146be9cd0da58fd
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46525567"
---
# <a name="undef-c-reference"></a>#undef (C#-Referenz)
Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) ausgewertet.  
  
 Ein Symbol kann entweder mit der Anweisung [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) oder der Compileroption [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) definiert werden. Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.  
  
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

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
