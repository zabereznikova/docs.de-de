---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b0a96f1e3ba72a226d9b1a871382a27db61c57e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|205|  
|Stichwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird unmittelbar vor dem Vorgang ausgegeben, bei dem der standardmäßige `OperationInvoker` des Dienstmodells mit dem Aufrufen einer Methode beginnt.  
  
## <a name="message"></a>Meldung  
 Ein OperationInvoker hat die '%1'-Methode aufgerufen. Aufruferdaten: '%2'.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Methodenname|`xs:string`|Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.|  
|Aufruferinformationen|`xs:string`|Die IP-Adresse und die Portnummer des Clients im Format 'IPAddress:PortNumber'. Diese beiden Werte werden aus der 'System.ServiceModel.Channels.RemoteEndpointMessageProperty'-Meldungseigenschaft im Vorgangskontext abgerufen. Beachten Sie, dass dieser Wert für Nicht-TCP-Bindungen `null` ist.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
