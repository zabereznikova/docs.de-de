---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 07712104a8dac002d46aee2ba6637bbbc9d850b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532337"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="b55e3-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="b55e3-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="b55e3-103">ID: 165</span><span class="sxs-lookup"><span data-stu-id="b55e3-103">Id: 165</span></span>  
  
 <span data-ttu-id="b55e3-104">Schweregrad: Fehler</span><span class="sxs-lookup"><span data-stu-id="b55e3-104">Severity: Error</span></span>  
  
 <span data-ttu-id="b55e3-105">Kategorie: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="b55e3-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="b55e3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b55e3-106">Description</span></span>  
 <span data-ttu-id="b55e3-107">Dieses Ereignis gibt an, dass beim Senden eines duplizierten Sockets ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b55e3-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="b55e3-108">Dieser Handle geht im Verlauf verloren.</span><span class="sxs-lookup"><span data-stu-id="b55e3-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="b55e3-109">Das Ereignis listet die Quelle, die Ausnahme, den Prozessnamen und die Prozess-ID auf.</span><span class="sxs-lookup"><span data-stu-id="b55e3-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55e3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b55e3-110">See also</span></span>
- [<span data-ttu-id="b55e3-111">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="b55e3-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="b55e3-112">Allgemeine Referenz zu Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b55e3-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
