---
title: '#endif – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712545"
---
# <a name="endif-c-reference"></a><span data-ttu-id="0e571-102">#endif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0e571-102">#endif (C# Reference)</span></span>
<span data-ttu-id="0e571-103">`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](./preprocessor-if.md)-Anweisung angefangen hat.</span><span class="sxs-lookup"><span data-stu-id="0e571-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="0e571-104">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="0e571-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e571-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e571-105">Remarks</span></span>  
 <span data-ttu-id="0e571-106">Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e571-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="0e571-107">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.</span><span class="sxs-lookup"><span data-stu-id="0e571-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e571-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e571-108">See also</span></span>

- [<span data-ttu-id="0e571-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0e571-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0e571-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0e571-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0e571-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="0e571-111">C# Preprocessor Directives</span></span>](./index.md)
