---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 365ce6ece1d964d3fac2a44f7ed4c1e16f44c95d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586398"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="f0a9a-102">Abgeleitete Klassen können keine Basisklassenereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="f0a9a-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="f0a9a-103">Ein Ereignis kann nur vom Deklarationsabschnitt ausgelöst werden, in der sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="f0a9a-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="f0a9a-104">Aus diesem Grund kann keine Klasse von einer anderen Klasse, eine Auslösen von Ereignissen von der sie abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f0a9a-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="f0a9a-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="f0a9a-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0a9a-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f0a9a-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f0a9a-107">Verschieben der `Event` Anweisung oder der `RaiseEvent` Anweisung, sodass sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="f0a9a-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a9a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0a9a-108">See Also</span></span>  
 [<span data-ttu-id="f0a9a-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0a9a-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="f0a9a-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f0a9a-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
