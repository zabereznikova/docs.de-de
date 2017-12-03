---
title: 303 - UserDefinedInformationEventOccured
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bc04837834277dccc9d21d27e89c84f09f36167
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="303---userdefinedinformationeventoccured"></a>303 - UserDefinedInformationEventOccured
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|303|  
|Stichwörter|Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom Benutzercode ausgegeben. Entwickler können dieses Ereignis ausgeben, wenn ein benutzerdefiniertes Informationsereignis im Dienst auftritt. Sie können dafür die <xref:System.Diagnostics.Eventing>-APIs verwenden. Zusätzlich ist ein WCF-Beispiel vorhanden, das als Wrapper dieser API fungiert und veranschaulicht, wie Sie dieses Ereignis ordnungsgemäß ausgeben.  
  
## <a name="message"></a>Meldung  
 Name:'%1', Verweis:'%2', Nutzlast:%3  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Name|`xs:string`|Der benutzerdefinierte Name des Ereignisses.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|Payload|`xs:string`|Die benutzerdefinierte Nutzlast des Ereignisses.|
