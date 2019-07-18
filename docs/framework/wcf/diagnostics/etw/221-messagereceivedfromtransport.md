---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781718"
---
# <a name="221---messagereceivedfromtransport"></a>221 - MessageReceivedFromTransport
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|221|  
|Schlüsselwörter|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht vom Transport empfängt.  
  
## <a name="message"></a>Meldung  
 Der Verteiler hat eine Nachricht vom Transport empfangen. Korrelations-ID == '%1'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Correlation ID|`xs:GUID`|Die Aktivitäts-ID, die verwendet wurde, um für ein `MessageSentToTransport`-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`-Objekt zu erstellen.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
