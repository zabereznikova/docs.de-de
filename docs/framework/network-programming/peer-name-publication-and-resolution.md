---
title: Peernamenveröffentlichung und -auflösung
ms.date: 03/30/2017
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
ms.openlocfilehash: 4a0787972a61f5700d1e8728be96db8ef9ee749e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "64623199"
---
# <a name="peer-name-publication-and-resolution"></a>Peernamenveröffentlichung und -auflösung

## <a name="publishing-a-peer-name"></a>Veröffentlichen eines Peernamens  

 Ein Peer geht folgendermaßen vor, um eine neue PNRP-ID (Peer Name Resolution Protocol) zu veröffentlichen:  
  
- Er sendet PNRP-Veröffentlichungsnachrichten an seine Cachenachbarn (die Peers, die PNRP-IDs in der untersten Ebene des Caches registriert haben), um deren Caches zu starten.  
  
- Er wählt zufällige Knoten in der Cloud aus, die nicht seine Nachbarn sind, und sendet ihnen PNRP-Namensauflösungsanforderungen für seine eigene P2P-ID. Der damit gestartete Endpunktbestimmungsprozess startet die Caches von zufälligen Knoten in der Cloud mit der PNRP-ID des Veröffentlichungspeers.  
  
Knoten der Version 2 von PNRP veröffentlichen keine PNRP-IDs, wenn diese nur andere P2P-IDs auflösen. Der Registrierungswert „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1“ (Typ „REG_DWORD“) gibt an, dass Peers PNRP nur für die Namensauflösung und niemals für die Namensveröffentlichung verwenden. Dieser Registrierungswert kann auch über die Gruppenrichtlinien konfiguriert werden.  
  
## <a name="resolving-a-peer-name"></a>Auflösen eines Peernamens

 Der Suchvorgang nach anderen Peers in einem PNRP-Netzwerk oder einer PNRP-Cloud besteht aus zwei Phasen:  
  
1. Endpunktbestimmung  
  
2. und PNRP-ID-Auflösung  
  
 In der Phase der Endpunktbestimmung bestimmt ein Peer, der die PNRP-ID eines Diensts auf einem anderen Computer versucht aufzulösen, die IPv6-Adresse dieses Remotepeers.  Der Remotepeer ist derjenige, der die PNRP-ID des Computers oder des Diensts veröffentlicht hat oder damit verknüpft ist.  
  
 Nachdem bestätigt wurde, dass der Remoteendpunkt in der PNRP-Cloud registriert wurde, sendet der anfordernde Peer in der Phase der PNRP-ID-Auflösung an diesen Peerendpunkt eine Anforderung für die PNRP-ID des gewünschten Diensts. Der Endpunkt sendet eine Antwort, in der die PNRP-ID des Diensts bestätigt wird, sowie einen Kommentar und bis zu 4 KB zusätzliche Informationen, die der anfordernde Peer für die spätere Kommunikation verwenden kann. Ist der gewünschte Endpunkt z.B. ein Gamingserver, kann der zusätzliche Peernamendatensatz Informationen zum Spiel, zum Level des Spiels und zur aktuellen Anzahl der Spieler enthalten.  
  
 In der Phase der Endpunktbestimmung verwendet PNRP einen iterativen Prozess für die Suche nach dem Knoten, der die PNRP-ID veröffentlicht hat. Der Knoten, der die Auflösung ausführt, ist für die Kontaktaufnahme mit den Knoten verantwortlich, die der Ziel-PNRP-ID stückchenweise näherkommen.  
  
 Zur Durchführung der Namensauflösung in PNRP überprüft der Peer die Einträge in seinem eigenen Cache nach einem Eintrag, der mit der Ziel-PNRP-ID übereinstimmt. Hat er den Eintrag gefunden, sendet der Peer eine PNRP-Anforderungsnachricht an den Peer und wartet auf eine Antwort. Hat er keinen Eintrag für die PNRP-ID gefunden, sendet der Peer eine PNRP-Anforderungsnachricht an den Peer, dessen Eintrag der Ziel-PNRP-ID am ehesten entspricht. Der Knoten, der die PNRP-Anforderungsnachricht erhält, überprüft wiederum seinen eigenen Cache und führt die folgenden Schritte aus:  
  
- Wird die PNRP-ID gefunden, antwortet der angeforderte Endpunktpeer dem anfordernden Peer direkt.  
  
- Wird die PNRP-ID nicht gefunden und ist eine PNRP-ID im Cache der Ziel-PNRP-ID ähnlicher, sendet der angeforderte Peer eine Antwort an den anfordernden Peer. Diese Antwort enthält die IPv6-Adresse des Peers, dessen Eintrag stärker mit der Ziel-PNRP-ID übereinstimmt. Mithilfe der IP-Adresse aus der Antwort sendet der anfordernde Knoten eine weitere PNRP-Anforderungsnachricht an die IPv6-Adresse, die antworten und ihren Cache überprüfen soll.  
  
- Wird die PNRP-ID nicht gefunden und befindet sich im Cache keine PNRP-ID, die stärker mit der Ziel-PNRP-ID übereinstimmt, sendet der angeforderte Peer dem anfordernden Peer eine Antwort, in der diese Bedingung angegeben wird. Der anfordernde Peer wählt anschließend die nächstgelegene PNRP-ID aus.  
  
Der anfordernde Peer wiederholt diesen Vorgang mit aufeinanderfolgenden Iterationen, bis er den Knoten, der die PNRP-ID registriert hat, gefunden hat.  
  
 Innerhalb des <xref:System.Net.PeerToPeer>-Namespaces besteht eine m:n-Beziehung zwischen den <xref:System.Net.PeerToPeer.PeerName>- Datensätzen, die Endpunkte enthalten, und den PNRP-Clouds oder -Meshs, in denen sie kommunizieren. Bei doppelten oder veralteten Einträgen sowie bei mehreren Knoten mit demselben Peernamen können PNRP-Knoten aktuelle Informationen mithilfe der <xref:System.Net.PeerToPeer.PeerNameResolver>-Klasse abrufen. Die <xref:System.Net.PeerToPeer.PeerNameResolver>-Methoden verwenden einen einzelnen Peernamen, um die Perspektive für die Peernamendatensätze und Clouds auf eine 1:n-Beziehung zu vereinfachen. Diese Methode ähnelt einer Abfrage, die mit einer relationalen Tabellenverknüpfung ausgeführt wird. Nach erfolgreichem Abschluss gibt das Resolverobjekt eine <xref:System.Net.PeerToPeer.PeerNameRecordCollection> für den angegebenen Peernamen zurück.  Ein Peername kommt z.B. in allen Peernamendatensätzen der Sammlung nach Cloud geordnet vor. Dies sind die Instanzen des Peernamens, dessen Daten von einer PNRP-basierten Anwendung angefordert werden können.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.PeerToPeer>
