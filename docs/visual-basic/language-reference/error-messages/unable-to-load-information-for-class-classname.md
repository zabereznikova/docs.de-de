---
title: Kann nicht geladen werden Informationen über die Klasse &#39; &lt;Klassenname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 368484d9138d1ae10efb8c63f6cfaa6bcefa6ed8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528961"
---
# <a name="unable-to-load-information-for-class-39ltclassnamegt39"></a><span data-ttu-id="d622a-102">Kann nicht geladen werden Informationen über die Klasse &#39; &lt;Klassenname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="d622a-102">Unable to load information for class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="d622a-103">Ein Verweis wurde auf eine Klasse erstellt, die nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d622a-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="d622a-104">**Fehler-ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="d622a-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d622a-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d622a-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="d622a-106">Stellen Sie sicher, dass die Klasse definiert ist und der Name richtig geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d622a-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2.  <span data-ttu-id="d622a-107">Versuchen Sie, auf einen der im Modul deklarierten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d622a-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="d622a-108">In einigen Fällen können in der Debugumgebung Member nicht gefunden werden, weil die Module, in denen sie deklariert sind, noch nicht geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="d622a-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d622a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d622a-109">See also</span></span>
- [<span data-ttu-id="d622a-110">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d622a-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
