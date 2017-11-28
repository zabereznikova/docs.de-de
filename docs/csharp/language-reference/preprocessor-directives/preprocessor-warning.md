---
title: '#<a name="warning-c-reference"></a>warning (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#warning'
helpviewer_keywords: '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8145c4a62d5179d6fa46e27186d83fc0108939d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="warning-c-reference"></a>#warning (C#-Referenz)
Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Warnung der Stufe 1 generieren. Zum Beispiel:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung. Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) zu generieren.  
  
## <a name="example"></a>Beispiel  
  
```csharp
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
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
