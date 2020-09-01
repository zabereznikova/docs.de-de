---
description: '#warning – C#-Referenz'
title: '#warning – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: ab2cc5120492fc2a4b94296eb85e563c0a1d5ad3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137837"
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
