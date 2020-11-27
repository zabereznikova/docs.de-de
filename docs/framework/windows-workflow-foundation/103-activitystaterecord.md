---
title: 103 - ActivityStateRecord
ms.date: 03/30/2017
ms.assetid: 57636a9a-561e-44aa-aef9-1f1894aaa6dd
ms.openlocfilehash: 02c33f02b7650c9f9b7527c319de3b58980fdd6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275075"
---
# <a name="103---activitystaterecord"></a>103 - ActivityStateRecord

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|103|  
|Keywords|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz ActivityStateRecord ausgibt  
  
## <a name="message"></a>`Message`  

 TrackRecord = ActivityStateRecord, INSTANCEID =% 1, RecordNumber=%2, EventTime=%3, Zustand =% 4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName =% 12  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|State|xs:string|Der Zustand der Aktivität|  
|Name|xs:string|Der Anzeigename der Aktivität, die das Ereignis ausgegeben hat.|  
|ActivityId|xs:string|Die Aktivitäts-ID der ausgebenden Aktivität|  
|ActivityInstanceId|xs:string|Die Aktivitätsinstanz-ID der ausgebenden Aktivität|  
|ActivityTypeName|xs:string|Der Typname der ausgebenden Aktivität|  
|Argumente|xs:string|Die Argumente, die mit diesem Ereignis nachverfolgt wurden.  Die Werte werden in einem XML-Element im Format Argument \<items> \< item  name = "argumentName" type="System.String"> value gespeichert \</item> \</items> .  Wenn keine Argumente nachverfolgt wurden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .  Die folgenden Typen werden als Wert gespeichert, wie von ToString () zurückgegeben. String, Char, bool, int, Short, Long, uint, ushort, ULONG, System. Single, float, Double, System. Guid, System. DateTimeOffset, System. DateTime.  Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Variablen|xs:string|Die Variablen, die mit diesem Ereignis nachverfolgt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "variableName" type="System.String"> VariableValue gespeichert \</item> \</items> .  Wenn keine Variablen nachverfolgt wurden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Variablen Wert durch \<items> ... ersetzt wird \</items> .  Die folgenden Typen werden als Wert gespeichert, wie von ToString () zurückgegeben. String, Char, bool, int, Short, Long, uint, ushort, ULONG, System. Single, float, Double, System. Guid, System. DateTimeOffset, System. DateTime.  Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "annotationName" type="System.String"> annotationvalue gespeichert \</item> \</items> .  Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;Dienst Pfad für virtuelle Dienste&#124;Service Name" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
