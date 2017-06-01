---
title: "223 - OperationFaulted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 223 - OperationFaulted
## Eigenschaften  
  
|||  
|-|-|  
|ID|223|  
|Schlüsselwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Grad|Warning|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn beim Aufrufen der Methode der standardmäßige `OperationInvoker` des Dienstmodells auf eine Ausnahme gestoßen ist, die von `FaultException` abgeleitet ist.  
  
## Meldung  
 Die '%1'\-Methode hat beim Aufrufen von OperationInvoker eine FaultException ausgelöst.Die Methodenaufrufdauer betrug '%2' ms.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|MethodName|`xs:string`|Der CLR\-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.|  
|Duration|`xs:long`|Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|