---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 3cb61a40e4522695b876d85f67dac1a109d3c3e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595863"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="e72f8-102">Abgeleitete Klassen können keine Basisklassenereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="e72f8-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="e72f8-103">Ein Ereignis kann nur aus der Deklaration ausgelöst werden, in dem sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="e72f8-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="e72f8-104">Eine Klasse kann nicht aus diesem Grund Ereignisse aus einer beliebigen anderen Klasse, selbst eine auslösen, von dem er abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="e72f8-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="e72f8-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="e72f8-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e72f8-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e72f8-106">To correct this error</span></span>  
  
-   <span data-ttu-id="e72f8-107">Verschieben der `Event` Anweisung oder der `RaiseEvent` Anweisung, sodass sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="e72f8-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e72f8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e72f8-108">See also</span></span>
- [<span data-ttu-id="e72f8-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e72f8-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="e72f8-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e72f8-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
