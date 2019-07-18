---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008797"
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1031|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass ein FaultWorkItem abgeschlossen wurde.  
  
## <a name="message"></a>Meldung  
 Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen. Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.  
  
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
