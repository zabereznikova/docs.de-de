---
title: "215 - MessageReceivedByTransport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 215 - MessageReceivedByTransport
## Eigenschaften  
  
|||  
|-|-|  
|ID|215|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis tritt auf, wenn ein TCP\-basierter Transport eine Nachricht empfängt.  Beachten Sie, dass auf Transportebene zwischen Clients und Diensten für einen einzelnen Vorgang mehrere Nachrichten ausgetauscht werden können.  Der Grund dafür kann das Infrastrukturverhalten sein, beispielsweise in Verbindung mit Sicherheitsfunktionen.  Daher kann die Anzahl von ausgegebenen `MessageReceivedByTransport`\-Ereignissen je nach Bindung des Diensts und seiner Konfiguration variieren.  
  
> [!NOTE]
>  Dieses Ereignis wird nicht bei unidirektionalen Transporten ausgegeben.  
  
## Meldung  
 Der Transport hat eine Nachricht von '%1' empfangen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Listen Address|`xs:string`|Die Adresse, die die Nachricht empfangen hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.  Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|