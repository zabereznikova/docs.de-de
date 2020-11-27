---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: e549a8aabd0a54022000515050cde19dc4f20dd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294065"
---
# <a name="401--stopsignpostevent"></a>401- StopSignPostEvent

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|401|  
|Keywords|Problembehandlung|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis kennzeichnet das Ende einer End-to-End-Aktivität. Enthält den Namen der Aktivität.  
  
## <a name="message"></a>`Message`  

 Aktivitätsgrenze.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|Der Name der Aktivität.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
