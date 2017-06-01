---
title: "4211 - QueuingSqlRetry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4211 - QueuingSqlRetry
## Eigenschaften  
  
|||  
|-|-|  
|ID|4211|  
|Schlüsselwörter|WFInstanceStore|  
|Ebene|Warnung|  
|Kanal|Microsoft\-Windows\-Application Server\-Applications\/Debug|  
  
## Beschreibung  
 Gibt an, dass eine SQL\-Wiederholung in die Warteschlange gestellt wird.  
  
## Meldung  
 SQL\-Wiederholung wird mit einer Verzögerung von %1 Millisekunden in die Warteschlange eingefügt.  
  
## Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|----------------------|---------------------|------------------|  
|Delay|xs:string|Die Verzögerung zwischen den Wiederholungen.|  
|AppDomain|xs:string|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|