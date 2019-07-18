---
title: 113 - WorkflowInstanceTerminatedRecord
ms.date: 03/30/2017
ms.assetid: f53204ee-4ea2-45e1-8859-e86d07305efd
ms.openlocfilehash: e6ea25de7ceea33ca1e552c12545525bbc17f198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924227"
---
# <a name="113---workflowinstanceterminatedrecord"></a>113 - WorkflowInstanceTerminatedRecord
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|113|  
|Schlüsselwörter|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz WorkflowInstanceTerminatedRecord ausgibt.  
  
## <a name="message"></a>Meldung  
 TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|ActivityDefinitionId|xs:string|Der Name der Stammaktivität im Workflow.|  
|Grund|xs:string|Der Grund, aus dem der Workflow beendet wurde.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden gespeichert, in einem XML-Element im Format \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.  Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch Ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName" Beispiel: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
