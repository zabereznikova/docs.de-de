---
title: "203 - ClientParameterInspectorAfterCallInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 203 - ClientParameterInspectorAfterCallInvoked
## Eigenschaften  
  
|||  
|-|-|  
|ID|203|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`\-Methode auf einem Clientparameterinspektor aufgerufen hat.  
  
## Meldung  
 Der Verteiler hat 'AfterCall' auf einem ClientParameterInspector vom Typ '%1' aufgerufen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|TypeName|`xs:string`|Der CLR\-FullName für den Typ des aufgerufenen Inspektors.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.  Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|