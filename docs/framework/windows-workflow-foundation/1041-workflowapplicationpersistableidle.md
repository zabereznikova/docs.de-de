---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924188"
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
 WorkflowApplication-Id: "%1" ist im Leerlauf und dauerhaft.  Die folgende Aktion wird ausgeführt: %2.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|Die Workflowanwendungs-ID|  
|ActionTaken|xs:string|Die Aktion, die für die Workflowanwendung ausgeführt wird.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
