---
title: '&#39;&lt;EventName&gt; &#39; ist ein Ereignis aus, und nicht direkt aufgerufen werden'
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3efd8c18497ce288e16659db4ca4693d5a3e6acc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581994"
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a><span data-ttu-id="c56bc-102">&#39;&lt;EventName&gt; &#39; ist ein Ereignis aus, und nicht direkt aufgerufen werden</span><span class="sxs-lookup"><span data-stu-id="c56bc-102">&#39;&lt;eventname&gt;&#39; is an event, and cannot be called directly</span></span>
<span data-ttu-id="c56bc-103">' <`eventname`>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c56bc-103">'<`eventname`>' is an event, and so cannot be called directly.</span></span> <span data-ttu-id="c56bc-104">Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="c56bc-104">Use a `RaiseEvent` statement to raise an event.</span></span>  
  
 <span data-ttu-id="c56bc-105">Ein Prozeduraufruf gibt ein Ereignis für den Namen der Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="c56bc-105">A procedure call specifies an event for the procedure name.</span></span> <span data-ttu-id="c56bc-106">Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein Signalisierung Gerät ausgelöst und verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c56bc-106">An event handler is a procedure, but the event itself is a signaling device, which must be raised and handled.</span></span>  
  
 <span data-ttu-id="c56bc-107">**Fehler-ID:** BC32022</span><span class="sxs-lookup"><span data-stu-id="c56bc-107">**Error ID:** BC32022</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c56bc-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c56bc-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="c56bc-109">Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis zu signalisieren und Aufrufen der Prozedur oder die Prozeduren, die sie verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c56bc-109">Use a `RaiseEvent` statement to signal an event and invoke the procedure or procedures that handle it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56bc-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c56bc-110">See also</span></span>
- [<span data-ttu-id="c56bc-111">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c56bc-111">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
