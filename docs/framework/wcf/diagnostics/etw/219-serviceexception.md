---
title: "219 - ServiceException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 219 - ServiceException
## Eigenschaften  
  
|||  
|-|-|  
|ID|219|  
|Schlüsselwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Grad|Error|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn in einem WCF\-Dienst eine nicht behandelte Ausnahme auftritt.Dies schließt nicht behandelte Ausnahmen während der Aktivierung, während der Meldungsverarbeitung und im Benutzercode ein.  
  
## Meldung  
 Während der Meldungsverarbeitung ist eine nicht behandelte Ausnahme vom Typ '%2' aufgetreten.Vollständige Ausnahme ToString: %1.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|ExceptionToString|`xs:string`|Das Ergebnis des Aufrufens von `ToString`\(\) für die CLR\-Ausnahme.|  
|ExceptionTypeName|`xs:string`|Der CLR\-FullName des Ausnahmetyps.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|