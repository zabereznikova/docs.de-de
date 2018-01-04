---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1041|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann. Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.  
  
## <a name="message"></a>Meldung  
 WorkflowApplication-Id: "%1" ist im Leerlauf und beibehalten.  Die folgende Aktion durchzuführenden: %2.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|Die Workflowanwendungs-ID|  
|ActionTaken|xs:string|Die Aktion, die für die Workflowanwendung ausgeführt wird.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
