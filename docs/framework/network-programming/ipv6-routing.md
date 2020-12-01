---
title: IPv6-Routing
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: 646eef4ec178472a99f60de4785fd53381296c3a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258334"
---
# <a name="ipv6-routing"></a>IPv6-Routing

Der flexible Routingmechanismus ist ein Vorteil von IPv6. Aufgrund der Art, auf die IPv4-Netzwerk-IDs zugeordnet werden, müssen große Routingtabellen von den Routern verwaltet werden, die sich in den Internetbackbones befinden. Diese Router müssen alle Routen kennen, um Pakete weiterzuleiten, die möglicherweise auf einen beliebigen Knoten im Internet weitergeleitet werden. IPv6 ermöglicht flexiblere Adressen durch seine Fähigkeit zum Aggregieren von Adressen und reduziert die Größe von Routingtabellen drastisch. In dieser neuen Adressarchitektur müssen zwischengeschaltete Router nur den lokalen Teil ihres Netzwerks verfolgen, um eine Nachricht korrekt weiterzuleiten.  
  
## <a name="neighbor-discovery"></a>Nachbarsuche  

 Im Folgenden finden Sie einige der Funktionen, die von der Nachbarsuche bereitgestellt werden:  
  
- Routersuche. Dadurch können Hosts lokale Router identifizieren.  
  
- Adressauflösung. Dadurch können Knoten eine Verbindungsschichtadresse für eine entsprechende Adresse für den nächsten Hop auflösen (ein Ersatz für das Address Resolution Protocol [ARP]).  
  
- Automatische Adresskonfiguration. Dadurch können Hosts automatisch standortlokale und globale Adressen konfigurieren.  
  
 Die Nachbarsuche verwendet das Internet Control Message-Protokoll für folgende IPv6-Nachrichten (ICMPv6):  
  
- Routerankündigungen. Werden von einem Router auf pseudo-periodischer Basis versendet oder als Antwort auf eine Routeranfrage. IPv6-Router verwenden Routerankündigungen, um ihre Verfügbarkeit, ihre Adresspräfixe und andere Parameter anzukündigen.  
  
- Routeranfrage. Werden von einem Host gesendet, um von den Routern auf einem Link eine sofortige Routerankündigung anzufordern.  
  
- Nachbaranfrage. Wird von Knoten für die Adressauflösung, die Erkennung doppelter Adressen oder die Überprüfung gesendet, ob ein Nachbar weiterhin erreichbar ist.  
  
- Nachbarankündigungen. Wird von Knoten gesendet, um auf eine Nachbaranfrage zu reagieren oder um Nachbarn über eine Änderung in der Verbindungsschichtadresse zu benachrichtigen.  
  
- Umleiten. Wird von Routern gesendet, um eine bessere Adresse für den nächsten Hop für ein bestimmtes Ziel eines Sendeknotens anzugeben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Internetprotokoll Version 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
