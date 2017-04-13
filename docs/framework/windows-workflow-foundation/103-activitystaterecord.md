---
title: "103 - ActivityStateRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 103 - ActivityStateRecord
## Eigenschaften  
  
|||  
|-|-|  
|Id|103|  
|Schlüsselwörter|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Grad|Informationen|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis wird vom ETW\-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz ActivityStateRecord ausgibt  
  
## Meldung  
 TrackRecord \= ActivityStateRecord, INSTANCEID \=% 1, RecordNumber\=%2, EventTime\=%3, Zustand \=% 4, Name\=%5, ActivityId\=%6, ActivityInstanceId\=%7, ActivityTypeName\=%8, Arguments\=%9, Variables\=%10, Annotations\=%11, ProfileName \=% 12  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|InstanceId|xs:GUID|Die Instanz\-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|State|xs:string|Der Zustand der Aktivität|  
|Name|xs:string|Der Anzeigename der Aktivität, die das Ereignis ausgegeben hat.|  
|ActivityId|xs:string|Die Aktivitäts\-ID der ausgebenden Aktivität|  
|ActivityInstanceId|xs:string|Die Aktivitätsinstanz\-ID der ausgebenden Aktivität|  
|ActivityTypeName|xs:string|Der Typname der ausgebenden Aktivität|  
|Argumente|xs:string|Die Argumente, die mit diesem Ereignis nachverfolgt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "argumentName" type\="System.String"\>argumentValue\<\/item\>\<\/items\> gespeichert.Wenn keine Argumente nachverfolgt wurden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch \<items\>...\<\/items\> ersetzt wird.Die folgenden Typen werden als Wert gespeichert, wie Sie von ToString\(\); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime. zurückgegeben wurden.Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Variablen|xs:string|Die Variablen, die mit diesem Ereignis nachverfolgt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "variableName" type\="System.String"\>variableValue\<\/item\>\<\/items\>.Wenn keine Variablen nachverfolgt wurden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und die Variablen durch \<items\>...\<\/items\> ersetzt werden.Die folgenden Typen werden als Wert gespeichert, wie Sie von ToString\(\); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime. zurückgegeben wurden.Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Annotations|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.Die Werte werden in einem XML\-Element im Format \<items\>\< item  name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> gespeichert.Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items\/\>.Die ETW\-Ereignisgröße wird von der ETW\-Puffergröße oder der maximalen Nutzlast für ein ETW\-Ereignis beschränkt.Wenn die Größe des Ereignisses die ETW\-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch \<items\>...\<\/items\> ersetzt wird.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.Das Format ist als "Virtueller Anwendungspfad des Websitenamens &#124; Virtueller Dienstpfad &#124; Servicename" definiert. Beispiel: "Standardwebsite\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService".|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|