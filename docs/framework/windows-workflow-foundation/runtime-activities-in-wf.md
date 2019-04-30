---
title: Laufzeitaktivitäten in WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938098"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="cd176-102">Laufzeitaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="cd176-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="cd176-103">enthält mehrere vom System bereitgestellte Aktivitäten für den Zugriff auf die Funktionen der Workflowlaufzeit, z. B. Persistenz und Beendigung.</span><span class="sxs-lookup"><span data-stu-id="cd176-103">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="cd176-104">Aktivität</span><span class="sxs-lookup"><span data-stu-id="cd176-104">Activity</span></span>|<span data-ttu-id="cd176-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd176-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="cd176-106">Fordert explizit an, dass der Workflow seinen Zustand beibehält.</span><span class="sxs-lookup"><span data-stu-id="cd176-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="cd176-107">Beendet die ausgeführte Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="cd176-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="cd176-108">Eine Containeraktivität, die untergeordnete Aktivitäten an der Beibehaltung hindert.</span><span class="sxs-lookup"><span data-stu-id="cd176-108">A container activity that prevents child activities from persisting.</span></span>|
