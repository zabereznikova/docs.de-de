---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874488"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="08447-102">Abgeleitete Klassen können keine Basisklassenereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="08447-102">Derived classes cannot raise base class events</span></span>

<span data-ttu-id="08447-103">Ein Ereignis kann nur aus dem Deklarations Bereich ausgelöst werden, in dem es deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="08447-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="08447-104">Daher kann eine Klasse keine Ereignisse von einer anderen Klasse, auch von einer Klasse, von der Sie abgeleitet ist, ableiten.</span><span class="sxs-lookup"><span data-stu-id="08447-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="08447-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="08447-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08447-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="08447-106">To correct this error</span></span>  
  
- <span data-ttu-id="08447-107">Verschieben Sie die- `Event` Anweisung oder die- `RaiseEvent` Anweisung so, dass Sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="08447-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08447-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08447-108">See also</span></span>

- [<span data-ttu-id="08447-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="08447-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="08447-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="08447-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
