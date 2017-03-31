---
title: '#region (C#-Referenz) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#region'
dev_langs:
- CSharp
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2924daffcdc44c8f5ba5cf97c5b141c0dd07ca4a
ms.lasthandoff: 03/13/2017

---
# <a name="region-c-reference"></a>#region (C#-Referenz)
Mit `#region` können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](https://docs.microsoft.com/visualstudio/ide/outlining) des Code-Editors von Visual Studio erweitert oder reduziert werden kann. Es ist bei längeren Codedateien bequemer, einen oder mehrere Bereiche reduzieren oder ausblenden zu können, sodass Sie sich auf den Teil der Datei konzentrieren können, an dem Sie gerade arbeiten. Das folgende Beispiel veranschaulicht, wie Sie einen Bereich definieren:  
  
```  
  
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
