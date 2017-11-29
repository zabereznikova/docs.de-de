---
title: CoordinatorRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1db6f8dc4136623f35767c122dbea46fd4706b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="5e5ad-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="5e5ad-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="5e5ad-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="5e5ad-103">Id: 139</span></span>  
  
 <span data-ttu-id="5e5ad-104">Schweregrad: Fehler</span><span class="sxs-lookup"><span data-stu-id="5e5ad-104">Severity: Error</span></span>  
  
 <span data-ttu-id="5e5ad-105">Kategorie: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="5e5ad-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="5e5ad-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e5ad-106">Description</span></span>  
 <span data-ttu-id="5e5ad-107">Dieses Ereignis gibt an, dass ein Koordinatorwiederherstellungsprotokolleintrag fehlerhaft war und nicht deserialisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="5e5ad-108">Aufgrund dieses Fehlers können Daten verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-108">Data loss may result from this error.</span></span> <span data-ttu-id="5e5ad-109">Das Ereignis führt die TransaktionsID, die Wiederherstellungsdaten (Base64-codiert), die Ausnahme, den Prozessnamen und die Prozess-ID auf.</span><span class="sxs-lookup"><span data-stu-id="5e5ad-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5ad-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e5ad-110">See Also</span></span>  
 [<span data-ttu-id="5e5ad-111">Protokollierung von Komponentenereignissen</span><span class="sxs-lookup"><span data-stu-id="5e5ad-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="5e5ad-112">Allgemeine Referenz zu Ereignissen</span><span class="sxs-lookup"><span data-stu-id="5e5ad-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
