---
title: '#region (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 88632b04ec8932e22f5bf7a23b8f0edf14d89f27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274964"
---
# <a name="region-c-reference"></a>#region (C#-Referenz)
Mit `#region` können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](/visualstudio/ide/outlining) des Code-Editors von Visual Studio erweitert oder reduziert werden kann. Es ist bei längeren Codedateien bequemer, einen oder mehrere Bereiche reduzieren oder ausblenden zu können, sodass Sie sich auf den Teil der Datei konzentrieren können, an dem Sie gerade arbeiten. Das folgende Beispiel veranschaulicht, wie Sie einen Bereich definieren:  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein `#region`-Block muss mit einer [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)-Direktive beendet werden.  
  
 Ein `#region`-Block kann sich nicht mit einem [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Block überschneiden. Allerdings kann ein `#region`-Block in einem `#if`-Block und ein `#if`-Block in einem `#region`-Block verschachtelt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
