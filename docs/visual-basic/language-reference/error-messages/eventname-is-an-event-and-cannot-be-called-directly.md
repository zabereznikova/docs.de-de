---
title: <eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 510fff5370e63a31ee271421c0ab6f154518899f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409594"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="dd75c-102">\<eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd75c-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="dd75c-103">"<`eventname`>" ist ein Ereignis und kann daher nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd75c-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="dd75c-104">Verwenden Sie eine- `RaiseEvent` Anweisung, um ein Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="dd75c-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="dd75c-105">Ein Prozedur aufruame gibt ein Ereignis für den Prozedur Namen an.</span><span class="sxs-lookup"><span data-stu-id="dd75c-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="dd75c-106">Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierungs Gerät, das ausgelöst und behandelt werden muss.</span><span class="sxs-lookup"><span data-stu-id="dd75c-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="dd75c-107">**Fehler-ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="dd75c-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd75c-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="dd75c-108">To correct this error</span></span>  
  
1. <span data-ttu-id="dd75c-109">Verwenden `RaiseEvent` Sie eine-Anweisung, um ein Ereignis zu signalisieren und die Prozeduren und Prozeduren aufzurufen, die</span><span class="sxs-lookup"><span data-stu-id="dd75c-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd75c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd75c-110">See also</span></span>

- [<span data-ttu-id="dd75c-111">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dd75c-111">RaiseEvent Statement</span></span>](../statements/raiseevent-statement.md)
