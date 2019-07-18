---
title: 111 - CustomTrackingRecordError
ms.date: 03/30/2017
ms.assetid: d469fb12-e094-4d6c-9b4d-abd7ce0d17da
ms.openlocfilehash: 737d48714020e20fc7b864de4e650ae234a8580e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009759"
---
# <a name="111---customtrackingrecorderror"></a>111 - CustomTrackingRecordError
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|111|  
|Schlüsselwörter|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz CustomTrackingRecord mit dem Grad "Fehler" ausgibt.  
  
## <a name="message"></a>Meldung  
 TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|Name|xs:string|Der Name des CustomTrackingRecord.|  
|ActivityName|xs:string|Der Name der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityId|xs:string|Die ID der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityInstanceId|xs:string|Die Instanz-ID der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|ActivityTypeName|xs:string|Der Name der Aktivität, die den CustomTrackingRecord ausgegeben hat.|  
|Daten|xs:string|Die Daten, die mit diesem Ereignis nachverfolgt wurden.  Die Werte werden gespeichert, in einem XML-Element im Format \<Elemente >\< Elementname = "DataName" Type = "> DataValue\</item > \< /items >.  Wenn keine Daten nachverfolgt wurden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem Sie die Anmerkungen ausgelassen, und ersetzen den Datenwert mit \<Elemente >...  \< /items >.  Die folgenden Typen werden als Wert gespeichert, wie Sie von ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime. zurückgegeben wurden.  Alle anderen Typen werden mit System.Runtime.Serialization.NetDataContractSerializer serialisiert.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden gespeichert, in einem XML-Element im Format \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.  Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch Ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName" Beispiel: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
