---
title: "1006 - WorkflowApplicationUnhandledException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1006 - WorkflowApplicationUnhandledException
## Eigenschaften  
  
|||  
|-|-|  
|ID|1006|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Fehler|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass in einer Workflowanwendung eine nicht behandelte Ausnahme aufgetreten ist.  
  
## Meldung  
 WorkflowInstance\-ID: '%1' hat eine nicht behandelte Ausnahme erkannt. Die Ausnahme stammt aus Aktivität '%2', DisplayName: '%3'. Die folgende Aktion wird ausgeführt: %4.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|WorkflowInstanceId|`xs:string`|Die Instanz\-ID für den Workflow.|  
|Ausnahme|`xs:string`|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|