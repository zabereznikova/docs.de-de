---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 842d6bb6172eed5f7382633119045ea7507fb955
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1006|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.  
  
## <a name="message"></a>Meldung  
 WorkflowInstance-Id: "%1" hat eine nicht behandelte Ausnahme aufgetreten.  Die Ausnahme stammt von der Aktivität '%2', DisplayName: "%3".  Die folgende Aktion durchzuführenden: %4.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Die Instanz-ID für den Workflow.|  
|Ausnahme|`xs:string`|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
