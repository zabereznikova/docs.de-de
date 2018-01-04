---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d54930a29a24dab97ce403c2808fb74b8cbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="301---userdefinederroroccurred"></a>301 - UserDefinedErrorOccurred
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|301|  
|Stichwörter|Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom Benutzercode ausgegeben. Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefinierter Fehler im Dienst auftritt. Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden. Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.  
  
## <a name="message"></a>Meldung  
 Name:'%1', Verweis:'%2', Nutzlast:%3  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|name|`xs:string`|Der benutzerdefinierte Name des Ereignisses.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|Payload|`xs:string`|Die benutzerdefinierte Nutzlast des Ereignisses.|
