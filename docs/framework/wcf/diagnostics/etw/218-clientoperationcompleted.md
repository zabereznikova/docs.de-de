---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 83f39be84a8d62962b85652b0e39b537c92e612c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457973"
---
# <a name="218---clientoperationcompleted"></a>218 - ClientOperationCompleted
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|218|  
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
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName". Beispiel: "Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
