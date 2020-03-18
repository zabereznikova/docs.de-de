---
title: NAT-Durchlauf mit IPv6 und Teredo
ms.date: 03/30/2017
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
ms.openlocfilehash: f617dc8912091576727b90da1e9efb9ebd5f9bda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642170"
---
# <a name="nat-traversal-using-ipv6-and-teredo"></a>NAT-Durchlauf mit IPv6 und Teredo
Es wurden Verbesserungen vorgenommen, sodass nun der NAT-Durchlauf (Netzwerkadressenübersetzung) unterstützt wird. Diese Änderungen wurden für den Gebrauch mit IPv6 und Teredo entwickelt, sie können aber auch auf andere Technologien zum IP-Tunneln angewendet werden. Diese Verbesserungen betreffen Klassen im <xref:System.Net> und verknüpften Namespaces.  
  
 Diese Änderungen können sich auf Client- und Serveranwendungen auswirken, die Technologien zum IP-Tunneln verwenden möchten.  
  
 Die Änderungen, die für die Unterstützung des NAT-Durchlaufs vorgenommen wurden, sind nur für Anwendungen mit .NET Framework Version 4 verfügbar. Diese Features stehen in früheren Versionen des .NET Frameworks nicht zur Verfügung.  
  
## <a name="overview"></a>Übersicht  
 Internetprotokoll Version 4 (IPv4) hat die Länge einer IPv4-Adresse als 32-Bit angegeben. Deshalb unterstützt IPv4 etwa 4 Milliarden eindeutige IP-Adressen (2 hoch 32). Als die Zahl der Computer und Netzwerkgeräte mit Internetzugriff in den 1990ern anwuchs, wurden die Grenzen des IPv4-Adressraums aufgezeigt.  
  
 Eine von mehreren eingesetzten Methoden zur Verlängerung der Lebensdauer von IPv4 wurde in NAT bereitgestellt. Damit kann eine einzelne, eindeutige öffentliche IP-Adresse eine große Zahl privater IP-Adressen darstellen (privates Netzwerk). Die privaten Adressen des NAT-Geräts haben die einzelne öffentliche IPv4-Adresse gemein. Das NAT-Gerät ist möglicherweise ein dediziertes Hardwaregerät (z.B. ein kostengünstiger Funkzugriffspunkt und Router) oder ein Computer, der einen Dienst zur Bereitstellung von NAT ausführt. Ein Gerät oder Dienst für diese öffentliche IP-Adresse übersetzt IP-Netzwerkpakete zwischen dem Internet und dem privaten Netzwerk.  
  
 Dies funktioniert ideal mit Clientanwendungen, die im privaten Netzwerk ausgeführt werden, die Anforderungen an andere IP-Adressen (überwiegend Server) im Internet senden. Das NAT-Gerät oder der NAT-Server kann ein Mapping der Clientanforderungen beibehalten, sodass klar ist, an welche Stelle eine Antwort geschickt werden muss, wenn diese zurückgegeben wird. Diese Methode ist jedoch problematisch für Anwendungen, die in einem privaten Netzwerk hinter dem NAT-Gerät ausgeführt werden, die Dienste bereitstellen, auf Pakete lauschen und darauf reagieren möchten. Dies gilt insbesondere für Peer-zu-Peer-Anwendungen.  
  
 Das IPv6-Protokoll hat die Länge einer IPv4-Adresse als 128-Bit angegeben. Deshalb unterstützt IPv6 einen sehr großen IP-Adressraum von 3,2 x 10^38 eindeutigen Adressen (2 hoch 128). Bei einem Adressraum dieser Größe kann jedes mit dem Internet verbundene Gerät eine eindeutige Adresse erhalten. Dabei gibt es allerdings Probleme. Ein Großteil der Welt verwendet immer noch IPv4. Insbesondere Router und Funkzugriffspunkte, die von kleinen Unternehmen, Organisationen und Haushalten eingesetzt werden, unterstützen kein IPv6. Darüber hinaus unterstützen einige Internetanbieter dieser Kunden IPv6 nicht oder haben die Konfiguration nicht konfiguriert.  
  
 Es wurden mehrere Übergangstechnologien für IPv6 entwickelt, um IPv6-Adressen in ein IPv4-Paket zu tunneln. Zu diesen Technologien zählen 6to4-, ISATAP- und Teredo-Tunnel, die Adressenzuweisungen und automatisches Host-zu-Host-Tunneln für IPv6-Unicastdatenverkehr bieten, wenn IPv6-Hosts IPv4-Netzwerke durchlaufen müssen, um andere IPv6-Netzwerke zu erreichen. IPv6-Pakete werden als IPv4-Pakete getunnelt gesendet. Es werden mehrere Tunnelmethoden verwendet, um IPv6-Adressen den NAT-Durchlauf durch ein NAT-Gerät zu erlauben.  
  
 Teredo ist eine der IPv6-Übergangstechnologien, durch die IPv6-Konnektivität in IPv4-Netzwerken möglich ist. Teredo wird in der RFC 4380 dokumentiert, die von der Internet Engineering Task Force (IETF) veröffentlicht wird. Windows XP SP2 und höher bietet Unterstützung für einen virtuellen Teredo-Adapter, der eine öffentliche IPv6-IP-Adresse im Bereich 2001:0::/32 bereitstellt. Diese IPv6-Adresse kann verwendet werden, um auf eingehende Verbindungen aus dem Internet zu lauschen und kann IPv6-fähigen Clients bereitgestellt werden, die eine Verbindung mit dem lauschenden Dienst herstellen möchten. So muss sich eine Anwendung nicht mehr darum kümmern, wie es auf einen Computer hinter einem NAT-Gerät eingeht, da die Anwendung einfach eine Verbindung mit ihrer IPv6-Teredo-Adresse herstellen kann.  
  
