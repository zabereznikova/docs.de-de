---
title: Abgeleitete Klassen können keine Basisklassenereignisse auslösen.
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 7b86420466d77a6aa45b1201a9375b4433e4b5ec
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163440"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="6394d-102">BC30029: abgeleitete Klassen können keine Basisklassen Ereignisse hervorrufen</span><span class="sxs-lookup"><span data-stu-id="6394d-102">BC30029: Derived classes cannot raise base class events</span></span>

<span data-ttu-id="6394d-103">Ein Ereignis kann nur aus dem Deklarations Bereich ausgelöst werden, in dem es deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="6394d-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="6394d-104">Daher kann eine Klasse keine Ereignisse von einer anderen Klasse, auch von einer Klasse, von der Sie abgeleitet ist, ableiten.</span><span class="sxs-lookup"><span data-stu-id="6394d-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>

 <span data-ttu-id="6394d-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="6394d-105">**Error ID:** BC30029</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6394d-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6394d-106">To correct this error</span></span>

- <span data-ttu-id="6394d-107">Verschieben Sie die- `Event` Anweisung oder die- `RaiseEvent` Anweisung so, dass Sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="6394d-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>

## <a name="see-also"></a><span data-ttu-id="6394d-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6394d-108">See also</span></span>

- [<span data-ttu-id="6394d-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6394d-109">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="6394d-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6394d-110">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
