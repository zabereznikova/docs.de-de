---
title: '#region – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 723a904d18955caceea9e0d485ab51f84366c66e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715117"
---
# <a name="region-c-reference"></a><span data-ttu-id="878fb-102">#region (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="878fb-102">#region (C# Reference)</span></span>
<span data-ttu-id="878fb-103">Mit `#region` können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](/visualstudio/ide/outlining) des Code-Editors von Visual Studio erweitert oder reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="878fb-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="878fb-104">Es ist bei längeren Codedateien bequemer, einen oder mehrere Bereiche reduzieren oder ausblenden zu können, sodass Sie sich auf den Teil der Datei konzentrieren können, an dem Sie gerade arbeiten.</span><span class="sxs-lookup"><span data-stu-id="878fb-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="878fb-105">Das folgende Beispiel veranschaulicht, wie Sie einen Bereich definieren:</span><span class="sxs-lookup"><span data-stu-id="878fb-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="878fb-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="878fb-106">Remarks</span></span>  
 <span data-ttu-id="878fb-107">Ein `#region`-Block muss mit einer [#endregion](./preprocessor-endregion.md)-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="878fb-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="878fb-108">Ein `#region`-Block kann sich nicht mit einem [#if](./preprocessor-if.md)-Block überschneiden.</span><span class="sxs-lookup"><span data-stu-id="878fb-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="878fb-109">Allerdings kann ein `#region`-Block in einem `#if`-Block und ein `#if`-Block in einem `#region`-Block verschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="878fb-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="878fb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="878fb-110">See also</span></span>

- [<span data-ttu-id="878fb-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="878fb-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="878fb-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="878fb-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="878fb-113">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="878fb-113">C# Preprocessor Directives</span></span>](./index.md)
