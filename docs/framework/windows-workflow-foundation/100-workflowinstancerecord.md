---
title: "100 - WorkflowInstanceRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed4d1851-b378-489b-a22d-c1db09571fb4
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 100 - WorkflowInstanceRecord
## Eigenschaften  
  
|||  
|-|-|  
|ID|100|  
|Schlüsselwörter|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird vom ETW\-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz für Workflowzustände "WorkflowInstanceRecord" ausgibt: Started \(Gestartet\), Resumed \(Wiederaufgenommen\), Persisted \(Beibehalten\), Idle \(Im Leerlauf\), Deleted \(Gelöscht\), Completed \(Abgeschlossen\), Canceled \(Abgebrochen\), Unloaded \(Entladen\), Unsuspended \(Fortgesetzt\).  
  
## Meldung  
 TrackRecord\= WorkflowInstanceRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, State \= %5, Annotations \= %6, ProfileName \= %7  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InstanceId|xs:GUID|Die Instanz\-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|ActivityDefinitionId|xs:string|Der Name der Stammaktivität im Workflow.|  
|State|xs:string|Der aktuelle Zustand des Workflows.|  
|Annotations|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> gespeichert.Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch \<items\>...\<\/items\> ersetzt wird.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als "Virtueller Anwendungspfad des Websitenamens &#124; Virtueller Dienstpfad &#124; Servicename" definiert. Beispiel: "Standardwebsite\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService".|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|