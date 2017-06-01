---
title: "NAT-Durchlauf mit IPv6 und Teredo | Microsoft Docs"
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
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# NAT-Durchlauf mit IPv6 und Teredo
Erweiterungen wurden vorgenommen, die Unterstützung für NAT\-Traversal \(Netzwerkadressübersetzung\) unterstützen.  Diese Änderungen sind für die Verwendung mit IPv6 und Teredo entworfen, sind jedoch auch für andere IP\-Tunnelntechnologien anwendbar.  Diese Erweiterungen beeinflussen Klassen in <xref:System.Net> und in den verknüpften Namespaces.  
  
 Diese Änderungen können Client\- und Serveranwendungen auswirken, die planen, IP\-Tunnelntechnologien zu verwenden.  
  
 Die Änderungen, die von NAT\-Durchlauf zu unterstützen sind nur für Anwendungen mit .NET Framework 4. verfügbar.  Diese Funktionen sind nicht auf früheren Versionen von .NET Framework verfügbar.  
  
## Übersicht  
 Die Internetprotokollversion 4 \(IPv4\) hat eine IPv4\-Adresse als 32 Bits lang.  Daher unterstützt IPv4 ungefähr 4 Milliarden eindeutige IP\-Adressen \(2^32\).  Wenn die Anzahl von Computern und Netzwerkgeräten im Internet, das in den neunziger Jahre erweitert wurde, wurden die Grenzen des IPv4\-Adressen\-Leerzeichens erleichtern.  
  
 Eine einige Techniken, die verwendet werden, um die Lebensdauer von IPv4 zu erweitern, ist, NAT bereitgestellt wurden, um einer einzelnen eindeutigen öffentlichen IP\-Adresse zu ermöglichen, um viele privaten IP\-Adressen \(privates Intranet\) darzustellen.  Die privaten IP\-Adressen hinter dem NAT\-Gerät geben die einzelne öffentliche IPv4\-Adresse frei.  Das NAT\-Gerät ist möglicherweise eine dedizierte Hardwaregerät \(ein billiger Drahtloszugriffspunkt und ein Router\), oder ein Computer, der einen Dienst ausführt, um NAT bereitzustellen.  Ein Gerät oder ein Dienst für diese öffentliche IP\-Adresse übersetzt IP\-Netzwerkpakete zwischen dem öffentlichen Internet und dem privaten Intranet.  
  
 Dieses Schema funktioniert gut für die Clientanwendungen, die an dem privaten Intranet ausgeführt werden, die Anforderungen in anderen IP\-Adressen \(normalerweise Server\) im Internet senden.  Das NAT\-Gerät oder Server können eine Zuordnung von Clientanforderungen so halten, wenn einer Antwort es weiß zurückgegeben wird, wo die Antwort sendet.  Dies wirft Schema Probleme für die Anwendungen auf, die in das private Intranet hinter das NAT\-Gerät ausgeführt werden, die Dienste bereitstellen möchten, auf Pakete überwachen und darauf reagieren.  Dies ist besonders Argument für gleichberechtigt Anwendungen.  
  
 Das Protokoll IPv6 hat eine IPv4\-Adresse als 128 Bits lang.  Daher unterstützt IPv6 sehr ein großes IP\-Adressen\-Leerzeichen von 3,2 eindeutigen Adressen x 10^38 \(2^128\).  Mit einem Adressbereich dieser Größe, ist es für jedes Gerät möglich, das an das eine verbundene eindeutige Adresse angegeben werden, Internet.  Es gibt Probleme.  Ein Großteil der Welt verwendet weiterhin nur IPv4.  Insbesondere unterstützen viele der vorhandenen Router und die Drahtloszugriffspunkte, die von Kleinunternehmen, Organisationen und Haushalte verwendet werden, nicht IPv6.  Für einige Internetdienstanbieter, die diese Kunden entweder dienen, haben unterstützen keine oder konfiguriert keine Unterstützung für IPv6.  
  
 Einige Technologien des Übergangs IPv6 sind entwickelt wurde, um Adressen IPv6 in einem Paket IPv4 zu abwärts.  Diese Technologien enthalten IP6\-zu\-IP4, ISATAP, und Teredo\-Tunnel, die automatische Tunneln der Adressierung und des Host\-zuHosts für Unicasten Datenverkehr IPv6 bereitstellen, wenn Hosts IPv6 Netzwerke IP4 durchlaufen müssen, um andere IPv6 zu erreichen, vernetzt.  Pakete IPv6 werden tunnelten als Pakete IPv4 gesendet.  Einige Tunnelntechniken werden verwendet, die NAT\-Durchlauf Adressen IPv6 durch ein NAT\-Gerät ermöglichen.  
  
 Teredo ist eine der Technologien des Übergangs IPv6, die Konnektivität IPv6 zu Funknetzwerken IPv4 führt.  Teredo wird in RFC 4380 dokumentiert, die von der Internet Engineering Task Force \(IETF\) veröffentlicht wird.  Windows XP SP2 und höher bieten Unterstützung für einen virtuellen Teredo\-Adapter, der eine öffentliche IPv6\-Adresse im Bereich 2001:0::\/32 bereitstellen kann.  Diese IPv6\-Adresse kann verwendet werden, um auf eingehende Verbindungen vom Internet zu überwachen und kann zu IPv6 aktivierten Client bereitgestellt werden, die an den überwachenden Dienst herstellen möchten.  Dies gibt eine Anwendung vom Sorgen um frei, wie ein Computer hinter einem NAT\-Gerät abweicht, da die Anwendung an sie mit der Adresse IPv6 Teredo derzeit herstellen kann.  
  
