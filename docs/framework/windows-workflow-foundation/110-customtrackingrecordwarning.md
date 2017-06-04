---
title: "110 - CustomTrackingRecordWarning | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3bc093de-be47-4ed0-983f-05b4246446fc
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 110 - CustomTrackingRecordWarning
## Eigenschaften  
  
|||  
|-|-|  
|Id|110|  
|Schlüsselwörter|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Grad|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird vom ETW\-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz CustomTrackingRecord auf der Ebene einer Warnung ausgibt  
  
## Meldung  
 TrackRecord \= CustomTrackingRecord, InstanceID \= %1, RecordNumber\=%2, EventTime\=%3, Name\=%4, ActivityName\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Data\=%9, Annotations\=%10, ProfileName \= %11  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InstanceId|xs:GUID|Die Instanz\-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|Name|xs:string|Der Name des CustomTrackingRecord.|  
|ActivityName|xs:string|Der Name der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityId|xs:string|Die ID der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityInstanceId|xs:string|Die Instanz\-ID der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityTypeName|xs:string|Der Name der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|Data|xs:string|Die Daten, die mit diesem Ereignis nachverfolgt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "dataName" type\="System.String"\>dataValue\<\/item\>\<\/items\> gespeichert.Wenn keine Daten nachverfolgt wurden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Datenwert durch \<items\>...\<\/items\> ersetzt wird.Die folgenden Typen werden als Wert gespeichert, wie sie von ToString\(\); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime. zurückgegeben wurden.Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Annotations|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> gespeichert.Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch \<items\>...\<\/items\> ersetzt wird.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Sein Format wird als 'Virtueller Anwendungspfad des Websitenamens &#124; Virtueller Dienstpfad &#124; Servicename' definiert. Beispiel: 'Standardwebsite\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|