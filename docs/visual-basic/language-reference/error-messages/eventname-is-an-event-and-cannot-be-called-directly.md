---
title: <eventname> ist ein Ereignis und kann nicht direkt aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: bf900566bdb4ecf8d8961a12b5dd67ba426caf27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803311"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="51280-102">"\<Ereignisname >' ist ein Ereignis aus, und nicht direkt aufgerufen werden</span><span class="sxs-lookup"><span data-stu-id="51280-102">'\<eventname>' is an event, and cannot be called directly</span></span>
<span data-ttu-id="51280-103">' <`eventname`>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="51280-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="51280-104">Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="51280-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="51280-105">Ein Prozeduraufruf gibt ein Ereignis für den Namen der Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="51280-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="51280-106">Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierung Gerät ausgelöst und verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="51280-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="51280-107">**Fehler-ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="51280-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51280-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="51280-108">To correct this error</span></span>  
  
1. <span data-ttu-id="51280-109">Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis zu signalisieren und Aufrufen der Prozedur oder die Prozeduren, die sie verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51280-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51280-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51280-110">See also</span></span>

- [<span data-ttu-id="51280-111">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="51280-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
