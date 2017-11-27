---
title: 218 - ClientOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea826aa99e847f74c5a44113f2ae16d7322873f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="218---clientoperationcompleted"></a>218 - ClientOperationCompleted
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|218|  
|Stichwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird von Clients direkt nach Abschluss eines Vorgangs ausgegeben. Bei unidirektionalen Vorgänge wird dies direkt nach dem erfolgreichen Senden der Nachricht ausgeführt. Für Anforderung-Antwort-Vorgänge wird dies ausgeführt, nachdem die Antwort empfangen wurde.  
  
## <a name="message"></a>Meldung  
 Der Client hat das Ausführen der Aktion '%1' abgeschlossen, die dem Vertrag '%2' zugeordnet ist. Die Nachricht wurde an '%3' gesendet.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Aktion|xs:string|Der SOAP-Aktionsheader der ausgehenden Nachricht.|  
|Contract Name|`xs:string`|Der Name des Vertrags. Beispiel: ICalculator.|  
|Ziel|`xs:string`|Die Adresse des Dienstendpunkts, an den die Nachricht gesendet wurde.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
