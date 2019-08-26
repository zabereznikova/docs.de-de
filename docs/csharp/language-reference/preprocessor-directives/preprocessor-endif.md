---
title: '#endif – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 74205c836b4eeb2d8b17b907bb13708f3225df08
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608578"
---
# <a name="endif-c-reference"></a><span data-ttu-id="35aff-102">#endif (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="35aff-102">#endif (C# Reference)</span></span>
<span data-ttu-id="35aff-103">`#endif` gibt das Ende einer bedingten Anweisung an, die mit der [#if](./preprocessor-if.md)-Anweisung angefangen hat.</span><span class="sxs-lookup"><span data-stu-id="35aff-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="35aff-104">Ein auf ein Objekt angewendeter</span><span class="sxs-lookup"><span data-stu-id="35aff-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="35aff-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="35aff-105">Remarks</span></span>  
 <span data-ttu-id="35aff-106">Eine bedingte Anweisung, die mit einer `#if`-Anweisung beginnt, muss explizit mit einer `#endif`-Anweisung beendet werden.</span><span class="sxs-lookup"><span data-stu-id="35aff-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="35aff-107">Unter [#if](./preprocessor-if.md) finden Sie ein Beispiel zur Verwendung von `#endif`.</span><span class="sxs-lookup"><span data-stu-id="35aff-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35aff-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35aff-108">See also</span></span>

- [<span data-ttu-id="35aff-109">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="35aff-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35aff-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="35aff-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="35aff-111">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="35aff-111">C# Preprocessor Directives</span></span>](./index.md)
