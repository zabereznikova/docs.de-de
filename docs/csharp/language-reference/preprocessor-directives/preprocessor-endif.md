---
description: '#endif – C#-Referenz'
title: '#endif – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168633"
---
# <a name="endif-c-reference"></a><span data-ttu-id="3b37a-103">#endif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3b37a-103">#endif (C# Reference)</span></span>

<span data-ttu-id="3b37a-104">`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](./preprocessor-if.md)-Anweisung angefangen hat.</span><span class="sxs-lookup"><span data-stu-id="3b37a-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="3b37a-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3b37a-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="3b37a-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3b37a-106">Remarks</span></span>  

 <span data-ttu-id="3b37a-107">Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b37a-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="3b37a-108">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.</span><span class="sxs-lookup"><span data-stu-id="3b37a-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b37a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b37a-109">See also</span></span>

- [<span data-ttu-id="3b37a-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3b37a-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3b37a-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3b37a-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3b37a-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="3b37a-112">C# Preprocessor Directives</span></span>](./index.md)
