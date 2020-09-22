---
title: Informationen über die Klasse "<classname>" konnten nicht geladen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 449bd34d5026dd4f9b9020123b99df81081f4331
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873505"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="f5ffb-102">Informationen über die Klasse "\<classname>" konnten nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f5ffb-102">Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="f5ffb-103">Es wurde auf eine Klasse verwiesen, die nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f5ffb-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="f5ffb-104">**Fehler-ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="f5ffb-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5ffb-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f5ffb-105">To correct this error</span></span>  
  
1. <span data-ttu-id="f5ffb-106">Vergewissern Sie sich, dass die Klasse definiert ist und Sie den Namen richtig geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="f5ffb-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2. <span data-ttu-id="f5ffb-107">Versuchen Sie, auf einen der im Modul deklarierten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5ffb-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="f5ffb-108">In einigen Fällen können in der Debugumgebung Member nicht gefunden werden, weil die Module, in denen sie deklariert sind, noch nicht geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="f5ffb-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ffb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5ffb-109">See also</span></span>

- [<span data-ttu-id="f5ffb-110">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f5ffb-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
