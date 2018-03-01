---
title: "&#39; &lt;Typename&gt;&#39; kann nicht Vererben &lt;Typ&gt; &#39;&lt; Basistypname&gt;&#39; erweitert den Zugriff von Basis-und &lt;Typ&gt; außerhalb der Assembly"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a><span data-ttu-id="9d0c0-102">&#39; &lt;Typename&gt;&#39; kann nicht Vererben &lt;Typ&gt; &#39;&lt; Basistypname&gt;&#39; erweitert den Zugriff von Basis-und &lt;Typ&gt; außerhalb der Assembly</span><span class="sxs-lookup"><span data-stu-id="9d0c0-102">&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly</span></span>
<span data-ttu-id="9d0c0-103">Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle enthält jedoch eine weniger restriktive Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="9d0c0-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="9d0c0-104">Z. B. eine `Public` Schnittstelle erbt von einer `Friend` -Schnittstelle, oder eine `Protected` Klasse erbt von einer `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="9d0c0-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="9d0c0-105">Dies stellt die Basisklasse oder-Schnittstelle außerhalb der vorgesehenen Ebene den Zugriff auf.</span><span class="sxs-lookup"><span data-stu-id="9d0c0-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="9d0c0-106">**Fehler-ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="9d0c0-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d0c0-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9d0c0-107">To correct this error</span></span>  
  
-   <span data-ttu-id="9d0c0-108">Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle, die mindestens so restriktiv wie, die von der Basisklasse oder Schnittstelle sein.</span><span class="sxs-lookup"><span data-stu-id="9d0c0-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="9d0c0-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="9d0c0-109">-or-</span></span>  
  
-   <span data-ttu-id="9d0c0-110">Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9d0c0-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="9d0c0-111">Sie können nicht von einem eingeschränkteren Basisklasse oder Schnittstelle erben.</span><span class="sxs-lookup"><span data-stu-id="9d0c0-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d0c0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d0c0-112">See Also</span></span>  
 [<span data-ttu-id="9d0c0-113">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9d0c0-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="9d0c0-114">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9d0c0-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="9d0c0-115">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9d0c0-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="9d0c0-116">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d0c0-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
