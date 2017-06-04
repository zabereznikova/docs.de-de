---
title: "Cacherichtlinieninteraktion – maximales Alter und minimale Aktualit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "zeitbasierte Cacherichtlinien"
  - "Richtlinie zum erneuten Überprüfen"
  - "Cache [.NET Framework], zeitbasierte Richtlinien"
  - "Aktualität zwischengespeicherter Ressourcen"
  - "Richtlinie zum maximalen Alter"
  - "Richtlinie zur minimalen Aktualität"
  - "Alter zwischengespeicherter Ressourcen"
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Cacherichtlinieninteraktion – maximales Alter und minimale Aktualit&#228;t
Um sicherzustellen dass der neuste Inhalt an die Clientanwendung zurückgegeben wird, führt die Interaktion der Clientcacherichtlinie und die Anforderungen der Servererneuten validierung immer die konservativste Cacherichtlinie.  Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert und am 4. Januar abläuft.  
  
 Die folgenden Beispiele veranschaulichen die Cacherichtlinie, die von der Interaktion des Höchstalters \(`maxAge`\) und der Mindestwerte der Aktualität \(`minFresh`\) resultiert.  
  
-   Wenn die Cacherichtlinie `maxAge` \= 2 Tage festgelegt und `minFresh` nicht angegeben wird, wird der Inhalt am 3. Januar neu überprüft.  
  
-   Wenn die Cacherichtlinie `maxAge` \= 2 Tage und `minFresh` festlegt, 1 \= Tag, entsprechend `maxAge`, ist der Inhalt bis zum 3. Januar neu.  Gemäß `minFresh` ist der Inhalt bis zum 3. Januar neu.  Daher muss der Inhalt am 3. Januar erneut überprüft werden.  
  
-   Wenn die Cacherichtlinie `maxAge`\= festlegt, 2 Tage und `minFresh` \= 2 Tage, entsprechend `maxAge`, ist der Inhalt bis zum 3. Januar neu.  Gemäß `minFresh` ist der Inhalt bis zum 2. Januar neu.  Daher muss der Inhalt am 2. Januar erneut überprüft werden.  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [Cacherichtlinieninteraktion – maximales Alter und maximale Überalterung](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)