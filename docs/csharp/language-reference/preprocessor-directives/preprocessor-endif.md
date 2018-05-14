---
title: '#endif (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 1686e706ce5cae3b2eaa28a7e1c89b5694b2be88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="endif-c-reference"></a>#endif (C#-Referenz)
`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung angefangen hat. Ein auf ein Objekt angewendeter  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden. Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
