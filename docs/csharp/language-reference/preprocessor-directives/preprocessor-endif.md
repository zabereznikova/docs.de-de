---
title: '#endif – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 13b43919b666dcc8c5adfc3490eaad73960547ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243900"
---
# <a name="endif-c-reference"></a><span data-ttu-id="2c8aa-102">#endif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2c8aa-102">#endif (C# Reference)</span></span>
<span data-ttu-id="2c8aa-103">`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)-Anweisung angefangen hat.</span><span class="sxs-lookup"><span data-stu-id="2c8aa-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="2c8aa-104">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="2c8aa-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c8aa-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c8aa-105">Remarks</span></span>  
 <span data-ttu-id="2c8aa-106">Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c8aa-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="2c8aa-107">Unter [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.</span><span class="sxs-lookup"><span data-stu-id="2c8aa-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c8aa-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c8aa-108">See Also</span></span>

- [<span data-ttu-id="2c8aa-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2c8aa-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="2c8aa-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2c8aa-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2c8aa-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="2c8aa-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
