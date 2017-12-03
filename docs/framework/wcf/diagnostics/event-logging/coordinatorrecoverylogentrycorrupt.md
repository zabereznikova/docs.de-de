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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d57f0e7528c8df6ebf98aa712fe3efd728b421d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="216c9-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="216c9-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="216c9-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="216c9-103">Id: 139</span></span>  
  
 <span data-ttu-id="216c9-104">Schweregrad: Fehler</span><span class="sxs-lookup"><span data-stu-id="216c9-104">Severity: Error</span></span>  
  
 <span data-ttu-id="216c9-105">Kategorie: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="216c9-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="216c9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="216c9-106">Description</span></span>  
 <span data-ttu-id="216c9-107">Dieses Ereignis gibt an, dass ein Koordinatorwiederherstellungsprotokolleintrag fehlerhaft war und nicht deserialisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="216c9-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="216c9-108">Aufgrund dieses Fehlers können Daten verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="216c9-108">Data loss may result from this error.</span></span> <span data-ttu-id="216c9-109">Das Ereignis führt die TransaktionsID, die Wiederherstellungsdaten (Base64-codiert), die Ausnahme, den Prozessnamen und die Prozess-ID auf.</span><span class="sxs-lookup"><span data-stu-id="216c9-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216c9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="216c9-110">See Also</span></span>  
 [<span data-ttu-id="216c9-111">Protokollierung von Komponentenereignissen</span><span class="sxs-lookup"><span data-stu-id="216c9-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="216c9-112">Allgemeine Referenz zu Ereignissen</span><span class="sxs-lookup"><span data-stu-id="216c9-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
