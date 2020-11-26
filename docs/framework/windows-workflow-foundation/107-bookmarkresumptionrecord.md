---
title: 107 -- BookmarkResumptionRecord
ms.date: 03/30/2017
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
ms.openlocfilehash: 14557ef2726a60bcde49d30f9d6168fd831e613c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238859"
---
# <a name="107----bookmarkresumptionrecord"></a>107 -- BookmarkResumptionRecord

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|107|  
|Keywords|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Information|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Workflowinstanz einen BookmarkResumptionRecord ausgibt.  
  
## <a name="message"></a>`Message`  

 TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5, OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
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
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "annotationName" type="System.String"> annotationvalue gespeichert \</item> \</items> .  Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;Dienst Pfad für virtuelle Dienste&#124;Service Name" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
