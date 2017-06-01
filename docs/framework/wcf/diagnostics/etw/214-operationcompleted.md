---
title: "214 - OperationCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 214 - OperationCompleted
## Eigenschaften  
  
|||  
|-|-|  
|ID|214|  
|Schlüsselwörter|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn der standardmäßige `OperationInvoker` des Dienstmodells das Aufrufen einer Methode abgeschlossen hat, ohne dass diese Methode eine Ausnahme auslöst.  
  
## Meldung  
 Ein OperationInvoker hat den Aufruf der '%1'\-Methode abgeschlossen.Die Methodenaufrufdauer betrug '%2' ms.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Method Name|`xs:string`|Der CLR\-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.|  
|Duration|`xs:long`|Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|