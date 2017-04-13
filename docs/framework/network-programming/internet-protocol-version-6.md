---
title: "Internetprotokoll Version 6 | Microsoft Docs"
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
  - "IPv6, Verbesserungen"
  - "IPv4"
  - "IPv6"
  - "Internetprotokoll Version 6, Verbesserungen"
  - "Internetprotokoll Version 6"
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Internetprotokoll Version 6
Das Internetprotokoll, Version 6 \(IPv6\) ist eine neue Suite von Standardprotokollen für die Vermittlungsschicht Web.  IPv6 ist so konzipiert, dass viele der Probleme der aktuellen Version von der Internetprotokollsuite \(bekannt als IPv4\) hinsichtlich der Adressenentleerung, Sicherheit, automatische Konfiguration, Erweiterbarkeit zu lösen, u. a.  IPv6 erweitert die Funktionen mit dem, neue Arten von Anwendungen, einschließlich gleichberechtigt und mobilen Anwendungen zu ermöglichen.  Die folgenden ist die Kernfragen des Protokolls des aktuellen IPv4:  
  
-   Schnelle Entleerung des Speicherbereichs.  
  
     Dies hat zur Verwendung von Endsystemadresse\-Übersetzern \(Netzwerkadressübersetzung\) mehrere Privatanschriften dieser Zuordnung zu einer einzelnen IP\-Adresse öffentlichen übernommen.  Die wichtigsten Probleme, die von diesen Mechanismus erstellt werden, verarbeiten Aufwand und mangelnder Verbindungsfähigkeit.  
  
-   Fehlende Hierarchienunterstützung.  
  
     Aufgrund der inhärenten vordefinierten Klassenorganisation fehlt IPv4 echte hierarchische Unterstützung.  Es ist nicht möglich, die IP\-Adressen auf eine Weise zu strukturieren, die eigentlich die Netzwerktopologie zuordnet.  Dieser endgültige Konstruktionsfehler erstellt die Anforderung, damit große Routingtabellen Pakete IPv4 an einem beliebigen Speicherort auf dem Internet bereitstellen.  
  
-   Komplexe Netzkonfiguration.  
  
     Mit IPv4 müssen Adressen statisch zugewiesen werden oder mit einem Konfigurationsprotokoll wie DHCP.  Unter optimalen Umständen nehmen Hosts nicht auf der Verwaltung einer DHCP\-Infrastruktur verwenden müssen.  Stattdessen werden sie sein, auf dem Netzwerksegment zu konfigurieren, in dem sie sind.  
  
-   Fehlende integrierter Authentifizierung und Vertraulichkeit.  
  
     IPv4 erfordert die Unterstützung nicht für einen Mechanismus, der Authentifizierung oder Verschlüsselung der ausgetauschten Daten bereitstellt.  Dadurch wird mit IPv6.  Internetprotokollsicherheit \(IPSec\) ist eine Anforderung der Unterstützungs IPv6.  
  
 Eine neue Protokollsuite muss den folgenden grundlegenden Anforderungen erfüllen:  
  
-   Umfangreiches Routing und Behandeln mit niedrigem Mehraufwand.  
  
-   Automatische Konfiguration für verschiedene Verbindungssituationen.  
  
-   Integrierte Authentifizierung und Vertraulichkeit.  
  
 Weitere Informationen finden Sie unter [IPv6\-Adressierung](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6\-Routing](../../../docs/framework/network-programming/ipv6-routing.md), [Automatische IPv6\-Konfiguration](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Aktivieren und Deaktivieren von IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) und [Gewusst wie: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6\-Unterstützung](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## Verweise  
 Die folgenden ist ausgewählte RFC\-Dokumente, die an der Internet Engineering Task Force\-Site finden \([http:\/\/www.ietf.org](http://www.ietf.org/)\):  
  
-   RFC 1287, und zur zukünftigen Internet\-Architektur.  
  
-   RFC 1454, Vergleich der Zugriff für nachfolgende Version von IP\-Adressen.  
  
-   RFC 2373, IP\-Version 6\-Adressarchitektur.  
  
-   RFC 2374, Ein IPv6\-aggregierbares globales Unicastadressformat.  
  
 Sie können IPv6\-related auch Informationen zu [Bereich IPv6 auf Technet](http://go.microsoft.com/fwlink/?LinkID=179658) suchen.  
  
## Siehe auch  
 [Beispiel für Socket\-IPv6](http://go.microsoft.com/fwlink/?LinkID=179568)   
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)