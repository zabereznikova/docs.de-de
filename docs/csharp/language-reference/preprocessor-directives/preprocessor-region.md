---
title: '#region (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 3edc4fe757ab1f5cbf42e67ab74cd8032a82d853
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463272"
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

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
