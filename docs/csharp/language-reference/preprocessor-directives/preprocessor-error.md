---
title: '#error (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: ed43c1f85142ec6c54e44db5e3b0b7de3ef36bb8
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259878"
---
# <a name="error-c-reference"></a>#error (C#-Referenz)
Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren. Zum Beispiel:  
  
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

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
