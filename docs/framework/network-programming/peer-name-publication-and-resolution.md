---
title: "Peernamenver&#246;ffentlichung und -aufl&#246;sung | Microsoft Docs"
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
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Peernamenver&#246;ffentlichung und -aufl&#246;sung
## Veröffentlichen eines Peer\-Namens  
 Um eine neue PNRP\-ID zu veröffentlichen, führt ein Peer Folgendes aus:  
  
-   Sendet PNRP\-Veröffentlichungsmeldungen den Cachenachbarn \(die Peers, die PNRP\-IDs in der untersten Ebene des Cache registriert haben\), um ihre Cache anzugeben.  
  
-   Wählt zufällige Knoten in der Cloud, die nicht ihre Nachbarn sind aus und sendet sie PNRP\-Namensauflösungsersuchen seine eigene P2P\-Identifikation  Der resultierende Endpunktbestimmungsprozess sät die Cache von zufälligen Knoten in der Cloud mit der PNRP\-ID des Veröffentlichungspeers.  
  
 Knoten PNRP\-Version 2 nicht PNRP\-IDs veröffentlichen, wenn sie nur andere P2P\-IDs auflösen.  Der Registrierungswert HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PeerNet\\PNRP\\IPV6\-Global\\SearchOnly\=1 \(REG\_DWORD\-Typ\) gibt an, dass Peers nur PNRP für Namensauflösung verwenden, nie für Nameveröffentlichung an.  Dieser Registrierungswert kann auch von Gruppenrichtlinien konfiguriert werden.  
  
## Auflösen eines Peernamens  
 Andere Peers in PNRP Lokalisieren, vernetzen Sie, oder Cloud ist ein Prozess, der von zwei Phasen besteht:  
  
1.  Endpunkt\-Bestimmung  
  
2.  PNRP\-ID\-Auflösung  
  
 In der Endpunktbestimmungsphase bestimmt Peer, der versucht, das Problem zu beheben, die PNRP\-ID eines Diensts auf einem anderen Computer die IPv6\-Adresse dieses den Peers.  Der Remotename Peer ist der, der veröffentlichte, oder ist, die PNRP\-ID des Computers oder Dienst zugeordnet.  
  
 Nach dem bestätigt hat, dass der Endpunkt Remote in die PNRP\-Cloud registriert wurde, sendet der anfordernde Peer in der PNRP\-ID\-Auflösungsphase eine Anforderung an diesem Peerendpunkt für die PNRP\-ID des gewünschten Diensts.  Der Endpunkt sendet eine Antwort, die die PNRP\-ID des Diensts, des Kommentars und auf 4 KB zusätzlichen Informationen bestätigt, die der anfordernden Peer für zukünftige Kommunikation verwenden kann.  Wenn der gewünschte Endpunkt ein Spielserver ist, können die zusätzlichen Peernamenseintragsdaten Informationen über das Spiel, das Ausmaß des Spiels und die aktuelle Anzahl von Playern enthalten.  
  
 In der Endpunktbestimmungsphase verwendet PNRP einen iterativen Prozess zum Suchen des Knotens, der die PNRP\-ID veröffentlichte, in der der Knoten, der die Auflösung ausführt, für das In Kontaktaufnahme mit Knoten zuständig ist, die nacheinander näher an der Ziel PNRP\-Identifikation sind  
  
 Um Namensauflösung in PNRP auszuführen, überprüft der Peer die Einträge in seinem eigenen Cache für einen Eintrag der die Ziel PNRP\-Identifikation übereinstimmt  Wenn er gefunden wird, sendet der Peer eine PNRP\-Anforderungnachricht den Peer und Wartung eine Antwort.  Wenn ein Eintrag für die PNRP\-ID nicht gefunden wird, sendet der Peer eine PNRP\-Anforderungnachricht den Peer, der dem Eintrag entspricht, der eine PNRP\-ID verfügt, die am besten mit Ziel PNRP\-Identifikation übereinstimmt  Der Knoten, der die PNRP\-Anforderungnachricht erhält, überprüft den eigenen Cache und führt Folgendes aus:  
  
-   Wenn die PNRP\-ID gefunden wird, antwortet der angeforderte Endpunktpeer direkt auf der anfordernde Peer.  
  
-   Wenn die PNRP\-ID nicht gefunden wird und eine PNRP\-ID im Cache näher an der Ziel PNRP\-ID ist, sendet der angeforderte Peer eine Antwort an den anfordernden Peer, der die IPv6\-Adresse des Peers enthält, der den Eintrag mit einer PNRP\-ID darstellt, dass genauer die Ziel PNRP\-Identifikation übereinstimmt  Verwenden der IP\-Adresse in der Antwort, sendet der anfordernden Knoten eine andere PNRP\-Anforderungnachricht zur IPv6\-Adresse, um zu reagieren oder den Cache zu überprüfen.  
  
-   Wenn die PNRP\-ID nicht gefunden wird und keine PNRP\-ID in dem Cache vorhanden ist, der näher an der Ziel PNRP\-ID ist, sendet der angeforderte Peer der anfordernde Peer eine Antwort, die diese Bedingung angibt.  Der anfordernde Peer wählt dann die NEXT\-nähste PNRP\-Identifikation aus  
  
 Der anfordernde Peer setzt diesen Vorgang mit aufeinander folgenden Iterationen fort und schließlich sucht den Knoten, der die PNRP\-Identifikation registrierte  
  
 Innerhalb des <xref:System.Net.PeerToPeer>\-Namespace gibt es eine m: n\-Beziehung zwischen den <xref:System.Net.PeerToPeer.PeerName> Datensätzen, die Endpunkte und PNRP\-Clouds oder \-Gitter enthalten, in denen sie kommunizieren.  Wenn es doppelte oder veraltete Einträge oder mehrere Knoten mit dem gleichen Peernamen gibt, können PNRP\-Knoten aktuelle Informationen mithilfe von <xref:System.Net.PeerToPeer.PeerNameResolver>\-Klasse erhalten.  Die <xref:System.Net.PeerToPeer.PeerNameResolver>\-Methoden verwenden einen einzelnen Peernamen, um die Perspektive Namenseinträgen mit einen zu Peer\-zu\-vielen Peers und den gleichen einem Peer zu vielen Clouds zu vereinfachen.  Dies ist mit einer Abfrage vergleichbar, die mithilfe eines RelationalTabelle Join ausgeführt wird.  Nach erfolgreichem Abschluss gibt das Resolverobjekt <xref:System.Net.PeerToPeer.PeerNameRecordCollection> für den angegebenen Peernamen zurück.  Ein Peername in allen Peernamenseinträgen in der Auflistung auftreten, sortiert nach Cloud.  Dies sind die Instanzen des Peernamens, dessen unterstützende möglicherweise von Daten durch eine PNRP\-basierte Anwendung angefordert wird.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer>