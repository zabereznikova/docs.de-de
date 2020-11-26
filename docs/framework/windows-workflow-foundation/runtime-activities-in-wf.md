---
title: Laufzeitaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: b0472c669d69d9397843a004bee1bb2c15e139c4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245700"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="5cb35-102">Laufzeitaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="5cb35-102">Runtime Activities in WF</span></span>

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="5cb35-103">enthält mehrere vom System bereitgestellte Aktivitäten für den Zugriff auf die Funktionen der Workflowlaufzeit, z. B. Persistenz und Beendigung.</span><span class="sxs-lookup"><span data-stu-id="5cb35-103">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="5cb35-104">Aktivität</span><span class="sxs-lookup"><span data-stu-id="5cb35-104">Activity</span></span>|<span data-ttu-id="5cb35-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5cb35-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="5cb35-106">Fordert explizit an, dass der Workflow seinen Zustand beibehält.</span><span class="sxs-lookup"><span data-stu-id="5cb35-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="5cb35-107">Beendet die ausgeführte Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="5cb35-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="5cb35-108">Eine Containeraktivität, die untergeordnete Aktivitäten an der Beibehaltung hindert.</span><span class="sxs-lookup"><span data-stu-id="5cb35-108">A container activity that prevents child activities from persisting.</span></span>|
