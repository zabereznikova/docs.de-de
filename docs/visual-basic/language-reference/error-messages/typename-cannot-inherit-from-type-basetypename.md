---
title: '&#39;&lt;TypeName&gt; &#39; kann nicht von erben &lt;Typ&gt; &#39; &lt;Basistypname&gt; &#39; erweitert den Zugriff der Basis &lt;Typ&gt; außerhalb der Assembly'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 108025132bdd0fa86df5ed142aaa39c7b7e18062
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556482"
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a><span data-ttu-id="a44e6-102">&#39;&lt;TypeName&gt; &#39; kann nicht von erben &lt;Typ&gt; &#39; &lt;Basistypname&gt; &#39; erweitert den Zugriff der Basis &lt;Typ&gt; außerhalb der Assembly</span><span class="sxs-lookup"><span data-stu-id="a44e6-102">&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly</span></span>
<span data-ttu-id="a44e6-103">Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle weist jedoch eine weniger restriktive Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="a44e6-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="a44e6-104">Z. B. eine `Public` Schnittstelle erbt von einer `Friend` -Schnittstelle, oder ein `Protected` Klasse erbt von einer `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="a44e6-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="a44e6-105">Dies stellt die Basisklasse oder Schnittstelle, um nach den gewünschten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a44e6-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="a44e6-106">**Fehler-ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="a44e6-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a44e6-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a44e6-107">To correct this error</span></span>  
  
-   <span data-ttu-id="a44e6-108">Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle, die mindestens so restriktiv wie der Basisklasse oder Schnittstelle sein.</span><span class="sxs-lookup"><span data-stu-id="a44e6-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="a44e6-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="a44e6-109">-or-</span></span>  
  
-   <span data-ttu-id="a44e6-110">Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a44e6-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="a44e6-111">Sie können nicht von einem eingeschränkteren Basisklasse oder Schnittstelle erben.</span><span class="sxs-lookup"><span data-stu-id="a44e6-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44e6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a44e6-112">See also</span></span>
- [<span data-ttu-id="a44e6-113">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a44e6-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="a44e6-114">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a44e6-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="a44e6-115">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a44e6-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="a44e6-116">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a44e6-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
