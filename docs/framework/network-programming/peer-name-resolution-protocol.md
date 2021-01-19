---
title: Peer Name Resolution-Protokoll (PNRP)
description: Erfahren Sie mehr über das Peer Name Resolution-Protokoll (PNRP), ein sicheres, skalierbares und dynamisches Protokoll für die Namensregistrierung und -auflösung.
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: 9ab46566b3c0d6ceff694eca266bdb6e10441374
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98191234"
---
# <a name="peer-name-resolution-protocol"></a>Peer Name Resolution-Protokoll (PNRP)

In Peer-zu-Peer-Umgebungen verwenden Peers bestimmte Namensauflösungssysteme, um Namen oder andere Arten von Bezeichner in die Netzwerkadressen des jeweils anderen Peers (Adressen, Protokolle und Ports) aufzulösen. In der Vergangenheit ist die Peernamensauflösung durch die grundsätzlich flüchtige Konnektivität sowie andere Mängel im Domänennamenserver (DNS) erschwert worden.  
  
 Die Microsoft® Windows® Peer-zu-Peer Netwerkplattform löst dieses Problem mit dem Peer Name Resolution-Protokoll (PNRP), ein sicheres, skalierbares und dynamisches Namensregistrierungs- und Namensauflösungsprotokoll, das erstmals für Windows XP entwickelt und dann in Windows Vista™ aktualisiert wurde. Die Funktionsweise des PNRP unterscheidet sich sehr von traditionellen Auflösungssystemen und eröffnet interessante neue Möglichkeiten für Anwendungsentwickler.  
  
 Mit PNRP können Peernamen auf den Computer oder auf einzelne Anwendungen oder Dienste auf dem Computer angewendet werden. Eine Peernamensauflösung enthält eine Adresse, einen Port und möglicherweise eine erweiterte Nutzlast. Die Vorteile dieses Systems sind Fehlertoleranz, keine Engpässe, und Namensauflösungen, die niemals veraltete Adressen zurückgeben; das Protokoll ist somit eine ausgezeichnete Lösung für die Lokalisierung mobiler Benutzer.  
  
 Im Hinblick auf die Sicherheit können Peernamen als gesichert (geschützt) oder unsicher (ungeschützt) veröffentlicht werden. PNRP verwendet die Kryptografie mit öffentlichem Schlüssel, um Peernamen gegen Spoofing zu schützen. Computer sowie Dienste können mit PNRP benannt werden.  
  
Das Peer Name Resolution-Protokoll hat die folgenden Eigenschaften:  
  
- Verteilt und nahezu serverlos. Server werden nur in der Bootstrapping-Phase benötigt.  
  
- Speichern Sie die Namensveröffentlichung ohne die Beteiligung Dritter. Im Gegensatz zur DNS-Namensveröffentlichung ist die PNRP-Namensveröffentlichung ohne Verzögerung und kostenlos.  
  
- PNRP wird in Echtzeit aktualisiert. Somit wird die Auflösung veralteter Adressen verhindert.  
  
- Die Auflösung von Namen per PNRP erstreckt sich über Computer hinaus, indem die Namensauflösung für Dienste zugelassen wird.  
  
## <a name="the-systemnetpeertopeer-namespace"></a>Der System.Net.PeerToPeer-Namespace  
  
- Die PNRP-Funktionalität wird durch den <xref:System.Net.PeerToPeer>-Namespace in .NET Framework, Version 3.5 definiert. Sie stellt eine Reihe von Typen zur Verfügung, die zum Registrieren und Auflösen von Peernamen mit einem verfügbaren PNRP-Dienst verwendet werden können.  
  
- (PNRP und benutzerdefinierte PeerResolver können mithilfe der im <xref:System.ServiceModel.PeerResolvers>-Namespace zur Verfügung gestellten Typen instanziiert und erstellt werden.)  
  
- Die grundlegenden Typen, die zum Registrieren und Auflösen von Namen mit einem verfügbaren PNRP-Dienst verwendet werden, sind wie folgt:  
  
- <xref:System.Net.PeerToPeer.Cloud>: Definiert die Informationen, die eine verfügbare PNRP-Cloud, einschließlich ihres Bereichs beschreiben.  
  
- <xref:System.Net.PeerToPeer.PeerName>: Definiert einen Peernamen, der zum Registrieren und anschließendem Auflösen von einem Peer in einer Cloud verwendet werden kann.  
  
- <xref:System.Net.PeerToPeer.PeerNameRecord>: Definiert den Datensatz in der PNRP-Cloud, die die Registrierungsinformationen für einen Peer enthält, der die Netzwerk-Endpunkte mit einschließt, an denen der Peer kontaktiert werden kann.  
  
- <xref:System.Net.PeerToPeer.PeerNameRegistration>: Definiert den Registrierungsvorgang für einen Peernamen, einschließlich der Methoden, um die Peer-Namensregistrierung zu starten oder zu beenden.  
  
- <xref:System.Net.PeerToPeer.PeerNameResolver>: Definiert den Prozess zum Auflösen eines Peernamens in den/die zugehörigen Netzwerk-Endpunkt(e), einschließlich der synchronen und asynchronen Methoden für die Auflösung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [Beispiele zur Netzwerkprogrammierung](network-programming-samples.md)
