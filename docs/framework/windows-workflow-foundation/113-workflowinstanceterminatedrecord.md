---
title: 113 - WorkflowInstanceTerminatedRecord
ms.date: 03/30/2017
ms.assetid: f53204ee-4ea2-45e1-8859-e86d07305efd
ms.openlocfilehash: 780841e50763d313debbfea6b84f7c6f412b5590
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294195"
---
# <a name="113---workflowinstanceterminatedrecord"></a>113 - WorkflowInstanceTerminatedRecord

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|113|  
|Keywords|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz WorkflowInstanceTerminatedRecord ausgibt.  
  
## <a name="message"></a>`Message`  

 TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|ActivityDefinitionId|xs:string|Der Name der Stammaktivität im Workflow.|  
|`Reason`|xs:string|Der Grund, aus dem der Workflow beendet wurde.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "annotationName" type="System.String"> annotationvalue gespeichert \</item> \</items> .  Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;Dienst Pfad für virtuelle Dienste&#124;Service Name" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
