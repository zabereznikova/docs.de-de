---
title: 107 -- BookmarkResumptionRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa2d37ed-2bfa-439b-89e8-a9354027f155
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8d3effb662ec2994351e1de7975b8ce2737c5ef0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
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
|Anmerkungen|xs:string|Die Anmerkungen, die diesem Ereignis hinzugefügt wurden.  Die Werte werden in einem XML-Element im Format gespeichert \<Elemente >\< Elementname = "AnnotationName" Type = "> AnnotationValue\</item > \< /items >.  Wenn keine Anmerkungen angegeben werden, die Zeichenfolge enthält \<Elemente / >. Die ETW-Ereignisgröße wird von der ETW-Puffergröße oder der maximalen Nutzlast für ein ETW-Ereignis beschränkt. Wenn die Größe des Ereignisses die ETW-Beschränkung überschreitet, und klicken Sie dann das Ereignis abgeschnitten, indem die Anmerkungen ausgelassen und der Anmerkungswert mit ersetzen \<Elemente >...  \< /items >.|  
|ProfileName|xs:string|Der Name oder das Überwachungsprofil, das zur Ausgabe dieses Ereignisses geführt hat.|  
|HostReference|xs:string|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.  Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName "Beispiel:" Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
