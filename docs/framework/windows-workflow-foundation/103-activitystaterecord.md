---
title: 103 - ActivityStateRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60dff5365ea98d767a271998a2de9fe3b1aae591
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="103---activitystaterecord"></a>103 - ActivityStateRecord
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|103|  
|Schlüsselwörter|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz ActivityStateRecord ausgibt  
  
## <a name="message"></a>Meldung  
 TrackRecord = ActivityStateRecord, INSTANCEID =% 1, RecordNumber=%2, EventTime=%3, Zustand =% 4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName =% 12  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|Zustand|xs:string|Der Zustand der Aktivität|  
|Name|xs:string|Der Anzeigename der Aktivität, die das Ereignis ausgegeben hat.|  
|ActivityId|xs:string|Die Aktivitäts-ID der ausgebenden Aktivität|  
|ActivityInstanceId|xs:string|Die Aktivitätsinstanz-ID der ausgebenden Aktivität|  
|ActivityTypeName|xs:string|Der Typname der ausgebenden Aktivität|  
|Argumente|xs:string|Die Argumente, die mit diesem Ereignis nachverfolgt wurden.  Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "ArgumentName" Type = "> ArgumentValue\</item > \< /items >.  Wenn keine Argumente nachverfolgt wurden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.  Die folgenden Typen werden als Wert gespeichert, wie Sie von ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime. zurückgegeben wurden.  Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Variablen|xs:string|Die Variablen, die mit diesem Ereignis nachverfolgt wurden.  Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "VariableName" Type = "> VariableValue\</item > \< /items >.  Wenn keine Variablen nachverfolgt wurden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und ersetzen den Wert der Variablen mit \<Elemente >...  \< /items >.  Die folgenden Typen werden als Wert gespeichert, wie Sie von ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime. zurückgegeben wurden.  Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.  Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName "Beispiel:" Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
