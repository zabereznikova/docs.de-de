---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 04c5e0f4fbf3b95485e5bf4aae53aa2e4912d893
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294494"
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|225|  
|Keywords|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird ausgegeben, wenn die inhaltsbasierte Korrelation für einen Workflowdienst verwendet wird. Es enthält die Korrelationsschlüssel, die angewendet werden, um eine Nachricht mit einer Instanz zu korrelieren.  
  
## <a name="message"></a>`Message`  

 Berechneter Korrelationsschlüssel '%1' mit den Werten '%2' im übergeordneten Bereich '%3'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|Instance Key|`xs:GUID`|Der Schlüssel, der aus den Korrelationswerten generiert wurde.|  
|Werte|`xs:string`|Die Werte, die verwendet wurden, um den Korrelationsinstanzschlüssel zu berechnen.|  
|Parent Scope|`xs:string`||  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
