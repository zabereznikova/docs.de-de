---
title: "1031 - CompleteFaultWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1031 - CompleteFaultWorkItem
## Eigenschaften  
  
|||  
|-|-|  
|ID|1031|  
|Schlüsselwörter|WFRuntime|  
|Ebene|Ausführlich|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass ein FaultWorkItem abgeschlossen wurde.  
  
## Meldung  
 Für die Aktivität '%1', DisplayName: '%2', InstanceId: '%3' wurde ein FaultWorkItem abgeschlossen.  Die Ausnahme wurde von der Aktivität '%4', DisplayName: '%5', InstanceId: '%6' propagiert.  
  
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