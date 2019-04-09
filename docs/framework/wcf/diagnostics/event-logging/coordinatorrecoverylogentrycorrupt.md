---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121627"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="0ebc6-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="0ebc6-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="0ebc6-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="0ebc6-103">Id: 139</span></span>  
  
 <span data-ttu-id="0ebc6-104">Schweregrad: Fehler</span><span class="sxs-lookup"><span data-stu-id="0ebc6-104">Severity: Error</span></span>  
  
 <span data-ttu-id="0ebc6-105">Kategorie: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="0ebc6-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="0ebc6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ebc6-106">Description</span></span>  
 <span data-ttu-id="0ebc6-107">Dieses Ereignis gibt an, dass ein Koordinatorwiederherstellungsprotokolleintrag fehlerhaft war und nicht deserialisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="0ebc6-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="0ebc6-108">Aufgrund dieses Fehlers können Daten verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="0ebc6-108">Data loss may result from this error.</span></span> <span data-ttu-id="0ebc6-109">Das Ereignis führt die TransaktionsID, die Wiederherstellungsdaten (Base64-codiert), die Ausnahme, den Prozessnamen und die Prozess-ID auf.</span><span class="sxs-lookup"><span data-stu-id="0ebc6-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebc6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ebc6-110">See also</span></span>

- [<span data-ttu-id="0ebc6-111">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="0ebc6-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="0ebc6-112">Allgemeine Referenz zu Ereignissen</span><span class="sxs-lookup"><span data-stu-id="0ebc6-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
