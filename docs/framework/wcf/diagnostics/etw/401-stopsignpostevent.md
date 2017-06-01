---
title: "401- StopSignPostEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 401- StopSignPostEvent
## Eigenschaften  
  
|||  
|-|-|  
|ID|401|  
|Schlüsselwörter|Problembehandlung|  
|Ebene|Information|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Dieses Ereignis kennzeichnet das Ende einer End\-to\-End\-Aktivität.  Enthält den Namen der Aktivität.  
  
## Meldung  
 Aktivitätsgrenze.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Extended Data|`xs:string`|Der Name der Aktivität.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|