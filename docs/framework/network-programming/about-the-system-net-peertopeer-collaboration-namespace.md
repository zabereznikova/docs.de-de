---
title: "Informationen zum System.NET.PeerToPeer.Collaboration-Namespace | Microsoft Docs"
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
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# Informationen zum System.NET.PeerToPeer.Collaboration-Namespace
Der <xref:System.Net.PeerToPeer.Collaboration>\-Namespace stellt Klassen und APIs, die verwendet werden, um Peerzusammenarbeitsaktivitäten mithilfe der gleichberechtigt Zusammenarbeits\-Infrastruktur zu implementieren.  
  
## Klassen  
 Die wichtigsten Klassen, die in der Implementierung einer gleichberechtigt Zusammenarbeitsaktivität verwendet werden, sind:  
  
-   <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, die verwendet werden kann, um Peerkontakte zu speichern.  
  
-   In die <xref:System.Net.PeerToPeer.Collaboration.PeerApplication>, um, wie ein Spiel, ein Chatclient oder eine Konferenzprojektmappe Zusammenarbeit.  
  
-   Die Peers, die in einer Aktivität zusammenarbeiten werden.  Diese Peers können als <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> oder <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>\-Objekte dargestellt werden.  
  
-   Die statische <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>\-Klasse selbst, die angibt, welche Anwendungen verfügbar sind und welche Peers an ihnen teilnehmen.  
  
 Die <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A>\-Methoden werden verwendet, um Peers zu einer Zusammenarbeitssitzung einzuladen.  Ein aufrufende Peer kann an einen anderen Peer für Ereignisse abonnieren, die Updates der Anwendung, das Objekt oder zu den Anwesenheitsinformationen, die mit der Zusammenarbeitssitzung verknüpft werden signalisieren.  Vorhandenseinsklassen geben an, ob <xref:System.Net.PeerToPeer.Collaboration.Peer> für die Zusammenarbeit verfügbar ist, und die <xref:System.Net.PeerToPeer.Collaboration.PeerScope>\-Klasse wird verwendet, um anzugeben, wie viel Teilnahme für einen Peer zulässig: <xref:System.Net.PeerToPeer.Collaboration.PeerScope> \(global\), <xref:System.Net.PeerToPeer.Collaboration.PeerScope>, \(Subnetz\) oder <xref:System.Net.PeerToPeer.Collaboration.PeerScope>.  
  
 Eine Zusammenarbeitssitzung wird von vier Schritte enthalten:  
  
-   Suche.  Ermitteln Sie oder veröffentlichen Sie Anwendungen, und Anwesenheitsinformationen Peers.  Beispielsweise suchen Sie andere Personen auf dem lokalen Subnetz, die dieselben Spiele installiert haben.  
  
-   Einladung.  Senden Sie und akzeptieren Sie sichere Einladungen, damit Remote Peer\(s\) <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>\-Sitzungen beginnen oder verknüpfen.  
  
-   Wenden Sie sich an Verwaltung in Verbindung.  Add ermittelte Peers als Kontakt zu <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
-   Kommunikation.  Wenn Kommunikation eingerichtet ist, verwenden Sie das <xref:System.Net> APIs, die <xref:System.Net.PeerToPeer> APIs, oder Windows Communication Foundations\-Peer\-Channel Klassen für Mehrparteien\- Kommunikation.  
  
 Beispielsweise beginnt der Hostpeer eine Zusammenarbeitssitzung und verwendet die <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A>\-Methode, um einen Remotepeer und ihrer lokalen Peers dem Kontakt\-Manager des Hostpeers hinzuzufügen.  Die drei Benutzer nehmen dann an ihren eigenen privaten Zusammenarbeitssitzung beteiligt.  
  
 Typische P2P\-Anwendungen sind: Telefonkonferenzen für das leichtere Hinweis\-Nehmen oder das Whiteboarding, serverless Chat\-Anwendungen, interaktive Ankündigungen und online Spielsitzungen.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer.Collaboration>