---
title: "207 - FaultProviderInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 207 - FaultProviderInvoked
## Eigenschaften  
  
|||  
|-|-|  
|ID|207|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, nachdem ein `FaultProvider` aufgerufen wurde.  
  
## Meldung  
 Der Verteiler hat einen FaultProvider vom Typ '%1' mit einer Ausnahme vom Typ '%2' aufgerufen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|TypeName|`xs:string`|Der CLR\-FullName des aufgerufenen `FaultProvider`\-Typs.|  
|ExceptionTypeName|`xs:string`|Der CLR\-FullName der Ausnahme, die der `FaultProvider` verarbeitet hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.  Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|