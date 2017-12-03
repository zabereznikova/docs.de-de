---
title: "Laufzeitaktivitäten in WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 022f12448d697ba179fb3705f18962e6b0c44239
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="78a39-102">Laufzeitaktivitäten in WF</span><span class="sxs-lookup"><span data-stu-id="78a39-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="78a39-103"> enthält mehrere vom System bereitgestellte Aktivitäten für den Zugriff auf die Funktionen der Workflowlaufzeit, z. B. Persistenz und Beendigung.</span><span class="sxs-lookup"><span data-stu-id="78a39-103"> provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="78a39-104">Aktivität</span><span class="sxs-lookup"><span data-stu-id="78a39-104">Activity</span></span>|<span data-ttu-id="78a39-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78a39-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="78a39-106">Fordert explizit an, dass der Workflow seinen Zustand beibehält.</span><span class="sxs-lookup"><span data-stu-id="78a39-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="78a39-107">Beendet die ausgeführte Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="78a39-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="78a39-108">Eine Containeraktivität, die untergeordnete Aktivitäten an der Beibehaltung hindert.</span><span class="sxs-lookup"><span data-stu-id="78a39-108">A container activity that prevents child activities from persisting.</span></span>|
