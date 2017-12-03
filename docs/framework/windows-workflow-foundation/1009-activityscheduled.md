---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1009|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass die Ausführung einer Aktivität geplant wird.  
  
## <a name="message"></a>Meldung  
 Die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat die untergeordnete Aktivität '%4', DisplayName: '%5', InstanceId: '%6' geplant.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Der Typname der übergeordneten Aktivität.|  
|ParentDisplayName|xs:string|Der Anzeigename der übergeordneten Aktivität.|  
|ParentInstanceId|xs:string|Die Instanz-ID der übergeordneten Aktivität.|  
|ChildActivity|xs:string|Der Typname der untergeordneten Aktivität.|  
|ChildDisplayName|xs:string|Der Anzeigename der untergeordneten Aktivität.|  
|ChildInstanceId|xs:string|Die Instanz-ID der geplanten untergeordneten Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
