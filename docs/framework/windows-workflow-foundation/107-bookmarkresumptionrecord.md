---
title: 107 -- BookmarkResumptionRecord
ms.date: 03/30/2017
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
ms.openlocfilehash: 860ed7cc065a862d100b0a8c6a88458e61930b9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052845"
---
# <a name="107----bookmarkresumptionrecord"></a>107 -- BookmarkResumptionRecord
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|107|  
|Schlüsselwörter|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz einen BookmarkResumptionRecord ausgibt.  
  
## <a name="message"></a>Meldung  
 TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5, OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|Name|xs:string|Der Name des Lesezeichens, das fortgesetzt wurde.|  
|SubInstanceID|xs:GUID|Die ID des Lesezeichenbereichs|  
|OwnerActivityName|xs:string|Der Name der Lesezeichenaktivität.|  
|OwnerActivityId|xs:string|Die ID der Lesezeichenaktivität.|  
|OwnerActivityInstanceId|xs:string|Die Instanz-ID der Lesezeichenaktivität|  
|OwnerActivityTypeName|xs:string|Der Typ der Lesezeichenaktivität|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden gespeichert, in einem XML-Element im Format \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.  Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert durch Ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist definiert als "Website Namen virtueller Anwendungspfad&#124;virtueller Dienstpfad&#124;ServiceName" Beispiel: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
