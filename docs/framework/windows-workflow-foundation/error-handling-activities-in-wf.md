---
title: Fehlerbehandlungsaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 332e16b4c399341151761a4bce2d47198779ad64
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280311"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="08c50-102">Fehlerbehandlungsaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="08c50-102">Error Handling Activities in WF</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="08c50-103">bietet mehrere vom System bereitgestellte Aktivitäten zum Implementieren von Fehlerbehandlungs- und Wiederherstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="08c50-103">provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="08c50-104">Weitere Informationen finden Sie unter [Ausnahmen](exceptions.md)definiert sind.</span><span class="sxs-lookup"><span data-stu-id="08c50-104">For more information, see [Exceptions](exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="08c50-105">Fehlerbehandlungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="08c50-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="08c50-106">Löst die letzte Ausnahme, die in einer `TryCatch`-Aktivität ausgelöst wurde, erneut aus.</span><span class="sxs-lookup"><span data-stu-id="08c50-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="08c50-107">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="08c50-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="08c50-108">Implementiert Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="08c50-108">Implements exception handling.</span></span>|
