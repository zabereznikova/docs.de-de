---
title: 110 - CustomTrackingRecordWarning
ms.date: 03/30/2017
ms.assetid: 3bc093de-be47-4ed0-983f-05b4246446fc
ms.openlocfilehash: 8fced5fe4baabac34b25b9a00421c3ded1c83ca6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238768"
---
# <a name="110---customtrackingrecordwarning"></a>110 - CustomTrackingRecordWarning

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|110|  
|Keywords|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz CustomTrackingRecord auf der Ebene einer Warnung ausgibt  
  
## <a name="message"></a>`Message`  

 TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|Name|xs:string|Der Name des CustomTrackingRecord.|  
|ActivityName|xs:string|Der Name der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityId|xs:string|Die ID der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityInstanceId|xs:string|Die Instanz-ID der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityTypeName|xs:string|Der Name der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|Daten|xs:string|Die Daten, die mit diesem Ereignis nachverfolgt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "dataName" type="System.String"> DataValue gespeichert \</item> \</items> .  Wenn keine Daten nachverfolgt wurden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Datenwert durch \<items> ... ersetzt wird \</items> .  Die folgenden Typen werden als Wert gespeichert, wie von ToString () zurückgegeben. String, Char, bool, int, Short, Long, uint, ushort, ULONG, System. Single, float, Double, System. Guid, System. DateTimeOffset, System. DateTime.  Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "annotationName" type="System.String"> annotationvalue gespeichert \</item> \</items> .  Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;virtuellen Dienst Pfad&#124;Service Name" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
