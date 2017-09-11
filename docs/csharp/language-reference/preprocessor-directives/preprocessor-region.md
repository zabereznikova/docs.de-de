---
title: '#<a name="region-c-reference"></a>region (C#-Referenz)'
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7685d23bc1d40a0d0b6c9ac9a644019e1186eb7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="region-c-reference"></a><span data-ttu-id="697cc-102">#region (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="697cc-102">#region (C# Reference)</span></span>
<span data-ttu-id="697cc-103">Mit `#region` können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](/visualstudio/ide/outlining) des Code-Editors von Visual Studio erweitert oder reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="697cc-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="697cc-104">Es ist bei längeren Codedateien bequemer, einen oder mehrere Bereiche reduzieren oder ausblenden zu können, sodass Sie sich auf den Teil der Datei konzentrieren können, an dem Sie gerade arbeiten.</span><span class="sxs-lookup"><span data-stu-id="697cc-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="697cc-105">Das folgende Beispiel veranschaulicht, wie Sie einen Bereich definieren:</span><span class="sxs-lookup"><span data-stu-id="697cc-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="697cc-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="697cc-106">Remarks</span></span>  
 <span data-ttu-id="697cc-107">Ein `#region`-Block muss mit einer [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="697cc-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="697cc-108">Ein `#region`-Block kann sich nicht mit einem [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Block überschneiden.</span><span class="sxs-lookup"><span data-stu-id="697cc-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="697cc-109">Allerdings kann ein `#region`-Block in einem `#if`-Block und ein `#if`-Block in einem `#region`-Block verschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="697cc-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697cc-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="697cc-110">See Also</span></span>  
 <span data-ttu-id="697cc-111">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="697cc-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="697cc-112">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="697cc-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="697cc-113">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="697cc-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

