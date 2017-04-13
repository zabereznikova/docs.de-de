---
title: "IPv6-Routing | Microsoft Docs"
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
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# IPv6-Routing
Ein flexibler Routingmechanismus ist ein Vorteil von IPv6.  Aufgrund der Methode, in der Netzwerk IPv4 IDs waren und zugeordnet sind, große Routingtabellenanforderung, von den Routern gespeichert werden, die auf den Internet\-Backbonen sind.  Diese Router müssen alle Routen kennen, um Pakete weiterzuleiten, die möglicherweise auf einen beliebigen Knoten im Internet verwiesen werden.  Mit seiner Möglichkeit, Adressen zu aggregieren, können IPv6 das Behandeln und flexible drastisch reduziert die Größe von Routingtabellen.  In dieser neuen adressierenden Architektur müssen zwischen Router nur den lokalen Teil des Netzwerks verfolgen, um die Meldungen entsprechend weiterzuleiten.  
  
## Nachbarsuche  
 Einige der Funktionen, die von den Nachbarsuchen bereitgestellt werden, sind:  
  
-   Routersuche.  Dadurch können Hosts, um lokale Router zu identifizieren.  
  
-   Address resolution.  Dadurch können Knoten, um eine Link\-Layer\-Adresse für ein entsprechendes Next\-Hop\-Adresse \(ein Ersatz für Address Resolution Protocol \[ARP\]\) aufzulösen.  
  
-   Adressenautomatische Konfiguration.  Dies ermöglicht Hosts, Site\-Local\- und globale Adressen automatisch zu konfigurieren.  
  
 Nachbarsuche verwenden Internet Message Control Protocol für Meldungen IPv6 \(ICMPv6\), die Folgendes umfassen:  
  
-   Routerankündigung.  Gesendet durch einen Router auf einer pseudo\-periodischen Basis oder als Reaktion auf eine Routeranfrage.  Verwendungsrouterankündigungen der Router IPv6, um ihre Verfügbarkeit, der Adressenpräfixe und anderer Parameter vorzulesen.  
  
-   Routeranfrage.  Gesendet durch einen Host, um anzufordern, dass Router im Link eine Routerankündigung sofort senden.  
  
-   Nachbaranfrage.  Gesendet durch Knoten für IP\-Adressen resolution, doppelte Adressenerkennung oder überprüfen, ob ein Nachbar weiterhin erreichbar ist.  
  
-   Nachbarankündigung.  Gesendet durch Knoten, um auf eine Nachbaranfrage zu reagieren oder Nachbarn zu einer Änderung der Link\-Layer\-Adresse zu benachrichtigen.  
  
-   Umleitung.  Gesendet durch Router, um ein besseres Next\-Hop\-Adresse zu einem bestimmten Ziel für einen sendenden Knoten anzugeben.  
  
## Siehe auch  
 [Internetprotokoll Version 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)