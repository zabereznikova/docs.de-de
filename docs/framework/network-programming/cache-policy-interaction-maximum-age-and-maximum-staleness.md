---
title: "Cacherichtlinieninteraktion – maximales Alter und maximale &#220;beralterung | Microsoft Docs"
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
  - "Maximale Überalterung"
  - "Aktualität zwischengespeicherter Ressourcen"
  - "Zeit, zwischengespeicherte Ressourcen"
  - "Richtlinie zum maximalen Alter"
  - "Überalterung zwischengespeicherter Ressourcen"
  - "Alter zwischengespeicherter Ressourcen"
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Cacherichtlinieninteraktion – maximales Alter und maximale &#220;beralterung
Um sicherzustellen dass der neuste Inhalt an die Clientanwendung zurückgegeben wird, führt die Interaktion der Clientcacherichtlinie und die Anforderungen der Servererneuten validierung immer die konservativste Cacherichtlinie.  Alle Beispiele in diesem Thema veranschaulichen die Cacherichtlinie für eine Ressource, die am 1. Januar zwischengespeichert und am 4. Januar abläuft.  
  
 In den folgenden Beispielen wird der maximale Abgestandenheitswert \(`maxStale`\) in Verbindung mit einem Höchstalter \(`maxAge`\) verwendet:  
  
-   Wenn die Cacherichtlinie `maxAge` \= 5 Tage festgelegt und nicht angibt, ist ein `maxStale`\-Wert, nach dem `maxAge`\-Wert, der Inhalt bis zum 6. Januar verwendbar.  jedoch gemäß den Anforderungen der erneuten Validierung des Servers, wird der Inhalt am 4. Januar ab.  Da das Ablaufdatum \(und\) konservativer ist, hat dieser Vorrang vor der `maxAge` Richtlinie.  Daher wird der Inhalt am 4. Januar ab und muss erneut überprüft werden, obwohl der Höchstalter nicht erreicht wurde.  
  
-   Wenn die Cacherichtlinie `maxAge` \= festlegt, 5 Tage und `maxStale` \= 3 Tage, entsprechend dem `maxAge`\-Wert, ist der Inhalt bis zum 6. Januar verwendbar.  Gemäß dem `maxStale`\-Wert ist der Inhalt bis zum 7. Januar verwendbar.  Daher wird der Inhalt am 6. Januar erneut überprüft ab.  
  
-   Wenn die Cacherichtlinie `maxAge` \= 5 Tage und `maxStale` festlegt, 1 \= Tag, entsprechend dem `maxAge`\-Wert, ist der Inhalt bis zum 6. Januar verwendbar.  Gemäß dem `maxStale`\-Wert ist der Inhalt bis zum 5. Januar verwendbar.  Daher wird der Inhalt am 5. Januar erneut überprüft ab.  
  
 Wenn der Höchstalter kleiner als das Ablaufdatum ist herrscht, das konservativere Cachingverhalten immer vor und der maximale Abgestandenheitswert hat keine Auswirkungen.  Die folgenden Beispiele veranschaulichen die Auswirkung des Festlegens eines maximalen Wert der Abgestandenheit \(`maxStale`\), wenn der Höchstalter \(`maxAge`\) erreicht wird, bevor der Inhalt abläuft:  
  
-   Wenn die Cacherichtlinie `maxAge` \= 1 Tag festgelegt und keinen Wert für `maxStale`\-Wert angibt, wird der Inhalt neu überprüft, am 2. Januar obwohl dies nicht abgelaufen ist.  
  
-   Wenn die Cacherichtlinie `maxAge` \= 1 Tag und `maxStale` \= 3 Tage festgelegt wird, wird der Inhalt am 2. Januar erneut überprüft, um die konservativere Richtlinieneinstellung zu erzwingen.  
  
-   Wenn die Cacherichtlinie `maxAge` \= 1 Tag und `maxStale` \= 1 Tag festlegt, wird der Inhalt am 2. Januar neu überprüft.  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [Cacherichtlinieninteraktion – maximales Alter und minimale Aktualität](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)