## Erweiterungen, um von NAT Durchlauf und Teredo zu unterstützen  
 Erweiterungen werden zu <xref:System.Net>, zu <xref:System.Net.NetworkInformation> und zu <xref:System.Net.Sockets>\-Namespaces für die Unterstützung von NAT\-Durchlauf mit IPv6 und Teredo hinzugefügt.  
  
 Einige Methoden werden der <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=fullName>\-Klasse hinzugefügt, um die Liste der Unicasten IP\-Adressen auf dem Host abzurufen.  Die <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A>\-Methode beginnt eine asynchrone Anforderung, die stabile Unicast\-IP\-Adresstabelle auf dem lokalen Computer abzurufen.  Die <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A>\-Methode beendet eine ausstehende asynchrone Anforderung, die stabile Unicast\-IP\-Adresstabelle auf dem lokalen Computer abzurufen.  Die <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A>\-Methode ist eine synchrone Anforderung, die stabile Unicast\-IP\-Adresstabelle auf dem lokalen Computer abzurufen und wartet, bis die Adresstabelle ggf. stabilisiert.  
  
 Die <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName>\-Eigenschaft kann verwendet werden, um zu bestimmen, ob <xref:System.Net.IPAddress> eine Adresse IPv6 Teredo ist.  
  
 Mithilfe dieses neuen <xref:System.Net.NetworkInformation.IPGlobalProperties> ermöglicht Klassenmethoden in Verbindung mit der <xref:System.Net.IPAddress.IsIPv6Teredo%2A>\-Eigenschaft eine Anwendung, die Teredo\-Adresse leicht zu suchen.  Eine Anwendung muss normalerweise nur die lokale Teredo\-Adresse kennen, wenn Sie diese Informationen den Remoteanwendungen an.  Beispielsweise kann beispielsweise eine gleichberechtigt Anwendung alle Adressen IPv6 zu einem Verkuppelnserver, der sie zu anderen weiterleitet kann blickt, um die direkte Kommunikation zu aktivieren.  
  
 Eine Anwendung sollte die überwachenden Dienst normalerweise festlegen, um auf <xref:System.Net.IPAddress.IPv6Any?displayProperty=fullName> statt auf der lokalen Teredo\-Adresse überwacht.  Daher, wenn ein Remote Client oder ein Peer eine direkte Route IPv6 auf den Host des Diensts überwachenden verfügt, der Client oder der Peer kann direkt mit IPv6 herstellen und muss nicht Teredo verwenden, um Pakete zu abwärts.  
  
 Für TCP\-Anwendungen hat die <xref:System.Net.Sockets.TcpListener?displayProperty=fullName>\-Klasse eine Methode, <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A>, von NAT\-Durchlauf zu aktivieren.  Für UDP\-Anwendungen hat die <xref:System.Net.Sockets.UdpClient?displayProperty=fullName>\-Klasse eine Methode, <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A>, von NAT\-Durchlauf zu aktivieren.  
  
 Für Anwendungen, die <xref:System.Net.Sockets.Socket?displayProperty=fullName> verwenden und verwandte Klassen, das <xref:System.Net.Sockets.Socket.GetSocketOption%2A> und die <xref:System.Net.Sockets.Socket.SetSocketOption%2A> werden mit der <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> Socketoption verwendet werden können NAT\-Durchlauf abzufragen, aktivieren oder deaktivieren.  
  
## Siehe auch  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=fullName>