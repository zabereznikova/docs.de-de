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
ms.workload: dotnet
ms.openlocfilehash: 3386138f01d4865b02ca821a30da68e5d73b64e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-activities-in-wf"></a>Laufzeitaktivitäten in WF
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] enthält mehrere vom System bereitgestellte Aktivitäten für den Zugriff auf die Funktionen der Workflowlaufzeit, z. B. Persistenz und Beendigung.  
  
|Aktivität|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Fordert explizit an, dass der Workflow seinen Zustand beibehält.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Beendet die ausgeführte Workflowinstanz.|  
|<xref:System.Activities.Statements.NoPersistScope>|Eine Containeraktivität, die untergeordnete Aktivitäten an der Beibehaltung hindert.|
