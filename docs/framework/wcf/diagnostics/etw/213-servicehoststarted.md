---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781822"
---
# <a name="213---servicehoststarted"></a>213 - ServiceHostStarted
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|213|  
|Schlüsselwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost|  
|Ebene|LogAlways|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn ein im Web gehosteter Diensthost gestartet wird. Dies kommt in der Regel vor, wenn der Dienst von einer Nachricht aktiviert wird. Es kann auch vorkommen, wenn für den Dienst das automatische Starten konfiguriert ist.  
  
## <a name="message"></a>Meldung  
 ServiceHost wurde gestartet: '%1'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Service Type Name|`xs:string`|Der CLR-FullName des Typs der Dienstimplementierung.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
