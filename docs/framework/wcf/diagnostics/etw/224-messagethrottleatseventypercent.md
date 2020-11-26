---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243520"
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|224|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Wenn eine der Hauptdienstdrosselungen überschritten wurde, wird das `MessageThrottleExceeded`-Ereignis ausgegeben. Wenn die Aktivitätsauslastung zurückgeht und der aktuelle Wert der Drosselung bei 70 Prozent der aktuellen Grenze liegt, wird dieses Ereignis ausgegeben. Beachten Sie, dass dieses Ereignis erst ausgegeben wird, nachdem sich die Aktivitätsauslastung abgeschwächt hat. Wenn sich der aktuelle Wert um die 70-Prozent-Marke bewegt (z. B. 70,69,70,71,70,69), führt nur das erste Erreichen von 70 Prozent zu einem Ereignis. Nachdem dieses Ereignis ausgegeben wurde, führt das nachfolgende Erreichen der Drosselungsgrenze zu einem `MessageThrottleExceeded`-Ereignis.  
  
## <a name="message"></a>`Message`  

 Die '%1'-Drosselungsgrenze von '%2' liegt bei 70%%.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|Der Name der Drosselung, die überschritten wurde. Dies ist entweder `MaxConcurrentCalls`, `MaxConcurrentInstances` oder `MaxConcurrentSessions`.|  
|Begrenzung|`xs:long`|Die momentan konfigurierte Grenze der Drosselung.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
