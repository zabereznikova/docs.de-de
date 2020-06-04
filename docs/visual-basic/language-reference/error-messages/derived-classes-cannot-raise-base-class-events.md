---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: c59212a28ba27123a7db9163ff7437c159a3d310
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409698"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="2453a-102">Abgeleitete Klassen können keine Basisklassenereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="2453a-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="2453a-103">Ein Ereignis kann nur aus dem Deklarations Bereich ausgelöst werden, in dem es deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="2453a-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="2453a-104">Daher kann eine Klasse keine Ereignisse von einer anderen Klasse, auch von einer Klasse, von der Sie abgeleitet ist, ableiten.</span><span class="sxs-lookup"><span data-stu-id="2453a-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="2453a-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="2453a-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2453a-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2453a-106">To correct this error</span></span>  
  
- <span data-ttu-id="2453a-107">Verschieben Sie die- `Event` Anweisung oder die- `RaiseEvent` Anweisung so, dass Sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="2453a-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2453a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2453a-108">See also</span></span>

- [<span data-ttu-id="2453a-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2453a-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="2453a-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2453a-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
