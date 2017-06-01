---
title: "101 - WorkflowInstanceUnhandledExceptionRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab7d50a0-5347-4390-8445-1def4dfdff6a
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 101 - WorkflowInstanceUnhandledExceptionRecord
## Eigenschaften  
  
|||  
|-|-|  
|Id|101|  
|Schlüsselwörter|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Grad|Fehler|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird vom ETW\-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz WorkflowInstanceUnhandledExceptionRecord ausgibt.  
  
## Meldung  
 TrackRecord \= WorkflowInstanceUnhandledExceptionRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, SourceName \= %5, SourceId \= %6, SourceInstanceId \= %7, SourceTypeName\=%8, Exception\=%9, Annotations\= %10, ProfileName \= %11  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InstanceId|xs:GUID|Die Instanz\-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|ActivityDefinitionId|xs:string|Der Name der Stammaktivität im Workflow|  
|SourceName|xs:string|Der Name der Quellaktivität, die zu einem Fehler und der unhandledException geführt hat|  
|SourceId|xs:string|Die Aktivitäts\-ID der fehlerhaften Quellaktivität|  
|SourceInstanceId|xs:string|Die Aktivitätsinstanz\-ID der fehlerhaften Quellaktivität|  
|SourceTypeName|xs:string|Der Name des Quellaktivitätstyps, die zu einem Fehler und der unhandledException geführt hat|  
|Exception|xs:string|Die Ausnahmedetails der nicht behandelten Ausnahme|  
|Annotations|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> gespeichert.Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch \<items\>...\<\/items\> ersetzt wird.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Sein Format wird als 'Virtueller Anwendungspfad des Websitenamens &#124; Virtueller Dienstpfad &#124; Servicename' definiert. Beispiel: 'Standardwebsite\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|