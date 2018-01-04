---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a3b03e8ac24bc1652b88b71e8c25862a07c194f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1012---startexecuteactivityworkitem"></a>1012 - StartExecuteActivityWorkItem
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1012|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein ExecuteActivityWorkItem mit der Ausführung beginnt.  
  
## <a name="message"></a>Meldung  
 Die Ausführung eines ExecuteActivityWorkItem für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Aktivität|xs:string|Der Typname der Aktivität.|  
|DisplayName|xs:string|Der Anzeigename der Aktivität.|  
|InstanceId|xs:string|Die Instanz-ID der Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
