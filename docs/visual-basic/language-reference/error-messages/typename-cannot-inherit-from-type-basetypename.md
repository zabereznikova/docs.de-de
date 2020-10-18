---
title: <typename> erweitert den Zugriff der Basis-<type> außerhalb der Assembly und kann daher nicht von <basetypename> "<type>" erben.
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 5c019f9d74b11e48aa05a1480b9449fa28488b43
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161841"
---
# <a name="bc30910-typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="6a729-102">BC30910: ' \<typename> ' kann nicht von \<type> ' \<basetypename> ' erben, da der Zugriff auf die Basis \<type> außerhalb der Assembly erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="6a729-102">BC30910: '\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>

<span data-ttu-id="6a729-103">Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle, verfügt aber über eine weniger restriktive Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="6a729-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>

 <span data-ttu-id="6a729-104">Eine- `Public` Schnittstelle erbt z. b. von einer- `Friend` Schnittstelle, oder eine `Protected` Klasse erbt von einer- `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="6a729-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="6a729-105">Dadurch wird die Basisklasse oder Schnittstelle für den Zugriff über die beabsichtigte Ebene verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="6a729-105">This exposes the base class or interface to access beyond the intended level.</span></span>

 <span data-ttu-id="6a729-106">**Fehler-ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="6a729-106">**Error ID:** BC30910</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6a729-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6a729-107">To correct this error</span></span>

- <span data-ttu-id="6a729-108">Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle so, dass Sie mindestens so restriktiv ist wie die der Basisklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6a729-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>

     <span data-ttu-id="6a729-109">Oder</span><span class="sxs-lookup"><span data-stu-id="6a729-109">-or-</span></span>

- <span data-ttu-id="6a729-110">Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die- `Inherits` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6a729-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="6a729-111">Es ist nicht möglich, von einer eingeschränkteren Basisklasse oder Schnittstelle zu erben.</span><span class="sxs-lookup"><span data-stu-id="6a729-111">You cannot inherit from a more restricted base class or interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a729-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a729-112">See also</span></span>

- [<span data-ttu-id="6a729-113">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6a729-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="6a729-114">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6a729-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="6a729-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="6a729-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="6a729-116">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a729-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
