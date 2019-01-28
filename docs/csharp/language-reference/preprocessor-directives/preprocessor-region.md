---
title: '#region – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: adaa58fc47da557a31270e99ff8a1dae3d0731bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724030"
---
# <a name="region-c-reference"></a><span data-ttu-id="8eff1-102">#region (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8eff1-102">#region (C# Reference)</span></span>
<span data-ttu-id="8eff1-103">Mit `#region` können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](/visualstudio/ide/outlining) des Code-Editors von Visual Studio erweitert oder reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8eff1-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="8eff1-104">Es ist bei längeren Codedateien bequemer, einen oder mehrere Bereiche reduzieren oder ausblenden zu können, sodass Sie sich auf den Teil der Datei konzentrieren können, an dem Sie gerade arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8eff1-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="8eff1-105">Das folgende Beispiel veranschaulicht, wie Sie einen Bereich definieren:</span><span class="sxs-lookup"><span data-stu-id="8eff1-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="8eff1-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8eff1-106">Remarks</span></span>  
 <span data-ttu-id="8eff1-107">Ein `#region`-Block muss mit einer [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="8eff1-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="8eff1-108">Ein `#region`-Block kann sich nicht mit einem [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Block überschneiden.</span><span class="sxs-lookup"><span data-stu-id="8eff1-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="8eff1-109">Allerdings kann ein `#region`-Block in einem `#if`-Block und ein `#if`-Block in einem `#region`-Block verschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="8eff1-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eff1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8eff1-110">See also</span></span>

- [<span data-ttu-id="8eff1-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8eff1-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="8eff1-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8eff1-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8eff1-113">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="8eff1-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
