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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
