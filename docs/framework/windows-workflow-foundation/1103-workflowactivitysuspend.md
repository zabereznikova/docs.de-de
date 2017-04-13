---
title: "1103 - WorkflowActivitySuspend | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1103 - WorkflowActivitySuspend
## Eigenschaften  
  
|||  
|-|-|  
|ID|1103|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine Workflowaktivität unterbrochen wurde.  
  
## Meldung  
 WorkflowInstance\-ID: '%1' E2E\-Aktivität  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|WorkflowInstanceId|xs:string|Die Instanz\-ID für den Workflow.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|