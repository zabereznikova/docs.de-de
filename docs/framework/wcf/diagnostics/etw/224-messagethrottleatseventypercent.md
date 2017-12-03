---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2f96aea0df629c24eb9d795a4409cae6a9c9aa9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|224|  
|Stichwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Wenn eine der Hauptdienstdrosselungen überschritten wurde, wird das `MessageThrottleExceeded`-Ereignis ausgegeben. Wenn die Aktivitätsauslastung zurückgeht und der aktuelle Wert der Drosselung bei 70 Prozent der aktuellen Grenze liegt, wird dieses Ereignis ausgegeben. Beachten Sie, dass dieses Ereignis erst ausgegeben wird, nachdem sich die Aktivitätsauslastung abgeschwächt hat. Wenn sich der aktuelle Wert um die 70-Prozent-Marke bewegt (z. B. 70,69,70,71,70,69), führt nur das erste Erreichen von 70 Prozent zu einem Ereignis. Nachdem dieses Ereignis ausgegeben wurde, führt das nachfolgende Erreichen der Drosselungsgrenze zu einem `MessageThrottleExceeded`-Ereignis.  
  
## <a name="message"></a>Meldung  
 Die '%1'-Drosselungsgrenze von '%2' liegt bei 70%%.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|Der Name der Drosselung, die überschritten wurde. Dies ist entweder `MaxConcurrentCalls`, `MaxConcurrentInstances` oder `MaxConcurrentSessions`.|  
|Limit|`xs:long`|Die momentan konfigurierte Grenze der Drosselung.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
