---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a80406ce56000703555f7834714222e03d2b65f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1014---schedulecompletionworkitem"></a>1014 - ScheduleCompletionWorkItem
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1014|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein CompletionWorkItem geplant wurde.  
  
## <a name="message"></a>Meldung  
 Wurde eine CompletionWorkItem geplant für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: "%3".  Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Der Typname der übergeordneten Aktivität.|  
|ParentDisplayName|xs:string|Der Anzeigename der übergeordneten Aktivität.|  
|ParentInstanceId|xs:string|Die Instanz-ID der übergeordneten Aktivität.|  
|CompletedActivity|xs:string|Der Typname der abgeschlossenen Aktivität.|  
|CompletedActivityDisplayName|xs:string|Der Anzeigename der abgeschlossenen Aktivität.|  
|CompletedActivityInstanceId|xs:string|Die Instanz-ID der abgeschlossenen Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
