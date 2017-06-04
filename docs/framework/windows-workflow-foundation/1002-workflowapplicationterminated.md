---
title: "1002 - WorkflowApplicationTerminated | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 1002 - WorkflowApplicationTerminated
## Eigenschaften  
  
|||  
|-|-|  
|ID|1002|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine Workflowanwendung im Faulted\-Zustand einer Ausnahme beendet wurde.  
  
## Meldung  
 WorkflowApplication\-ID: '%1' wurde beendet.  Sie wurde im Faulted\-Status mit einer Ausnahme abgeschlossen.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|WorkflowApplicationId|`xs:string`|Die Workflowanwendungs\-ID|  
|Ausnahme|`xs:string`|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|