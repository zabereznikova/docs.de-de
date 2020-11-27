---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 4aa0f41b0b772551d9257920e5c15051961b7332
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267818"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a>208 - MessageInspectorAfterReceiveInvoked

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|id|208|  
|Keywords|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterReceive`-Methode auf einem Nachrichteninspektor aufgerufen hat.  
  
## <a name="message"></a>`Message`  

 Der Verteiler hat 'AfterReceiveReply' auf einem MessageInspector vom Typ '%1' aufgerufen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|TypName|`xs:string`|Der CLR-FullName des aufgerufenen `MessageInspector`-Typs.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Dienst Name '" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService '.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
