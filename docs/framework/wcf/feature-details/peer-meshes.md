---
title: Peer-Meshs
ms.date: 03/30/2017
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
ms.openlocfilehash: 62feb237dd4a8a471175e32363887376f7d86212
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272097"
---
# <a name="peer-meshes"></a>Peer-Meshs

Ein *Mesh* ist eine benannte Auflistung (ein verbundenes Diagramm) von Peer Knoten, die untereinander kommunizieren können und durch eine eindeutige Mesh-ID identifiziert werden. Jeder Knoten ist mit mehreren anderen Knoten verbunden. In einem gut verbundenen Mesh gibt es einen Pfad zwischen zwei beliebigen Knoten mit relativ wenigen Hops zwischen den Knoten an den weitesten Rändern des Netzes, und das Mesh bleibt verbunden, auch wenn einige Knoten oder Verbindungen ausfallen. Aktive Knoten im Netz veröffentlichen ihre Endpunkt Informationen mit einer entsprechenden Mesh-ID, sodass andere Peers Sie finden können.  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a>Eigenschaften eines Netzes, das mit Peerkanal erstellt wurde  
  
#### <a name="uniquely-identified"></a>Eindeutige Identifizierung  
  
- Jedes Netz ist durch eine eindeutige ID gekennzeichnet. Der Name des Meshs (die Mesh-ID) hat das gleiche Format wie der Domain Name System (DNS)-Hostname. Diese Mesh-ID muss für den vorgesehenen Client der Anwendung im Bereich des verwendeten Resolvers eindeutig sein. Allgemeine Namen wie "MyFamilysPeers" oder "KevinsPokerTable" können sich schnell mit anderen Benutzernamen überschneiden und unter Umständen unerwünschte Peerendpunktinformationen zurückgeben, was zu Datenschutzproblemen führen oder die Verbindungswartezeit erhöhen kann. Sie können eine eindeutige ID als Postfix zum Spitznamen für das Netz hinzufügen (beispielsweise "KevinsPokerTable90210").  
  
#### <a name="message-flooding"></a>Nachrichtenweiterleitung  
  
- Das Mesh ermöglicht die Weitergabe von Nachrichten von einem oder mehreren Absender an alle anderen Peerknoten im gleichen Mesh. Durch Peerknoten weitergeleitete Nachrichten verwenden Header, die im Namespace unter `http://schemas.microsoft.com/net/2006/05/peer` angegeben sind.  
  
#### <a name="optimized-connections"></a>Optimierte Verbindungen  
  
- Ein Peerkanalnetz wird beim Hinzufügen und Entfernen von Knoten automatisch angepasst. Damit wird sichergestellt, dass die Verbindung für alle Knoten gut und die Wahrscheinlichkeit für die Entstehung von Partitionen (voneinander isolierte Knotengruppen) gering ist. Verbindungen im Mesh werden auch auf der Grundlage aktueller Muster im Datenverkehr dynamisch optimiert, sodass die Nachrichtenwartezeit vom Absender zum Empfänger so kurz wie möglich ist.  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a>Gebräuchliche Netzwerkfunktionen, die von Peerkanal nicht bereitgestellt werden  

 Einige gebräuchliche Netzwerkfunktionen werden von Peerkanal nicht bereitgestellt. Zu diesen Funktionen, die alle auf „Peerkanal“ aufbauen können, gehören:  
  
- **Nachrichten Reihenfolge:** Nachrichten, die von einer einzelnen Quelle stammen, werden möglicherweise nicht an allen anderen Parteien in derselben Reihenfolge oder in der von der Quelle gesendeten Reihenfolge ankommen. Anwendungen, die erfordern, dass Nachrichten in einer bestimmten Reihenfolge übermittelt werden, müssen dies integrieren (z. B. durch Einschließen einer gleichmäßig zunehmenden ID in alle Nachrichten).  
  
- **Zuverlässiges Messaging:** Peerkanal umfasst keinen Mechanismus, um den Nachrichten Empfang durch alle Peers sicherzustellen. Um die Meldungsübermittlung zu garantieren, müssen Sie eine Zuverlässigkeitsebene schreiben, die Peerkanal übergeordnet ist.
