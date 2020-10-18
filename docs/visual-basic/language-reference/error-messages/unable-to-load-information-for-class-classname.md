---
title: Informationen über die Klasse "<classname>" konnten nicht geladen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 05c3303db90a396479bc396c5c2395c3afbb59ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161607"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a><span data-ttu-id="37da2-102">BC30712: die Informationen für die Klasse "" konnten nicht geladen werden. \<classname></span><span class="sxs-lookup"><span data-stu-id="37da2-102">BC30712: Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="37da2-103">Es wurde auf eine Klasse verwiesen, die nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="37da2-103">A reference was made to a class that is not available.</span></span>

 <span data-ttu-id="37da2-104">**Fehler-ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="37da2-104">**Error ID:** BC30712</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="37da2-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="37da2-105">To correct this error</span></span>

1. <span data-ttu-id="37da2-106">Vergewissern Sie sich, dass die Klasse definiert ist und Sie den Namen richtig geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="37da2-106">Verify that the class is defined and that you spelled the name correctly.</span></span>

2. <span data-ttu-id="37da2-107">Versuchen Sie, auf einen der im Modul deklarierten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="37da2-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="37da2-108">In einigen Fällen können in der Debugumgebung Member nicht gefunden werden, weil die Module, in denen sie deklariert sind, noch nicht geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="37da2-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>

## <a name="see-also"></a><span data-ttu-id="37da2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37da2-109">See also</span></span>

- [<span data-ttu-id="37da2-110">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="37da2-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
