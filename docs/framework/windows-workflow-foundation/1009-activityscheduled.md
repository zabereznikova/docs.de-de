---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924656"
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
