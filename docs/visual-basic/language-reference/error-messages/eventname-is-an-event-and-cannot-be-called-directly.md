---
title: <eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3366bc215a45cd7de9dc2de285758a78144df509
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874319"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="c9210-102">\<eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c9210-102">'\<eventname>' is an event, and cannot be called directly</span></span>

<span data-ttu-id="c9210-103">"<`eventname`>" ist ein Ereignis und kann daher nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c9210-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="c9210-104">Verwenden Sie eine- `RaiseEvent` Anweisung, um ein Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="c9210-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="c9210-105">Ein Prozedur aufruame gibt ein Ereignis für den Prozedur Namen an.</span><span class="sxs-lookup"><span data-stu-id="c9210-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="c9210-106">Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierungs Gerät, das ausgelöst und behandelt werden muss.</span><span class="sxs-lookup"><span data-stu-id="c9210-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="c9210-107">**Fehler-ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="c9210-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9210-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c9210-108">To correct this error</span></span>  
  
1. <span data-ttu-id="c9210-109">Verwenden `RaiseEvent` Sie eine-Anweisung, um ein Ereignis zu signalisieren und die Prozeduren und Prozeduren aufzurufen, die</span><span class="sxs-lookup"><span data-stu-id="c9210-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9210-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9210-110">See also</span></span>

- [<span data-ttu-id="c9210-111">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c9210-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
