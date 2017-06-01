---
title: "1015 - StartCompletionWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1015 - StartCompletionWorkItem
## Eigenschaften  
  
|||  
|-|-|  
|ID|1015|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass ein CompletionWorkItem mit der Ausführung beginnt.  
  
## Meldung  
 Die Ausführung einer CompletionWorkItem für die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wird gestartet.  Abgeschlossene Aktivität '%4', DisplayName: '%5', InstanceId: '%6'.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|ParentActivity|xs:string|Der Typname der übergeordneten Aktivität.|  
|ParentDisplayName|xs:string|Der Anzeigename der übergeordneten Aktivität.|  
|ParentInstanceId|xs:string|Die Instanz\-ID der übergeordneten Aktivität.|  
|CompletedActivity|xs:string|Der Typname der abgeschlossenen Aktivität.|  
|CompletedActivityDisplayName|xs:string|Der Anzeigename der abgeschlossenen Aktivität.|  
|CompletedActivityInstanceId|xs:string|Die Instanz\-ID der abgeschlossenen Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|