---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a>1029 - ScheduleFaultWorkItem
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1029|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein FaultWorkItem geplant wurde.  
  
## <a name="message"></a>Meldung  
 Wurde ein FaultWorkItem geplant für die Aktivität '%1', DisplayName: '%2', InstanceId: "%3".  Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Der Typname der fault-Aktivität.|  
|FaultActivityDisplayName|xs:string|Der Anzeigename der fault-Aktivität.|  
|FaultActivityInstanceId|xs:string|Die Instanz-ID der fault-Aktivität.|  
|ExceptionActivity|xs:string|Der Typname der Aktivität, die die Ausnahme ausgelöst hat.|  
|ExceptionActivityDisplayName|xs:string|Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.|  
|ExceptionActivityInstanceId|xs:string|Die Instanz-ID der Aktivität, die die Ausnahme ausgelöst hat.|  
|Ausnahme|xs:string|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
