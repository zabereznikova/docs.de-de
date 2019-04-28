---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755661"
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|225|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn die inhaltsbasierte Korrelation für einen Workflowdienst verwendet wird. Es enthält die Korrelationsschlüssel, die angewendet werden, um eine Nachricht mit einer Instanz zu korrelieren.  
  
## <a name="message"></a>Meldung  
 Berechneter Korrelationsschlüssel '%1' mit den Werten '%2' im übergeordneten Bereich '%3'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Instance Key|`xs:GUID`|Der Schlüssel, der aus den Korrelationswerten generiert wurde.|  
|Werte|`xs:string`|Die Werte, die verwendet wurden, um den Korrelationsinstanzschlüssel zu berechnen.|  
|Parent Scope|`xs:string`||  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
