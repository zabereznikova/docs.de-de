---
description: '#warning – C#-Referenz'
title: '#warning – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 9ade723bdca17597dcd56240f506e60f2debf6be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186418"
---
# <a name="warning-c-reference"></a>#warning (C#-Referenz)

Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren. Beispiel:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Bemerkungen

 Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung. Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](./preprocessor-error.md) zu generieren.  
  
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

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
