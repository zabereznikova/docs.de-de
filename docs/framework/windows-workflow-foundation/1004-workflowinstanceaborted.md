---
title: 1004 - WorkflowInstanceAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc940e1781f821f12efb42c5198e77eb0451a164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1004---workflowinstanceaborted"></a>1004 - WorkflowInstanceAborted
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1004|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.  
  
## <a name="message"></a>Meldung  
 WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Die Instanz-ID für den Workflow.|  
|Ausnahme|`xs:string`|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
