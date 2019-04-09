---
title: MessageQueueDuplicatedSocketLeak
ms.date: 03/30/2017
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
ms.openlocfilehash: 8533d53dc6a2d4510ffec2dcbf0e9bef15cde6ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206121"
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="6d5dc-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="6d5dc-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="6d5dc-103">ID: 165</span><span class="sxs-lookup"><span data-stu-id="6d5dc-103">Id: 165</span></span>  
  
 <span data-ttu-id="6d5dc-104">Schweregrad: Fehler</span><span class="sxs-lookup"><span data-stu-id="6d5dc-104">Severity: Error</span></span>  
  
 <span data-ttu-id="6d5dc-105">Kategorie: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="6d5dc-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="6d5dc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d5dc-106">Description</span></span>  
 <span data-ttu-id="6d5dc-107">Dieses Ereignis gibt an, dass beim Senden eines duplizierten Sockets ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6d5dc-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="6d5dc-108">Dieser Handle geht im Verlauf verloren.</span><span class="sxs-lookup"><span data-stu-id="6d5dc-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="6d5dc-109">Das Ereignis listet die Quelle, die Ausnahme, den Prozessnamen und die Prozess-ID auf.</span><span class="sxs-lookup"><span data-stu-id="6d5dc-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5dc-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d5dc-110">See also</span></span>

- [<span data-ttu-id="6d5dc-111">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="6d5dc-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="6d5dc-112">Allgemeine Referenz zu Ereignissen</span><span class="sxs-lookup"><span data-stu-id="6d5dc-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
