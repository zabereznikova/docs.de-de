---
title: Fehlerbehandlungsaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
ms.openlocfilehash: 51431e367f0ec8874588a52cb4dbd76d714768fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512384"
---
# <a name="error-handling-activities-in-wf"></a><span data-ttu-id="1ee9b-102">Fehlerbehandlungsaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="1ee9b-102">Error Handling Activities in WF</span></span>
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="1ee9b-103"> bietet mehrere vom System bereitgestellte Aktivitäten zum Implementieren von Fehlerbehandlungs- und Wiederherstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="1ee9b-103"> provides several system-provided activities for implementing error handling and recovery.</span></span> <span data-ttu-id="1ee9b-104">Weitere Informationen finden Sie unter [Ausnahmen](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="1ee9b-104">For more information, see [Exceptions](../../../docs/framework/windows-workflow-foundation/exceptions.md).</span></span>  
  
## <a name="error-handling-activities"></a><span data-ttu-id="1ee9b-105">Fehlerbehandlungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="1ee9b-105">Error handling activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|<span data-ttu-id="1ee9b-106">Löst die letzte Ausnahme, die in einer `TryCatch`-Aktivität ausgelöst wurde, erneut aus.</span><span class="sxs-lookup"><span data-stu-id="1ee9b-106">Rethrows the last exception thrown from within a `TryCatch` activity.</span></span>|  
|<xref:System.Activities.Statements.Throw>|<span data-ttu-id="1ee9b-107">Löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="1ee9b-107">Throws an exception.</span></span>|  
|<xref:System.Activities.Statements.TryCatch>|<span data-ttu-id="1ee9b-108">Implementiert Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="1ee9b-108">Implements exception handling.</span></span>|
