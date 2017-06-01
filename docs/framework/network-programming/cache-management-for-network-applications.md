---
title: "Cacheverwaltung f&#252;r Netzwerkanwendungen | Microsoft Docs"
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
  - "Cache [.NET Framework], Netzwerkanwendungen"
  - "Netzwerkressourcen, Zwischenspeichern"
  - "Internet, Zwischenspeichern"
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Cacheverwaltung f&#252;r Netzwerkanwendungen
Dieses Thema und die zugehörigen Abschnitten werden, für Ressourcen zwischenzuspeichern abgerufen mithilfe <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> und <xref:System.Net.FtpWebRequest>\-Klassen.  
  
 Ein Cache ermöglicht eine temporäre Speicherung von Ressourcen, die von einer Anwendung angefordert wurden.  Wenn dieselbe Ressource mehrmals anfordert, kann diese aus dem Cache zurückgegeben werden und den Aufwand von wieder\-fordernd vermeiden es vom Server.  Zwischenspeichern kann die Anwendungsleistung verbessern, indem die Zeit reduziert, die erforderlich ist, um eine angeforderte Ressource abzurufen.  Zwischenspeichern kann auch Netzwerkverkehr verringern, indem die Anzahl der Reisen zum Server reduziert.  Während das Zwischenspeichern Leistung verbessert, erhöht er das Risiko, dass die Ressource, die der Anwendung zurückgegeben wird, veraltet ist und bedeutet, dass es nicht zur Ressource identisch ist, die vom Server gesendet wäre, beim Zwischenspeichern nicht verwendet wurden.  
  
 Zwischenspeichern erlaubt möglicherweise unbefugte Benutzer oder Prozesse zu den Lesesensiblen Daten.  Eine authentifizierte Antwort, die zwischengespeichert wird, wird aus dem Cache ohne eine zusätzliche Autorisierung abgerufen werden.  Wenn die Zwischenspeicherung aktiviert ist, Änderung an <xref:System.Net.WebRequest.CachePolicy%2A> zu <xref:System.Net.Cache.RequestCacheLevel> oder zu <xref:System.Net.Cache.RequestCacheLevel>, um das Zwischenspeichern für diese Anforderung zu deaktivieren.  
  
 Aufgrund der Sicherheitsaspekte ist das Zwischenspeichern **not**, das für die mittlere Ebenenszenarien empfohlen wird.  
  
## In diesem Abschnitt  
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)  
 Erklärt, was eine Cacherichtlinie ist und wie ein definiert.  
  
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 Definiert jeden Typ ortsbasierte Cacherichtlinie, die für Ressourcen verfügbar ist des Hypertext Transfer Protocol \(HTTP und https\).  
  
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 Beschreibt die Kriterien, die verwendet werden können, um eine zeitbasierte Cacherichtlinie anzupassen.  
  
 [Konfigurieren der Zwischenspeicherung in den Netzwerkanwendungen](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 Beschreibt, wie programmgesteuert Cacherichtlinien und \-anforderungen erstellt, die Zwischenspeicherung verwenden.  
  
## Referenz  
 <xref:System.Net.Cache>  
 Definiert die Typen und die Enumerationen, die verwendet wurden, um Cacherichtlinien für Ressourcen zu definieren, werden mithilfe <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> und <xref:System.Net.FtpWebRequest>\-Klassen.