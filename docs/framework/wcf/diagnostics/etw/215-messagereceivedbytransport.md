---
title: 215 - MessageReceivedByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 92880fd01f8f61a06c9b2c7d51ecc4a1671c6c85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="215---messagereceivedbytransport"></a>215 - MessageReceivedByTransport
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|215|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis tritt auf, wenn ein TCP-basierter Transport eine Nachricht empfängt. Beachten Sie, dass auf Transportebene zwischen Clients und Diensten für einen einzelnen Vorgang mehrere Nachrichten ausgetauscht werden können. Der Grund dafür kann das Infrastrukturverhalten sein, beispielsweise in Verbindung mit Sicherheitsfunktionen. Daher kann die Anzahl von ausgegebenen `MessageReceivedByTransport`-Ereignissen je nach Bindung des Diensts und seiner Konfiguration variieren.  
  
> [!NOTE]
>  Dieses Ereignis wird nicht bei unidirektionalen Transporten ausgegeben.  
  
## <a name="message"></a>Meldung  
 Der Transport hat eine Nachricht von '%1' empfangen.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Listen Address|`xs:string`|Die Adresse, die die Nachricht empfangen hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
