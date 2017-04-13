---
title: "205 - OperationInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 205 - OperationInvoked
## Eigenschaften  
  
|||  
|-|-|  
|ID|205|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird unmittelbar vor dem Vorgang ausgegeben, bei dem der standardmäßige `OperationInvoker` des Dienstmodells mit dem Aufrufen einer Methode beginnt.  
  
## Meldung  
 Ein OperationInvoker hat die '%1'\-Methode aufgerufen.Aufruferdaten: '%2'.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Methodenname|`xs:string`|Der CLR\-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.|  
|Aufruferdaten|`xs:string`|Die IP\-Adresse und die Portnummer des Clients im Format 'IPAddress:PortNumber'.Diese beiden Werte werden aus der 'System.ServiceModel.Channels.RemoteEndpointMessageProperty'\-Meldungseigenschaft im Vorgangskontext abgerufen.Beachten Sie, dass dieser Wert für Nicht\-TCP\-Bindungen `null` ist.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|