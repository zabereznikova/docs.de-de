---
title: '#error (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 9ea4c24dcc3c0a4d39499bee5900cb9c6cc768c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="error-c-reference"></a>#error (C#-Referenz)
Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus einen Fehler generieren. Zum Beispiel:  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.  
  
 Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) zu generieren.  
  
## <a name="example"></a>Beispiel  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
