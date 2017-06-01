---
title: "202 - ClientMessageInspectorBeforeSendInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 202 - ClientMessageInspectorBeforeSendInvoked
## Eigenschaften  
  
|||  
|-|-|  
|ID|202|  
|Schlüsselwörter|Troubleshooting, ServiceModel|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeSendRequest`\-Methode auf einem Clientmeldungsinspektor aufgerufen hat.  
  
## Meldung  
 Der Verteiler hat 'BeforeSendRequest' auf einem ClientMessageInspector des Typs '%1' aufgerufen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|TypeName|`xs:string`|Der CLR\-FullName für den Typ des aufgerufenen Inspektors.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als 'Websitename Virtueller Pfad der Anwendung&#124;Virtueller Pfad des Diensts&#124;ServiceName' definiert.Beispiel: 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|