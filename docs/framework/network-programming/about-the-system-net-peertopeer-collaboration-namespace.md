---
title: Informationen zum System.NET.PeerToPeer.Collaboration-Namespace
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5d23fe51249df53b3874a8fd6fda60377f7366ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394042"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a>Informationen zum System.NET.PeerToPeer.Collaboration-Namespace
Der <xref:System.Net.PeerToPeer.Collaboration>-Namespace stellt Klassen und APIs bereit, die zum Implementieren von Aktivitäten der Peer-Zusammenarbeit mithilfe der Peer-zu-Peer-Zusammenarbeitsinfrastruktur verwendet werden.  
  
## <a name="classes"></a>Klassen  
 Die wichtigsten Klassen in der Implementierung einer Peer-zu-Peer-Zusammenarbeit sind folgende:  
  
-   Die <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, die zum Speichern von Peer-Kontakten verwendet werden kann.  
  
-   Die <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> für die Zusammenarbeit, z.B. ein Spiel, Chat-Client oder eine Konferenzlösung.  
  
-   Peers, die in einer Aktivität zusammenarbeiten.  Dieser Peers können als <xref:System.Net.PeerToPeer.Collaboration.PeerContact>-, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>- oder <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>-Objekte dargestellt werden.  
  
-   Die statische <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>-Klasse selbst, die angibt, welche Anwendungen verfügbar sind und welche Peers an ihnen teilnehmen.  
  
 Die <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A>-Methoden werden zum Einladen von Peers zu einer Zusammenarbeitssitzung verwendet.  Ein aufrufender Peer kann einen anderen Peer für Ereignisse abonnieren, die Updates von Anwendungen und Objekten, oder Anwesenheitsinformationen in Zusammenhang mit der Zusammenarbeitssitzung signalisieren. Anwesenheitsklassen geben an, ob eine <xref:System.Net.PeerToPeer.Collaboration.Peer> für die Zusammenarbeit zur Verfügung steht, und die <xref:System.Net.PeerToPeer.Collaboration.PeerScope>-Klasse wird verwendet, um anzugeben, wie viel Beteiligung für einen Peer zulässig ist: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global) <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe> (Subnetz) oder <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.  
  
 Eine Zusammenarbeitssitzung besteht aus vier Schritten:  
  
-   Ermittlung. Ermitteln oder veröffentlichen Sie Anwendungen, Peers und Anwesenheitsinformationen.  Suchen Sie z.B. andere Personen im lokalen Subnetz, die die gleichen Spiele installiert haben.  
  
-   Einladung. Senden und akzeptieren Sie sichere Einladungen, damit ein oder mehrere Remotepeers <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>-Sitzungen starten oder verknüpfen können.  
  
-   Kontaktverwaltung. Fügen Sie ermittelte Peers als Kontakt zu <xref:System.Net.PeerToPeer.Collaboration.ContactManager> hinzu.  
  
-   Kommunikation. Verwenden Sie die <xref:System.Net>-, <xref:System.Net.PeerToPeer>-APIs oder Peer Channel-Klassen der Windows Communication Foundation für Mehrparteienkommunikation, wenn Sie eine Kommunikation etabliert haben.  
  
 Z.B. startet der Hostpeer eine Zusammenarbeitssitzung und nutzt die <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A>-Methode, um einen Remotepeer und einen der lokalen Peers zum Contact Manager des Hostpeers hinzuzufügen.  Die drei Benutzer werden dann an ihren eigenen privaten Zusammenarbeitssitzungen teilnehmen.  
  
 Typische P2P-Anwendungen sind: Telefonkonferenzen für gemeinsame Notizen oder Whiteboards, serverlose Chat-Anwendungen, interaktive Ankündigungen und Onlinespielsitzungen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.PeerToPeer.Collaboration>
