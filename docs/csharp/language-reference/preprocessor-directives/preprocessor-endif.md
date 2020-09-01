---
description: '#endif – C#-Referenz'
title: '#endif – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 8068a6e437145178fd5c88763c86692a8700c349
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138162"
---
# <a name="endif-c-reference"></a><span data-ttu-id="1978e-103">#endif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1978e-103">#endif (C# Reference)</span></span>
<span data-ttu-id="1978e-104">`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](./preprocessor-if.md)-Anweisung angefangen hat.</span><span class="sxs-lookup"><span data-stu-id="1978e-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="1978e-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1978e-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="1978e-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1978e-106">Remarks</span></span>  
 <span data-ttu-id="1978e-107">Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden.</span><span class="sxs-lookup"><span data-stu-id="1978e-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="1978e-108">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.</span><span class="sxs-lookup"><span data-stu-id="1978e-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1978e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1978e-109">See also</span></span>

- [<span data-ttu-id="1978e-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1978e-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1978e-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1978e-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1978e-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="1978e-112">C# Preprocessor Directives</span></span>](./index.md)
