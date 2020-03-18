---
title: Internetprotokoll Version 6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: 367db4fa4e585d6066009dbd1afacb154829319a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047878"
---
# <a name="internet-protocol-version-6"></a>Internetprotokoll Version 6
Das Internetprotokoll Version 6 (IPv6) ist eine neue Standardprotokollsammlung für die Netzwerkebene des Internets. IPv6 wurde entwickelt, um viele Probleme der aktuellen Version der Internetprotokollsammlung (IPv4) hinsichtlich Adressenknappheit, Sicherheit, automatischer Konfiguration, Bedarf an Erweiterbarkeit usw., zu lösen. IPv6 erweitert die Funktionen des Internets, um neue Arten von Anwendungen zu ermöglichen, einschließlich Peer-zu-Peer-Anwendungen und mobile Anwendungen. Nachfolgend sind die Hauptprobleme des aktuellen IPv4-Protokolls aufgelistet:  
  
- Schnelle Erschöpfung des Adressraums  
  
     Dies hat zur Verwendung von Netzwerkadressübersetzungen (NATs, Network Address Translators) geführt, wodurch mehrere private Adressen einer einzelnen IP-Adresse zugeordnet werden. Die wichtigsten dadurch entstandenen Probleme sind Mehraufwand und Verlust von End-to-End-Verbindungen.  
  
- Fehlende hierarchische Unterstützung  
  
     Aufgrund seiner inhärenten Organisation in vordefinierte Klassen verfügt IPv4 über keine echte hierarchische Unterstützung. Die IP-Adressen können unmöglich so strukturiert werden, dass sie der tatsächlichen Netzwerktopologie entsprechen. Durch diesen entscheidenden Entwurfsfehler sind umfangreiche Routingtabellen notwendig, um IPv4-Pakete an einem beliebigen Speicherort im Internet bereitzustellen.  
  
- Komplexe Netzwerkkonfiguration  
  
     Mit IPv4 müssen Adressen statisch oder mithilfe eines Configuration-Protokolls, wie z.B. DHCP, zugewiesen werden. Idealerweise sollten Hosts nicht auf die Verwaltung einer DHCP-Infrastruktur vertrauen müssen. Sie sollten stattdessen selbst Konfigurationen basierend auf dem Netzwerksegment, in dem sie sich befinden, vornehmen können.  
  
- Fehlende integrierte Authentifizierung und Vertraulichkeit  
  
     IPv4 erfordert keine Unterstützung für jedweden Mechanismus zur Authentifizierung oder Verschlüsselung der ausgetauschten Daten. Dies ändert sich mit IPv6. Internetprotokollsicherheit (IPSec, Internet Protocol Security) ist eine Supportanforderung von IPv6.  
  
 Eine neue Protokollsammlung muss die folgenden grundlegenden Anforderungen erfüllen:  
  
- umfangreiches Routing und Adressierung mit geringem Mehraufwand  
  
- automatische Konfiguration für verschiedene Verbindungssituationen  
  
- integrierte Authentifizierung und Vertraulichkeit  
  
 Weitere Informationen finden Sie unter [IPv6-Adressierung](ipv6-addressing.md), [IPv6-Routing](ipv6-routing.md), [IPv6 Auto-Configuration (Automatische IPv6-Konfiguration)](ipv6-auto-configuration.md), [Enabling and Disabling IPv6 (Aktivieren und Deaktivieren von IPv6)](enabling-and-disabling-ipv6.md) und [How to: Modify the Computer Configuration File to Enable IPv6 Support (Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung)](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## <a name="references"></a>Verweise  
 Nachfolgend finden Sie eine Auswahl von RFC-Dokumenten, die Sie auf der Webseite der [Engineering Task Force (IETF)](https://www.ietf.org/) finden können:  
  
- RFC 1287: Towards the Future Internet Architecture (Internetarchitektur der Zukunft)  
  
- RFC 1454: Comparison of Proposals for Next Version of IP (Vergleich von Vorschlägen für die nächste IP-Version)  
  
- RFC 2373: IP Version 6 Addressing Architecture (Adressierungsarchitektur von IP Version 6)  
  
- RFC 2374: An IPv6 Aggregatable Global Unicast Address Format (Ein globales aggregierbares Unicast-Adressenformat in IPv6)  
  
 Informationen zu IPv6 finden Sie auch in der [IP-Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).  
  
## <a name="see-also"></a>Weitere Informationen

- [Beispiel für Socket-IPv6](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms180981%28v=vs.85%29)
- [Network Programming Samples (Beispiele zur Netzwerkprogrammierung)](network-programming-samples.md)
- [Sockets](sockets.md)
