---
title: PNRP-Caches
ms.date: 03/30/2017
ms.assetid: 270068d9-1b6b-4eb9-9e14-e02326bb88df
ms.openlocfilehash: 6f45b6d829867d830a9a10acf11e8456ba65d29e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263216"
---
# <a name="pnrp-caches"></a>PNRP-Caches

PNRP-Caches (Peer Name Resolution-Protokoll) sind lokale Sammlungen algorithmisch ausgewählter Peerendpunkte, die auf dem Peer verwaltet werden.  
  
## <a name="pnrp-cache-initialization"></a>Initialisieren des PNRP-Caches  

 Der PNRP-Cache oder die Sammlung des Peernamendatensatzes kann beim Start eines Peerknotens mit den folgenden Methoden initialisiert werden:  
  
- Dauerhafte Cacheeinträge, die beim Schließen des Knotens vorhanden waren, werden aus dem Festplattenspeicher geladen.  
  
- Verwendet eine Anwendung die P2P-Zusammenarbeitsinfrastruktur, sind die Zusammenarbeitsinformationen für diesen Knoten im Contact Manager verfügbar.  
  
## <a name="scaling-peer-name-resolution-with-a-multi-level-cache"></a>Skalieren des PNRP mithilfe eines Caches mit mehreren Ebenen  

 Damit die PNRP-Caches so klein wie möglich bleiben, verwenden Peerknoten einen Cache mit mehreren Ebenen, in dem jede Ebene eine maximale Anzahl von Einträgen enthält. Jede Ebene des Caches stellt einen um ein Zehntel kleineren Teil des PNRP-ID-Nummernbereichs dar (2<sup>256</sup>). Die niedrigste Ebene des Caches enthält eine lokal registrierte PNRP-ID sowie weitere PNRP-IDs, die ihr numerisch ähnlich sind. Sobald eine Ebene des Caches mit den maximal möglichen 20 Einträgen gefüllt ist, wird eine neue niedrigere Ebene erstellt. Die maximale Anzahl von Ebenen im Cache liegt bei etwa log10 (Gesamtzahl der PNRP-IDs in der Cloud). Für eine globale Cloud mit 100 Millionen PNRP-IDs sind beispielsweise nicht mehr als 8 (= log10(100.000.000)) Ebenen im Cache vorhanden sowie eine vergleichbare Anzahl von Hops, um eine PNRP-ID während der Namensauflösung aufzulösen. Dieser Mechanismus ermöglicht eine verteilte Hashtabelle, für die eine beliebige PNRP-ID aufgelöst werden kann, indem PNRP-Anforderungsnachrichten an den nächstgelegenen Peer weitergeleitet werden, bis der Peer mit der entsprechenden CPA gefunden ist.  
  
 Damit die Auflösung auch sicher abgeschlossen werden kann, leitet ein Knoten beim Hinzufügen eines Eintrags in die unterste Ebene seines Caches jedes Mal eine Kopie des Eintrags an alle Knoten innerhalb der letzten Ebene des Caches weiter.  
  
 Die Cacheeinträge werden mit der Zeit aktualisiert. Veraltete Cacheeinträge werden aus dem Cache entfernt. Dadurch basiert die verteilte Hashtabelle mit PNRP-IDs auf aktiven Endpunkten. Im Gegensatz dazu garantieren die Adresseinträge und das DNS-Protokoll in DNS nicht, dass der mit der Adresse verknüpfte Knoten im Netzwerk aktiv ist.  
  
## <a name="other-pnrp-caches"></a>Weitere PNRP-Caches  

 Ein weiterer dauerhafter Datenspeicher ist der lokale Cache.  Neben den anderen für PNRP-Aktivität erforderlichen Objekten kann er die mit einer PNRP-Cloud oder Zusammenarbeitssitzung verknüpften Datensätze enthalten. Diese werden sicher veröffentlicht und zwischen allen Mitgliedern der Cloud synchronisiert. Dieser replizierte Speicher stellt die Ansicht der Gruppendaten dar, die für alle Gruppenmitglieder identisch sein sollte. Technisch gesehen sind diese Objekte eigentlich keine Einträge, sondern vielmehr Anwendungs-, Anwesenheits- und Objektdaten, die für einen lokalen Cache bestimmt sind. Durch die Verwendung der PNRP-Cloud wird sichergestellt, dass die Objekte an alle Knoten der Zusammenarbeitssitzung oder der PNRP-Cloud weitergegeben werden.  Für die Replikation von Datensätzen zwischen Cloudmitgliedern wird SSL verwendet, um Verschlüsselung und Datenintegrität zu gewährleisten.  
  
 Wenn ein Peer einer Cloud beitritt, erhält er vom Hostpeer, dem er angefügt ist, nicht automatisch Daten aus dem lokalen Cache. Er muss den Hostpeer abonnieren, um Updates zu Anwendungs-, Anwesenheits- und Objektdaten zu erhalten. Nach der anfänglichen Synchronisierung synchronisieren Peers in regelmäßigen Abständen ihre replizierten Speicher neu, um sicherzustellen, dass alle Gruppenmitglieder über dieselbe Ansicht verfügen.  Die Zusammenarbeitssitzung bzw. Anwendungen innerhalb der Zusammenarbeitssitzung führen möglicherweise auch die gleiche Funktion aus.  
  
 Nachdem eine Zusammenarbeitssitzung für eine Cloud gestartet wurde, können Anwendungen Peers registrieren und damit beginnen, ihre Informationen mithilfe der im Cloudbereich definierten Sicherheit zu veröffentlichen. Wenn ein Peer einer Cloud beitritt, werden die Sicherheitsmechanismen für die Cloud auf den Peer angewendet. Er erhält einen Gültigkeitsbereich, in dem er sich beteiligen soll.  Seine Datensätze können anschließend innerhalb des Gültigkeitsbereichs der Cloud sicher veröffentlicht werden. Beachten Sie, dass der Gültigkeitsbereich der Cloud und der Gültigkeitsbereich der Zusammenarbeitsanwendung möglicherweise nicht identisch sind.  
  
 Peers können Interesse am Empfang von Objekten von anderen Peers registrieren. Wenn ein Objekt aktualisiert wird, wird die Zusammenarbeitsanwendung benachrichtigt und das neue Objekt an alle Abonnenten der Anwendung übergeben. Ein Peer in einer Gruppenchatanwendung kann z.B. Interesse an Anwendungsinformationen registrieren, wodurch er alle Chatdatensätze als Anwendungsdaten erhält.  Dadurch kann er die Chataktivität in der Cloud überwachen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.PeerToPeer>
