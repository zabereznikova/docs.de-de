---
title: Peerkanalszenarien
ms.date: 03/30/2017
ms.assetid: dae6e0f7-900c-45ee-8be9-3647698382fb
ms.openlocfilehash: c4c24a0bafa4f73760d02de6242a9ed438d7d60e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596876"
---
# <a name="peer-channel-scenarios"></a>Peerkanalszenarien
Die Peerkanal-APIs unterstützen die folgenden Entwicklungsszenarien:  
  
## <a name="publicationsubscription-messaging"></a>Veröffentlichungs-/Abonnement-Messaging  
 Unternehmen, die Veröffentlichungs-/Abonnementanwendungen erstellen (beispielsweise Börsenticker und Herausgeber von Nachrichtenüberschriften, Sportergebnissen und Wetterberichten), können Peerkanal für serverlose Anwendungen verwenden. Benutzer können beispielsweise die aktuellen Sportergebnisse abrufen, indem sie Mitglieder eines gemeinsamen Meshs (oder einer Gruppen von Clients) werden und die Vielzahl von aktuellen Spieldaten ohne Erhöhung der Serverauslastung weitergeben. Dies ermöglicht dem Datenanbieter das Bereitstellen einer höheren Servicequalität ohne beträchtliche Steigerung der Investitionen in serverbasierte Technologien.  
  
## <a name="collaboration"></a>Zusammenarbeit  
 Unabhängige Softwareanbieter können Anwendungen erstellen, mit denen Benutzer enge Gruppen für die Teilnahme an Peer-to-Peer-Aktivitäten erstellen können. Dies können beispielsweise gemeinsam bearbeitete Teamprojekte, die Freigabe von Bildern für den Freundeskreis oder Aktivitäten zum Planen einer Party sein. Normalerweise sind für diese Aktivitäten immer Server erforderlich; dank der Möglichkeit zur Verwendung von Offline-Zugriffsszenarien, die in einem herkömmlichen Server-Client-Modell nicht so einfach implementiert werden können, bietet Peerkanal jedoch eine kostengünstigere Methode.  
  
## <a name="distributed-processing-and-compute-clusters"></a>Verteilte Verarbeitung und Compute-Cluster  
 Compute-Cluster und verteilte Verarbeitung werden in der Regel für umfangreiche Berechnungen wie Finanz-/Wettermodelle und das Decodieren der menschlichen DNA verwendet. Normalerweise weisen dabei Server allen Clients im Berechnungscluster Aufgaben individuell zu. Diese Server können auch zusätzliche Forderungen stellen; z. B. müssen unter Umständen alle Aufgaben innerhalb einer bestimmten Zeit ausgeführt werden, sodass für jede Aufgabe mehr als ein Computer erforderlich ist. Darüber hinaus muss, wenn ein Client ausfällt, der eine Aufgabe ausführt, ein anderer Client diese Aufgabe übernehmen und ausführen können. Entsprechend müssen eventuell mehrere Clients die gleiche Aufgabe ausführen, um konsistente Ergebnisse sicherzustellen. Obwohl Server in der Lage sind, diesen Typ von Clientkoordinierung auszuführen, können Sie eine Peer-to-Peer-Lösung erstellen, in der die Clients eine Aufgabe erhalten, unabhängig die Serveranforderungen im Zusammenhang mit der Aufgabe bestimmen und mit einem Compute-Mesh bestimmen, wie diese Aufgabe ausgeführt wird.  
  
## <a name="gaming"></a>Spiele  
 Mit Peerkanal können Anwendungsentwickler serverlose Versionen ihrer Spiele erstellen, in denen Spielzüge nicht über einen zentralen Server, sondern durch einen Peer-to-Peer-Mechanismus übertragen und mit anderen Spielern synchronisiert werden. Für kleine unabhängige Softwareanbieter lassen sich so die Betriebskosten für das Bereitstellen, Warten und Bedienen von zentralen Servern einsparen. Mit einer Peer-to-Peer-Architektur entwickelte Spiele können über das Internet bzw. in drahtgebundenen oder drahtlosen lokalen Netzwerken gespielt werden. Sekundäre Spielaktivitäten wie Lobby und Chatten während des Spiels können mit einem Peer-to-Peer-Netzwerk entwickelt werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Peerkanalbegriffe](peer-channel-concepts.md)
