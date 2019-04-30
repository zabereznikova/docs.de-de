---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925228"
---
# <a name="1008---workflowapplicationunloaded"></a>1008 - WorkflowApplicationUnloaded
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|1008|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Beschreibung  
 Gibt an, dass eine Workflowanwendung entladen wurde.  
  
## <a name="message"></a>Meldung  
 WorkflowInstance-ID: '%1 ' wurde entladen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Die Instanz-ID für den Workflow.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
