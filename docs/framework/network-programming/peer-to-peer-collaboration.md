---
title: Peer-to-Peer-Zusammenarbeit
ms.date: 03/30/2017
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
ms.openlocfilehash: 7cf92f6bf3c269e584cb8b3cdcf910be5b89fd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047383"
---
# <a name="peer-to-peer-collaboration"></a>Peer-to-Peer-Zusammenarbeit

Peer-zu-Peer Networking ist die Verwendung relativ leistungsfähiger Computer (Personalcomputer), die am Rand des Internets für mehr als nur clientbasierte Rechenaufgaben vorhanden sind. Der moderne Personalcomputer (PC) verfügt über einen sehr schnellen Prozessor, einen beträchtlichen Arbeitsspeicher und eine große Festplatte, die beim Ausführen von allgemeinen Rechenaufgaben, wie z.B. E-Mail und Webbrowsen allesamt nicht voll ausgelastet werden. Der moderne PC kann einfach sowohl als Client als auch als Server (kein Peer) für viele Arten von Anwendungen fungieren.  
  
Die Peer-zu-Peer-Kollaborationsinfrastruktur ist eine vereinfachte Implementierung der Microsoft Windows-Peer-zu-Peer-Infrastruktur, die den Dienst „Personen in meiner Umgebung“ in Windows Vista und späteren Plattformen nutzt. Sie wird am besten für Peer-fähige Anwendungen innerhalb eines Subnetzes verwendet, für die der „Personen in meiner Umgebung“-Dienst ausgeführt wird, obwohl sie auch Internetendpunkte oder Kontakte bedienen kann. Sie beinhaltet den gängigen Contact Manager, der vom Live Messenger und anderen Live-fähigen Anwendungen verwendet wird, um die Kontaktendpunkte, die Verfügbarkeit und die Präsenz zu bestimmen.  
  
## <a name="collaboration-applications"></a>Anwendungen für die Zusammenarbeit

 Eine typische Peer-zu-Peer-Kollaborationsanwendung umfasst die folgenden Schritte:  
  
- Der Peer bestimmt die Identität eines Peers, der sich für das Hosten einer Kollaborationssitzung interessiert.  
  
- Eine Anforderung zum Hosten einer Sitzung wird aus irgendeinem Grund gesendet, und der Peer erklärt sich dazu bereit, die Kollaborationstätigkeit zu verwalten.  
  
- Der Host lädt Kontakte im Subnetz (einschließlich des Anforderers) zu einer Sitzung ein.  
  
- Alle Peers, die kollaborieren möchten, können den Host zu Ihrem Kontaktmanager hinzufügen.  
  
- Die meisten Peers senden die Antwort auf die Einladung, ob akzeptiert oder abgelehnt, zeitnah zurück an den Hostpeer.  
  
- Alle Peers, die kollaborieren möchten, abonnieren den Hostpeer.  
  
- Während die Peers ihre anfängliche Kollaborationsaktivität ausführen, kann der Hostpeer Remotepeers zu seinem Kontaktmanager hinzufügen. Er verarbeitet auch alle Antworten auf Einladungen, um zu bestimmen, wer die Einladung akzeptiert, wer sie abgelehnt, und wer nicht geantwortet hat.  Er kann möglicherweise Einladungen an jene, die nicht geantwortet haben, widerrufen oder einige andere Aktivitäten durchführen.  
  
- An diesem Punkt kann der Hostpeer eine Kollaborationssitzung mit allen eingeladenen Peers starten oder eine Anwendung mit der Kollaborationsinfrastruktur registrieren.  P2P-Anwendungen verwenden die Infrastruktur für die Peer-zu-Peer-Kollaboration und den <xref:System.Net.PeerToPeer.Collaboration>-Namespace, um die Kommunikation für Spiele, Bulletin Boards, Konferenzen und andere serverlose Anwendungen zu koordinieren.  
  
## <a name="peer-to-peer-networking-security"></a>Sicherheit von Peer-to-Peer-Netzwerken  

 In einer Active Directory-Domäne bieten Domänencontroller Kerberos-Authentifizierungsdienste an. In einer serverlosen Peer-Umgebung müssen die Peers ihre eigene Authentifizierung bereitstellen. Für das Peer-zu-Peer-Netzwerk kann jeder beliebige Knoten als Zertifizierungsstelle fungieren, wobei die Anforderung für ein Stammzertifikat in jedem vertrauenswürdigen Stammspeicher des Peers wegfällt. Die Authentifizierung wird unter Verwendung selbstsignierter Zertifikate, formatiert als x. 509-Zertifikate, bereitgestellt. Hierbei handelt es sich um Zertifikate, die von jedem Peer erstellt werden, der den öffentlichen Schlüssel/das private Schlüsselpaar und das Zertifikat, das mit dem privaten Schlüssel signiert ist, generiert. Das selbstsignierte Zertifikat wird zur Authentifizierung und zum Bereitstellen von Informationen über die Peer-Entität verwendet. Wie bei der X.509-Authentifizierung, verlässt sich die Peer-Netzwerkauthentifizierung auf eine Kette von Zertifikaten, die auf einen öffentlichen Schlüssel zurückführen, der als vertrauenswürdig eingestuft wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.PeerToPeer.Collaboration>
- [About the System.Net.PeerToPeer.Collaboration Namespace (Informationen zum System.NET.PeerToPeer.Kollaborations-Namespace)](about-the-system-net-peertopeer-collaboration-namespace.md)
