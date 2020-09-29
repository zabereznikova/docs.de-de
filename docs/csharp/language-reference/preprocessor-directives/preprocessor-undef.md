---
description: '#undef – C#-Referenz'
title: '#undef – C#-Referenz'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 7db79be7ea9d8462e09b6ae874bf0ae7d265afe2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150556"
---
# <a name="undef-c-reference"></a>#undef (C#-Referenz)

Mit `#undef` können Sie ein Symbol definieren. Wenn dieses Symbol dann als Ausdruck in einer [#if`false`-Anweisung verwendet wird, wird der Ausdruck als ](./preprocessor-if.md) ausgewertet.  
  
 Ein Symbol kann entweder mit der Anweisung [#define](./preprocessor-define.md) oder der Compileroption [-define](../compiler-options/define-compiler-option.md) definiert werden. Die `#undef`-Anweisung muss in einer Datei vor allen Anweisungen erscheinen, bei denen es sich nicht ebenfalls um Anweisungen handelt.  
  
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

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
