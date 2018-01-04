---
title: 105 - FaultPropagationRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec9de51055812083430d9bcee780818187be04da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="105---faultpropagationrecord"></a>105 - FaultPropagationRecord
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|Id|105|  
|Schlüsselwörter|EndToEndMonitoring, Problembehandlung, HealthMonitoring, WFTracking|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird vom ETW-Überwachungsteilnehmer ausgegeben, wenn eine Aktivität der Workflowinstanz FaultPropagationRecord ausgibt.  
  
## <a name="message"></a>Meldung  
 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
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
|Fault|xs:string|Die Fehlerdetails|  
|IsFaultSource|xs:unsignedByte|Gibt an, ob das Ereignis von der Fehlerquelle ausgegeben wurde|  
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.  Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName "Beispiel:" Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
