---
title: 1126 - InvokedMethodThrewException
ms.date: 03/30/2017
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
ms.openlocfilehash: 7caaebe42f49a62fec61ba17a4d3fe3a538e2ab4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262839"
---
# <a name="1126---invokedmethodthrewexception"></a>1126 - InvokedMethodThrewException

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|1126|  
|Keywords|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>BESCHREIBUNG  

 Gibt an, dass von der Methode, die von der InvokeMethod-Aktivität aufgerufen wurde, eine Ausnahme ausgelöst wurde.  
  
## <a name="message"></a>`Message`  

 In der von der Aktivität '%1' aufgerufenen Methode wurde eine Ausnahme ausgelöst. %2  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Der Anzeigename der InvokeMethod-Aktivität.|  
|Ausnahme|xs:string|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
