---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5750748f2885418b8992ce54bbdf6a92b8e1fe39
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="219---serviceexception"></a>219 - ServiceException
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|219|  
|Stichwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn in einem WCF-Dienst eine nicht behandelte Ausnahme auftritt. Dies schließt nicht behandelte Ausnahmen während der Aktivierung, während der Meldungsverarbeitung und im Benutzercode ein.  
  
## <a name="message"></a>Meldung  
 Während der Meldungsverarbeitung ist eine nicht behandelte Ausnahme vom Typ '%2' aufgetreten. Vollständige Ausnahme ToString: %1.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|Das Ergebnis des Aufrufens von `ToString`() für die CLR-Ausnahme.|  
|ExceptionTypeName|`xs:string`|Der CLR-FullName des Ausnahmetyps.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
