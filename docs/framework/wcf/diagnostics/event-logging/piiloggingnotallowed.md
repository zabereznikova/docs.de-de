---
title: "PiiLoggingNotAllowed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# PiiLoggingNotAllowed
ID: 108  
  
 Schweregrad: Fehler  
  
 Kategorie: Ablaufverfolgung  
  
## Beschreibung  
 Dieses Ereignis gibt an, dass keine bekannten PII protokolliert werden.  Das Protokollieren bekannter PII ist nicht zulässig.  Legen Sie zum Zulassen der Protokollierung bekannter PII in Machine.config das Element "enableLoggingKnownPii" auf `true` fest.  Das Ereignis führt den Prozessnamen und die Prozess\-ID auf.  
  
## Siehe auch  
 [Ereignisprotokollierung](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [Allgemeine Referenz zu Ereignissen](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)