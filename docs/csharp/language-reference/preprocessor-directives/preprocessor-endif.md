---
title: '#endif – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 58e29363ca1298966ecf88e6b456f33f43a176b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573045"
---
# <a name="endif-c-reference"></a><span data-ttu-id="3ab80-102">#endif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3ab80-102">#endif (C# Reference)</span></span>
<span data-ttu-id="3ab80-103">`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung angefangen hat.</span><span class="sxs-lookup"><span data-stu-id="3ab80-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="3ab80-104">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="3ab80-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="3ab80-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ab80-105">Remarks</span></span>  
 <span data-ttu-id="3ab80-106">Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ab80-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="3ab80-107">Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.</span><span class="sxs-lookup"><span data-stu-id="3ab80-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab80-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ab80-108">See also</span></span>

- [<span data-ttu-id="3ab80-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3ab80-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="3ab80-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3ab80-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3ab80-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="3ab80-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
