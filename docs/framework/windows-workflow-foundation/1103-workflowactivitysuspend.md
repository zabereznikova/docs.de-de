---
title: 1103 - WorkflowActivitySuspend
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 381d68d3f2f36b73cde4fa4edf9ae38dc9ef1be7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1103---workflowactivitysuspend"></a>1103 - WorkflowActivitySuspend
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1103|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Workflowaktivität unterbrochen wurde.  
  
## <a name="message"></a>Meldung  
 WorkflowInstance-ID: '%1' E2E-Aktivität  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Die Instanz-ID für den Workflow.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
