---
title: "1041 - WorkflowApplicationPersistableIdle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1041 - WorkflowApplicationPersistableIdle
## Eigenschaften  
  
|||  
|-|-|  
|ID|1041|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine Workflowanwendung im Leerlauf ist und beibehalten werden kann.  Die Workflowanwendung bleibt im Leerlauf oder wird beibehalten.  
  
## Meldung  
 WorkflowApplication\-ID: '%1' ist im Leerlauf und dauerhaft. Die folgende Aktion wird ausgeführt: %2.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|WorkflowApplicationId|xs:string|Die Workflowanwendungs\-ID|  
|ActionTaken|xs:string|Die Aktion, die für die Workflowanwendung ausgeführt wird.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|