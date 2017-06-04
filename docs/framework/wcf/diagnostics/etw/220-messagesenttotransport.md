---
title: "220 - MessageSentToTransport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 220 - MessageSentToTransport
## Eigenschaften  
  
|||  
|-|-|  
|ID|220|  
|Schlüsselwörter|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn das Dienstmodell eine Nachricht an den Transport sendet.  
  
> [!NOTE]
>  Dieses Ereignis wird nicht für unidirektionale Transporte ausgegeben.  
  
## Meldung  
 Der Verteiler hat eine Nachricht an den Transport gesendet.Korrelations\-ID \=\= '%1'.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Correlation ID|`xs:GUID`|Die Aktivitäts\-ID, die verwendet wurde, um für ein `MessageSentToTransport`\-Ereignis eine Korrelation zum entsprechenden `MessageReceivedFromTransport`\-Objekt zu erstellen.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|