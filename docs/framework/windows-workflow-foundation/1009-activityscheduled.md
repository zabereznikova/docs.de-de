---
title: "1009 - ActivityScheduled | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1009 - ActivityScheduled
## Eigenschaften  
  
|||  
|-|-|  
|ID|1009|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass die Ausführung einer Aktivität geplant wird.  
  
## Meldung  
 Die übergeordnete Aktivität '%1', DisplayName: '%2', InstanceId: '%3' hat die untergeordnete Aktivität '%4', DisplayName: '%5', InstanceId: '%6' geplant.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|ParentActivity|xs:string|Der Typname der übergeordneten Aktivität.|  
|ParentDisplayName|xs:string|Der Anzeigename der übergeordneten Aktivität.|  
|ParentInstanceId|xs:string|Die Instanz\-ID der übergeordneten Aktivität.|  
|ChildActivity|xs:string|Der Typname der untergeordneten Aktivität.|  
|ChildDisplayName|xs:string|Der Anzeigename der untergeordneten Aktivität.|  
|ChildInstanceId|xs:string|Die Instanz\-ID der geplanten untergeordneten Aktivität.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|