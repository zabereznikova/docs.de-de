---
title: <typename> erweitert den Zugriff der Basis-<type> außerhalb der Assembly und kann daher nicht von <basetypename> "<type>" erben.
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: aa04c558abbcc4259c2821cdcbdc1669b91ffee0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402771"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="ed120-102">\<typename> erweitert den Zugriff der Basis-\<type> außerhalb der Assembly und kann daher nicht von \<basetypename> "\<type>" erben.</span><span class="sxs-lookup"><span data-stu-id="ed120-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="ed120-103">Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle, verfügt aber über eine weniger restriktive Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="ed120-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="ed120-104">Eine- `Public` Schnittstelle erbt z. b. von einer- `Friend` Schnittstelle, oder eine `Protected` Klasse erbt von einer- `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="ed120-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="ed120-105">Dadurch wird die Basisklasse oder Schnittstelle für den Zugriff über die beabsichtigte Ebene verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ed120-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="ed120-106">**Fehler-ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="ed120-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed120-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ed120-107">To correct this error</span></span>  
  
- <span data-ttu-id="ed120-108">Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle so, dass Sie mindestens so restriktiv ist wie die der Basisklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ed120-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="ed120-109">Oder</span><span class="sxs-lookup"><span data-stu-id="ed120-109">-or-</span></span>  
  
- <span data-ttu-id="ed120-110">Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die- `Inherits` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ed120-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="ed120-111">Es ist nicht möglich, von einer eingeschränkteren Basisklasse oder Schnittstelle zu erben.</span><span class="sxs-lookup"><span data-stu-id="ed120-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed120-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed120-112">See also</span></span>

- [<span data-ttu-id="ed120-113">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ed120-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="ed120-114">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ed120-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="ed120-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="ed120-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="ed120-116">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed120-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
