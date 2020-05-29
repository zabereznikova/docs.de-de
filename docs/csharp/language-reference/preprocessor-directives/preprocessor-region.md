---
title: '#region – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: 66583d6e067b006b03130d8ff842b56bf57bcebc
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802779"
---
# <a name="region-c-reference"></a><span data-ttu-id="eae91-102">#region (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eae91-102">#region (C# Reference)</span></span>
<span data-ttu-id="eae91-103">Mit `#region` können Sie einen Codeblock festlegen, der bei Verwendung der [Gliederungsfunktion](/visualstudio/ide/outlining) des Code-Editors erweitert oder reduziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="eae91-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="eae91-104">Es ist bei längeren Codedateien bequemer, einen oder mehrere Bereiche reduzieren oder ausblenden zu können, sodass Sie sich auf den Teil der Datei konzentrieren können, an dem Sie gerade arbeiten.</span><span class="sxs-lookup"><span data-stu-id="eae91-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="eae91-105">Das folgende Beispiel veranschaulicht, wie Sie einen Bereich definieren:</span><span class="sxs-lookup"><span data-stu-id="eae91-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="eae91-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eae91-106">Remarks</span></span>  
 <span data-ttu-id="eae91-107">Ein `#region`-Block muss mit einer [#endregion](./preprocessor-endregion.md)-Direktive beendet werden.</span><span class="sxs-lookup"><span data-stu-id="eae91-107">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="eae91-108">Ein `#region`-Block kann sich nicht mit einem [#if](./preprocessor-if.md)-Block überschneiden.</span><span class="sxs-lookup"><span data-stu-id="eae91-108">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="eae91-109">Allerdings kann ein `#region`-Block in einem `#if`-Block und ein `#if`-Block in einem `#region`-Block verschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="eae91-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae91-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eae91-110">See also</span></span>

- [<span data-ttu-id="eae91-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eae91-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eae91-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eae91-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="eae91-113">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="eae91-113">C# Preprocessor Directives</span></span>](./index.md)
