---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b264450703090edfcf99f9584c16d33eb82a76e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1003---workflowinstancecanceled"></a>1003 - WorkflowInstanceCanceled
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1003|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Workflowinstanz mit dem Status 'Canceled' abgeschlossen wurde.  
  
## <a name="message"></a>Meldung  
 WorkflowInstance-ID: '%1 ' wurde mit dem Status 'Canceled' abgeschlossen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Die Instanz-ID für den Workflow.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
