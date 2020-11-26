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
# <a name="runtime-activities-in-wf"></a>Laufzeitaktivitäten in WF

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] enthält mehrere vom System bereitgestellte Aktivitäten für den Zugriff auf die Funktionen der Workflowlaufzeit, z. B. Persistenz und Beendigung.  
  
|Aktivität|BESCHREIBUNG|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|Fordert explizit an, dass der Workflow seinen Zustand beibehält.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|Beendet die ausgeführte Workflowinstanz.|  
|<xref:System.Activities.Statements.NoPersistScope>|Eine Containeraktivität, die untergeordnete Aktivitäten an der Beibehaltung hindert.|
