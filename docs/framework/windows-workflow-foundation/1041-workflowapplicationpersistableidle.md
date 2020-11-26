---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238937"
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|1041|  
|Keywords|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann. Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.  
  
## <a name="message"></a>`Message`  

 WorkflowApplication-ID: ' %1 ' ist im Leerlauf und dauerhaft.  Die folgende Aktion wird ausgeführt: %2.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|Die Workflowanwendungs-ID|  
|ActionTaken|xs:string|Die Aktion, die für die Workflowanwendung ausgeführt wird.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
