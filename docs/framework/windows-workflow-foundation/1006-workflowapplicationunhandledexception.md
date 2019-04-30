---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924708"
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
 WorkflowInstance-Id: "%1" hat eine nicht behandelte Ausnahme festgestellt.  Die Ausnahme stammt aus Aktivität '%2', DisplayName: '%3'.  Die folgende Aktion wird ausgeführt: %4.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Die Instanz-ID für den Workflow.|  
|Ausnahme|`xs:string`|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