## <a name="enhancements-to-support-nat-traversal-and-teredo"></a>Verbesserungen zur Unterstützung des NAT-Durchlaufs und Teredo  
 Den Namespaces <xref:System.Net>, <xref:System.Net.NetworkInformation>und <xref:System.Net.Sockets> wurden Verbesserungen hinzugefügt, um den NAT-Durchlauf mit IPv6 und Teredo zu unterstützen.  
  
 Mehrere Methoden werden zu der <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=nameWithType>-Klasse hinzugefügt, um die Liste von Unicast-IP-Adressen auf dem Host abzurufen. Die <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A>-Methode beginnt eine asynchrone Anforderung zum Abrufen der Tabelle der stabilen Unicast-IP-Adresse auf dem lokalen Computer. Die <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A>-Methode beendet eine ausstehende asynchrone Anforderung zum Abrufen der Tabelle der stabilen Unicast-IP-Adresse auf dem lokalen Computer. Die <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A>-Methode ist eine synchrone Anforderung zum Abrufen der Tabelle der stabilen Unicast-IP-Adresse auf dem lokalen Computer, wobei falls nötig gewartet wird, bis sich die Adressentabelle stabilisiert.  
  
 Die <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>-Eigenschaft kann verwendet werden, um zu bestimmen, ob eine <xref:System.Net.IPAddress> eine IPv6 Teredo-Adresse ist.  
  
 Die Verwendung dieser neuen <xref:System.Net.NetworkInformation.IPGlobalProperties>-Klassenmethoden in Kombination mit der <xref:System.Net.IPAddress.IsIPv6Teredo%2A>-Eigenschaft ermöglicht es einer Anwendung, die Teredo-Adresse leicht zu finden. Eine Anwendung muss die lokale Teredo-Adresse normalerweise nur kennen, wenn sie diese Information an Remoteanwendungen kommuniziert. Beispielsweise könnte eine Peer-zu-Peer-Anwendung alle ihre IPv6-Adressen an einen Zuordnungsserver senden, der diese dann an andere Peers weiterleiten kann, um die direkte Kommunikation zu ermöglichen.  
  
 Eine Anwendung sollte normalerweise ihren lauschenden Dienst so festlegen, dass er an <xref:System.Net.IPAddress.IPv6Any?displayProperty=nameWithType> anstatt an der lokalen Teredo-Adresse lauscht. Wenn also ein Remoteclient oder Peer über eine IPv6-Route zum Host des lauschenden Diensts verfügt, kann der Client oder Peer mithilfe von IPv6 direkt eine Verbindung herstellen und muss nicht Teredo verwenden, um Pakete zu tunneln.  
  
 Bei TCP-Anwendungen verfügt die <xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType>-Klasse über eine <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A>-Methode zum Aktivieren des NAT-Durchlaufs. Bei UDP-Anwendungen verfügt die <xref:System.Net.Sockets.UdpClient?displayProperty=nameWithType>-Klasse über eine <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A>-Methode zum Aktivieren des NAT-Durchlaufs.  
  
 Bei Anwendungen, die <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> und zugehörige Klassen verwenden, können die <xref:System.Net.Sockets.Socket.GetSocketOption%2A>- und <xref:System.Net.Sockets.Socket.SetSocketOption%2A>-Methoden mit der Socketoption <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType> verwendet werden, um den NAT-Durchlauf abzufragen, zu aktivieren oder zu deaktivieren.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=nameWithType>
