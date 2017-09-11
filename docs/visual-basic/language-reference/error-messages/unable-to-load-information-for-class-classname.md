---
title: "Informationen für die Klasse können nicht geladen&lt;Classname&gt;&quot; | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30712
- bc30712
dev_langs:
- VB
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0e95ba21e7ec751fe0276244dd1ce49552b178ab
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-load-information-for-class-39ltclassnamegt39"></a><span data-ttu-id="59efb-102">Informationen für die Klasse können nicht geladen&lt;Classname&gt;'</span><span class="sxs-lookup"><span data-stu-id="59efb-102">Unable to load information for class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="59efb-103">Ein Verweis wurde auf eine Klasse erstellt, die nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="59efb-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="59efb-104">**Fehler-ID:** BC30712</span><span class="sxs-lookup"><span data-stu-id="59efb-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="59efb-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="59efb-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="59efb-106">Stellen Sie sicher, dass die Klasse definiert ist und der Name richtig geschrieben.</span><span class="sxs-lookup"><span data-stu-id="59efb-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2.  <span data-ttu-id="59efb-107">Versuchen Sie, auf einen der im Modul deklarierten Member zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="59efb-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="59efb-108">In einigen Fällen können in der Debugumgebung Member nicht gefunden werden, weil die Module, in denen sie deklariert sind, noch nicht geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="59efb-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59efb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59efb-109">See Also</span></span>  
 [<span data-ttu-id="59efb-110">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="59efb-110">Debugging in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)
