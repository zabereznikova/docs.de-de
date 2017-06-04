---
title: "57398 - MaxInstancesExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 57398 - MaxInstancesExceeded
## Eigenschaften  
  
|||  
|-|-|  
|ID|57398|  
|Schlüsselwörter|WFServices|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Analytic|  
  
## Beschreibung  
 Gibt an, dass das System die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht hat.  
  
## Meldung  
 Das System hat die für "MaxConcurrentInstances" festgelegte Drosselungsgrenze erreicht.  Die Grenze für diese Drosselung war auf %1 festgelegt.  Der Drosselungswert kann geändert werden, indem das Attribut "maxConcurrentInstances" im serviceThrottle\-Element oder die "MaxConcurrentInstances"\-Eigenschaft im Verhalten "ServiceThrottlingBehavior" geändert wird.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Name|xs:string|Name des Elements.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|