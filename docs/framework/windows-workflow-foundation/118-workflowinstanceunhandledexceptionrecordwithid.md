---
title: 118 - WorkflowInstanceUnhandledExceptionRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ce4b193-e141-4cc4-86a3-2e8c984c110d
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d5449a619138d136fe4150bef99c682f156fd245
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="118---workflowinstanceunhandledexceptionrecordwithid"></a>118 - WorkflowInstanceUnhandledExceptionRecordWithId
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|118|  
|Schlüsselwörter|HealthMonitoring, WFTracking|  
|Ebene|Fehler|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz WorkflowInstanceUnhandledExceptionRecord ausgibt.  
  
## <a name="message"></a>Meldung  
 TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName = %8, Exception = %9, Annotations = % 10, ProfileName = % 11, WorkflowDefinitionIdentity = %12  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|ActivityDefinitionId|xs:string|Der Name der Stammaktivität im Workflow.|  
|SourceName|xs:string|Der Name der Quellaktivität, die zu einem Fehler und der unhandledException geführt hat|  
|SourceId|xs:string|Die Aktivitäts-ID der fehlerhaften Quellaktivität|  
|SourceInstanceId|xs:string|Die Aktivitätsinstanz-ID der fehlerhaften Quellaktivität|  
|SourceTypeName|xs:string|Der Name des Quellaktivitätstyps, die zu einem Fehler und der unhandledException geführt hat|  
|Ausnahme|xs:string|Die Ausnahmedetails der nicht behandelten Ausnahme|  
|Zustand|xs:string|Der aktuelle Zustand des Workflows.|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden. Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >. Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|WorkflowDefinitionIdentity|xs:string|Die ID der Workflowdefinition.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
