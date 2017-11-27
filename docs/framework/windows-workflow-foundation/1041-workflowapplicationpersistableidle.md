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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea6b31a83df6e15fe34f9e4be31a4eb53bc5bb51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
