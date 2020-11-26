---
title: 105 - FaultPropagationRecord
ms.date: 03/30/2017
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
ms.openlocfilehash: 3390a77f16cc52e52ea1b3e4c1a34d0f44795abb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238911"
---
# <a name="105---faultpropagationrecord"></a>105 - FaultPropagationRecord

## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|105|  
|Keywords|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität der Workflowinstanz FaultPropagationRecord ausgibt.  
  
## <a name="message"></a>`Message`  

 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|BESCHREIBUNG|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|Die Instanz-ID für den Workflow.|  
|RecordNumber|xs:long|Die Sequenznummer des ausgegebenen Datensatzes.|  
|EventTime|xs:dateTime|Die Zeit in UTC, als das Ereignis ausgegeben wurde.|  
|FaultSourceActivityName|xs:string|Der Name der Aktivität, die den Fehler ausgegeben hat|  
|FaultSourceActivityId|xs:string|Die ID der Aktivität, die den Fehler ausgegeben hat|  
|FaultSourceActivityInstanceId|xs:string|Die Instanz-ID der Aktivität, die den Fehler ausgegeben hat|  
|FaultSourceActivityTypeName|xs:string|Der Typ der Aktivität, die den Fehler ausgegeben hat|  
|FaultHandlerActivityName|xs:string|Der Anzeigename der Fehlerhandleraktivität|  
|FaultHandlerActivityId|xs:string|Die ID der Fehlerhandleraktivität|  
|FaultHandlerActivityInstanceId|xs:string|Die Instanz-ID der Fehlerhandleraktivität|  
|FaultHandlerActivityTypeName|xs:string|Der Typ der Fehlerhandleraktivität|  
|Fehler|xs:string|Die Fehlerdetails|  
|IsFaultSource|xs:unsignedByte|Gibt an, ob das Ereignis von der Fehlerquelle ausgegeben wurde|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format \<items> \< item  name = "annotationName" type="System.String"> annotationvalue gespeichert \</item> \</items> .  Wenn keine Anmerkungen angegeben werden, enthält die Zeichenfolge \<items/> . Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Limits überschreitet, wird das Ereignis abgeschnitten, indem die Anmerkungen gelöscht und der Anmerkung-Wert durch \<items> ... ersetzt wird \</items> .|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Sein Format ist als "Website Name Anwendungspfad für virtuelle Computer&#124;Dienst Pfad für virtuelle Dienste&#124;Service Name" definiert. Beispiel: "Default Web Site/calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
