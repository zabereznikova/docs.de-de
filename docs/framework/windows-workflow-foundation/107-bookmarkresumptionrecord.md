---
title: "107 -- BookmarkResumptionRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 107 -- BookmarkResumptionRecord
## Eigenschaften  
  
|||  
|-|-|  
|Id|107|  
|Schlüsselwörter|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird vom ETW\-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz einen BookmarkResumptionRecord ausgibt.  
  
## Meldung  
 TrackRecord \= BookmarkResumptionRecord, InstanceID\=%1, RecordNumber\=%2,EventTime\=%3, Name\=%4, SubInstanceID\=%5,  OwnerActivityName\=%6, OwnerActivityId \=%7, OwnerActivityInstanceId\=%8, OwnerActivityTypeName\=%9, Annotations\=%10, ProfileName \= %11  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InstanceId|xs:GUID|Die Instanz\-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde|  
|Name|xs:string|Der Name des Lesezeichens, das fortgesetzt wurde.|  
|SubInstanceID|xs:GUID|Die ID des Lesezeichenbereichs|  
|OwnerActivityName|xs:string|Der Name der Lesezeichenaktivität.|  
|OwnerActivityId|xs:string|Die ID der Lesezeichenaktivität.|  
|OwnerActivityInstanceId|xs:string|Die Instanz\-ID der Lesezeichenaktivität|  
|OwnerActivityTypeName|xs:string|Der Typ der Lesezeichenaktivität|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> gespeichert.Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch \<items\>...\<\/items\> ersetzt wird.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als "Virtueller Anwendungspfad des Websitenamens &#124; Virtueller Dienstpfad &#124; Servicename" definiert. Beispiel: "Standardwebsite\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService".|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|