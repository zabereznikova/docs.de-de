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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8842bb47ad32ae1e26eaa503398ea91afb7fd1dd
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003202"
---
# <a name="internet-protocol-version-6"></a>Internetprotokoll Version 6
Das Internetprotokoll Version 6 (IPv6) ist eine neue Standardprotokollsammlung für die Netzwerkebene des Internets. IPv6 wurde entwickelt, um viele Probleme der aktuellen Version der Internetprotokollsammlung (IPv4) hinsichtlich Adressenknappheit, Sicherheit, automatischer Konfiguration, Bedarf an Erweiterbarkeit usw., zu lösen. IPv6 erweitert die Funktionen des Internets, um neue Arten von Anwendungen zu ermöglichen, einschließlich Peer-zu-Peer-Anwendungen und mobile Anwendungen. Nachfolgend sind die Hauptprobleme des aktuellen IPv4-Protokolls aufgelistet:  
  
-   Schnelle Erschöpfung des Adressraums  
  
     Dies hat zur Verwendung von Netzwerkadressübersetzungen (NATs, Network Address Translators) geführt, wodurch mehrere private Adressen einer einzelnen IP-Adresse zugeordnet werden. Die wichtigsten dadurch entstandenen Probleme sind Mehraufwand und Verlust von End-to-End-Verbindungen.  
  
-   Fehlende hierarchische Unterstützung  
  
     Aufgrund seiner inhärenten Organisation in vordefinierte Klassen verfügt IPv4 über keine echte hierarchische Unterstützung. Die IP-Adressen können unmöglich so strukturiert werden, dass sie der tatsächlichen Netzwerktopologie entsprechen. Durch diesen entscheidenden Entwurfsfehler sind umfangreiche Routingtabellen notwendig, um IPv4-Pakete an einem beliebigen Speicherort im Internet bereitzustellen.  
  
-   Komplexe Netzwerkkonfiguration  
  
     Mit IPv4 müssen Adressen statisch oder mithilfe eines Configuration-Protokolls, wie z.B. DHCP, zugewiesen werden. Idealerweise sollten Hosts nicht auf die Verwaltung einer DHCP-Infrastruktur vertrauen müssen. Sie sollten stattdessen selbst Konfigurationen basierend auf dem Netzwerksegment, in dem sie sich befinden, vornehmen können.  
  
-   Fehlende integrierte Authentifizierung und Vertraulichkeit  
  
     IPv4 erfordert keine Unterstützung für jedweden Mechanismus zur Authentifizierung oder Verschlüsselung der ausgetauschten Daten. Dies ändert sich mit IPv6. Internetprotokollsicherheit (IPSec, Internet Protocol Security) ist eine Supportanforderung von IPv6.  
  
 Eine neue Protokollsammlung muss die folgenden grundlegenden Anforderungen erfüllen:  
  
-   umfangreiches Routing und Adressierung mit geringem Mehraufwand  
  
-   automatische Konfiguration für verschiedene Verbindungssituationen  
  
-   integrierte Authentifizierung und Vertraulichkeit  
  
 Weitere Informationen finden Sie unter [IPv6-Adressierung](../../../docs/framework/network-programming/ipv6-addressing.md), [IPv6-Routing](../../../docs/framework/network-programming/ipv6-routing.md), [IPv6 Auto-Configuration (Automatische IPv6-Konfiguration)](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Enabling and Disabling IPv6 (Aktivieren und Deaktivieren von IPv6)](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) und [How to: Modify the Computer Configuration File to Enable IPv6 Support (Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung)](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## <a name="references"></a>Verweise  
 Nachfolgend eine Auswahl von RFC-Dokumenten, die Sie auf der Internetseite der „Engineering Task Force“ finden können ([http://www.ietf.org](http://www.ietf.org/)):  
  
-   RFC 1287: Towards the Future Internet Architecture (Internetarchitektur der Zukunft)  
  
-   RFC 1454: Comparison of Proposals for Next Version of IP (Vergleich von Vorschlägen für die nächste IP-Version)  
  
-   RFC 2373: IP Version 6 Addressing Architecture (Adressierungsarchitektur von IP Version 6)  
  
-   RFC 2374: An IPv6 Aggregatable Global Unicast Address Format (Ein globales aggregierbares Unicast-Adressenformat in IPv6)  
  
 Informationen zu IPv6 finden Sie auch im [IPv6-Bereich auf TechNet](http://go.microsoft.com/fwlink/?LinkID=179658).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für Socket-IPv6](https://msdn.microsoft.com/library/ms180981(v=vs.85).aspx)  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Sockets](../../../docs/framework/network-programming/sockets.md)
