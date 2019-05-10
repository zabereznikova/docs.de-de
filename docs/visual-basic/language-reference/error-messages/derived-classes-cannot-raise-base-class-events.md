---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 030c9c2ffa97572298b23f05c23e3af0df7387b0
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913162"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="33f73-102">Abgeleitete Klassen können keine Basisklassenereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="33f73-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="33f73-103">Ein Ereignis kann nur aus der Deklaration ausgelöst werden, in dem sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="33f73-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="33f73-104">Eine Klasse kann nicht aus diesem Grund Ereignisse aus einer beliebigen anderen Klasse, selbst eine auslösen, von dem er abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="33f73-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="33f73-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="33f73-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33f73-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="33f73-106">To correct this error</span></span>  
  
- <span data-ttu-id="33f73-107">Verschieben der `Event` Anweisung oder der `RaiseEvent` Anweisung, sodass sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="33f73-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f73-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33f73-108">See also</span></span>

- [<span data-ttu-id="33f73-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="33f73-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="33f73-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="33f73-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
