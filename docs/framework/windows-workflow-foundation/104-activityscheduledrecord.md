---
title: 104 - ActivityScheduledRecord
ms.date: 03/30/2017
ms.assetid: ae202178-8fb1-4646-a3aa-18beeda8ff93
ms.openlocfilehash: b2c7cbd169053188d5e84a0b8afd87c4916c87cb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238963"
---
# <a name="104---activityscheduledrecord"></a>104 - ActivityScheduledRecord

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|104|  
|Keywords|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität in einer Workflowinstanz ActivityScheduledRecord ausgibt  
  
## <a name="message"></a>`Message`  

 TrackRecord = ActivityScheduledRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|Name|xs:string|Der Name der Aktivität, die die untergeordnete Aktivität geplant hat|  
|ActivityId|xs:string|Die ID der Aktivität, die die untergeordnete Aktivität geplant hat|  
|ActivityInstanceId|xs:string|Die Instanz-ID der Aktivität, die die untergeordnete Aktivität geplant hat|  
|ActivityTypeName|xs:string|Der Typ der Aktivität, die den Abbruchvorgang angefordert hat.|  
|ChildActivityName|xs:string|Der Name der geplanten Aktivität|  
|ChildActivityId|xs:string|Die ID der geplanten Aktivität|  
|ChildActivityInstanceId|xs:string|Die Instanz-ID der geplanten Aktivität|  
|ChildActivityTypeName|xs:string|Der Typ der geplanten Aktivität|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "annotationName" type="System.String"> annotationvalue gespeichert \</item> \</items> .  Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;Dienst Pfad für virtuelle Dienste&#124;Service Name" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
