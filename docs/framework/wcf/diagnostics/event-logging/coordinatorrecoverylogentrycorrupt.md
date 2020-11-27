---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: c3174e70d42385923674a3db5f696a0f64eda29f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295358"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="74f84-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="74f84-102">CoordinatorRecoveryLogEntryCorrupt</span></span>

<span data-ttu-id="74f84-103">ID: 139</span><span class="sxs-lookup"><span data-stu-id="74f84-103">Id: 139</span></span>  
  
 <span data-ttu-id="74f84-104">Schweregrad: Fehler</span><span class="sxs-lookup"><span data-stu-id="74f84-104">Severity: Error</span></span>  
  
 <span data-ttu-id="74f84-105">Kategorie: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="74f84-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="74f84-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="74f84-106">Description</span></span>  

 <span data-ttu-id="74f84-107">Dieses Ereignis gibt an, dass ein Koordinatorwiederherstellungsprotokolleintrag fehlerhaft war und nicht deserialisiert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="74f84-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="74f84-108">Aufgrund dieses Fehlers können Daten verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="74f84-108">Data loss may result from this error.</span></span> <span data-ttu-id="74f84-109">Das Ereignis führt die TransaktionsID, die Wiederherstellungsdaten (Base64-codiert), die Ausnahme, den Prozessnamen und die Prozess-ID auf.</span><span class="sxs-lookup"><span data-stu-id="74f84-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f84-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74f84-110">See also</span></span>

- [<span data-ttu-id="74f84-111">Ereignisprotokollierung</span><span class="sxs-lookup"><span data-stu-id="74f84-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="74f84-112">Allgemeine Referenz zu Ereignissen</span><span class="sxs-lookup"><span data-stu-id="74f84-112">Events General Reference</span></span>](events-general-reference.md)
