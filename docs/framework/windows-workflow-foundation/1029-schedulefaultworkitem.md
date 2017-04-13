---
title: "1029 - ScheduleFaultWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1029 - ScheduleFaultWorkItem
## Eigenschaften  
  
|||  
|-|-|  
|ID|1029|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass ein FaultWorkItem geplant wurde.  
  
## Meldung  
 Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde FaultWorkItem geplant. Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|FaultActivity|xs:string|Der Typname der fault\-Aktivität.|  
|FaultActivityDisplayName|xs:string|Der Anzeigename der fault\-Aktivität.|  
|FaultActivityInstanceId|xs:string|Die Instanz\-ID der fault\-Aktivität.|  
|ExceptionActivity|xs:string|Der Typname der Aktivität, die die Ausnahme ausgelöst hat.|  
|ExceptionActivityDisplayName|xs:string|Der Anzeigename der Aktivität, die die Ausnahme ausgelöst hat.|  
|ExceptionActivityInstanceId|xs:string|Die Instanz\-ID der Aktivität, die die Ausnahme ausgelöst hat.|  
|Ausnahme|xs:string|Die Ausnahmedetails der Ausnahme.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|