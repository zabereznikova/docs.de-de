---
title: '#warning – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 08fcefd904ad43c781017087082592120e21f5cd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236829"
---
# <a name="warning-c-reference"></a>#warning (C#-Referenz)
Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren. Zum Beispiel:  
  
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

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
