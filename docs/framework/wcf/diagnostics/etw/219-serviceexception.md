---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781731"
---
# <a name="219---serviceexception"></a>219 - ServiceException
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|219|  
|Schlüsselwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
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
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
