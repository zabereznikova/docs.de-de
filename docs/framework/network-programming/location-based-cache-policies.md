---
title: "Speicherortbasierte Cacherichtlinien | Microsoft Docs"
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
  - "Richtlinie „Zwischenspeichern, sofern verfügbar“"
  - "Richtlinie zum erneuten Laden"
  - "Speicherortbasierte Cacherichtlinien"
  - "Richtlinie „Nur zwischenspeichern“"
  - "Lokaler Cache"
  - "Zwischen-Cache"
  - "Richtlinie „Kein Cache, kein Speicher“"
  - "Cache [.NET Framework], Speicherortbasierte Richtlinien"
  - "Richtlinie zum erneuten Überprüfen"
  - "Aktualität zwischengespeicherter Ressourcen"
  - "Richtlinie „Cache oder nur nächster Cache“"
  - "Aktualisierungsrichtlinie"
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Speicherortbasierte Cacherichtlinien
Ziehen Sie eine ortsbasierte Cacherichtlinie definiert die Aktualität von gültigen zwischengespeicherten Einträgen auf Grundlage, wo die angeforderte Ressource verwiesen werden kann.  Eine zwischengespeicherte Ressource ist gültig, wenn die Anwendung sie nicht verstößt nicht vom Server angegebene Anforderungen der erneuten Validierung ausführt.  Eine ortsbasierte Cacherichtlinie wird programmgesteuert erstellt, indem ein <xref:System.Net.Cache.RequestCachePolicy> oder <xref:System.Net.Cache.HttpRequestCachePolicy>\-Klassenkonstruktor verwendet.  Der Typ der ortsbasierten Richtlinie wird dem Konstruktor mit einem <xref:System.Net.Cache.RequestCacheLevel> oder <xref:System.Net.Cache.HttpRequestCacheLevel>\-Enumerationswerts übergeben.  Codebeispiele, die ortsbasierte Cacherichtlinien erstellen, finden Sie unter [Gewusst wie: Legen Sie eine ortsbasierte Cache\-Richtlinie für eine Anwendung fest](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md).  In den folgenden Abschnitten werden die einzelnen Typ ortsbasierte Cacherichtlinie für Ressourcen des Hypertext Transfer Protocol \(HTTP und https\).  
  
## Cache wenn verfügbare Richtlinie  
 Wenn eine gültige angeforderte Ressource im lokalen Cache ist, wird sie Ressource verwendet; Andernfalls wird die Anforderung für die Ressource an den Server gesendet.  Wenn die angeforderte Ressource in einem Cache zwischen Client und Server verfügbar ist, kann die Anforderung durch einen Zwischencachen erfüllt werden.  
  
## Cache\-nur Richtlinie  
 Wenn eine gültige angeforderte Ressource im lokalen Cache ist, wird sie Ressource verwendet.  Wenn diese Cacherichtlinienebene angegeben wird, wird eine <xref:System.Net.WebException> Ausnahme ausgelöst, wenn das Element nicht im lokalen Cache.  
  
## Cache oder folgende Cache\-nur Richtlinie  
 Wenn eine gültige angeforderte Ressource im lokalen Cache oder in einem Zwischencachen im lokalen Netzwerk ist, wird sie Ressource verwendet.  Andernfalls wird eine <xref:System.Net.WebException>\-Ausnahme ausgelöst.  Im HTTP\-Zwischenspeichernprotokoll wird dieses mithilfe der nur\-wenn\-gezwischenspeicherten Cachesteuerungsdirektive erreicht.  
  
## Kein Cache keine Speicher\-Richtlinie  
 Eine angeforderte Ressource wird nie von jedem Cache verwendet und wird nie in einen Cache vorgenommen.  Wenn eine angeforderte Ressource im lokalen Cache vorhanden ist, wird sie entfernt.  Diese Richtlinienebene gibt an Zwischencachen an, dass die Ressource auch entfernt werden kann.  Im HTTP\-Zwischenspeichernprotokoll wird dieses mithilfe der NO\-Speicher Cachesteuerungsdirektive erreicht.  
  
## Aktualisierungs\-Richtlinie  
 Eine angeforderte Ressource kann verwendet werden, wenn sie vom Server abgerufen wird oder in einem Cache als dem lokalen Cache gefunden.  Bevor die Anforderung von einem Zwischencache ausgeführt werden kann, muss dieser Cache den zwischengespeicherten Eintrag anhand des Servers neu überprüfen.  Im HTTP\-Zwischenspeichernprotokoll wird dieses mithilfe MaximumAGEs \= 0 Cachesteuerungsdirektive und der no\-cache\-Pragmaheader erreicht.  
  
## Umladen\-Richtlinie  
 Angeforderte Ressourcen müssen vom Server abgerufen werden.  Die Antwort wird im lokalen Cache gespeichert.  Im HTTP\-Zwischenspeichernprotokoll wird dieses mithilfe der no\-cache\-Cachesteuerungsdirektive und des no\-cache\-Pragmaheaders erreicht.  
  
## Validieren Sie Richtlinie erneut  
 Vergleicht die Kopie der Ressource im Cache mit der Kopie auf dem Server.  Wenn die Kopie auf dem Server aktueller ist, wird sie zum Ausführen der Anforderung verwendet und ersetzt die Kopie im Cache.  Wenn die Kopie im Cache mit dem Exemplar auf dem Server identisch ist, wird die zwischengespeicherte Kopie verwendet.  Im HTTP\-Cacheprotokoll erfolgt dies durch eine bedingte Anforderung.  
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)