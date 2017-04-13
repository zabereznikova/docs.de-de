---
title: "PNRP-Caches | Microsoft Docs"
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
ms.assetid: 270068d9-1b6b-4eb9-9e14-e02326bb88df
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# PNRP-Caches
Cache des Peer Name Resolution\-Protokoll \(PNRP\) sind lokale Auflistungen der algorithmisch ausgewählten Peerendpunkte, die auf dem Peer verwaltet werden.  
  
## PNRP\-Cache\-Initialisierung  
 Um den PNRP\-Cachen oder Peer\-Namenseintrags\-Auflistung zu initialisieren, wenn ein Peerknoten oben beginnt, kann ein Knoten die folgenden Methoden verwenden:  
  
-   Persistente Cacheeinträge, die vorhanden waren, als der Knoten beendet wurde, werden vom Festplattenspeicher geladen.  
  
-   Wenn eine Anwendung die P2P\-Zusammenarbeitsinfrastruktur verwendet, sind Zusammenarbeitsinformationen im Kontakt\-Manager für diesen Knoten verfügbar.  
  
## Skalieren von Peer\-Namensauflösung mit einem Cache auf mehreren Ebenen  
 Um die Größen der PNRP\-Cachen gering zu halten, verwenden Peerknoten einen Cache mit mehreren Ebenen, in dem jede Ebene eine maximale Anzahl Einträge enthält.  Jede Ebene im Cache stellt einen um ein Zehntel kleineren Teil des PNRP\-ID\-Nummernraums \(2<sup>256</sup>\) dar.  Die niedrigste Ebene im Cache enthält eine lokal registrierte PNRP\-ID und andere PNRP\-IDs, die in numerischer Form genau sie sind.  Während ein Ebene des Cache mit maximal 20 Einträgen gefüllt wird, wird ein neues untergeordnetes erstellt.  Die maximale Anzahl der Ebenen im Cache ist in der Größenordnung von log10\(Gesamtzahl der PNRP\-IDs in der Cloud\).  Für eine globale Cloud mit 100 Millionen PNRP\-IDs, ist nicht mehr als 8 \(\=log10\(100.000.000\)\) Ebenen im Cache und in einer ähnlichen Anzahl der Hops, um eine PNRP\-ID während der Namensauflösung aufzulösen.  Dieser Mechanismus können eine verteilte Hashtabelle zu, für die eine beliebige PNRP\-ID aufgelöst werden kann, indem PNRP\-Anforderungnachrichten zum NEXT\-nähsten Peer weiterleitet, bis der Peer mit entsprechenden CPA gefunden wird.  
  
 Um sicherzustellen dass Auflösung abschließen kann, wenn ein Knoten einen Eintrag der niedrigsten Ebene des Cache hinzufügt, überschwemmt er eine Kopie des Eintrags in allen Knoten innerhalb des letzten Ebenen des Cache.  
  
 Die Cacheeinträge werden im Zeitverlauf aktualisiert.  Cacheeinträge, die veraltet sind, werden aus dem Cache entfernt.  Das Ergebnis ist, dass die verteilte Hashtabelle mit PNRP\-IDs auf Grundlage aktive Endpunkte ist, anders als DNS, in dem Adresssätze und das DNS\-Protokoll keine Garantie bereitstellen, dass der Knoten, der mit der Adresse zugeordnet wird, aktiv im Netzwerk befindet.  
  
## Andere PNRP\-Cachen  
 Ein weiterer persistenter Datenspeicher ist der lokale Cache.  Zusätzlich zu den anderen Objekten, die für PNRP\-Aktivität erforderlich sind, wird jedoch möglicherweise die Datensätze ein, die mit einer PNRP\-Cloud\- oder \-zusammenarbeitssitzung zugeordnet werden, die sicher zwischen alle Member der Cloud veröffentlicht und synchronisiert wird.  Dieser replizierte Speicher stellt die Ansicht der Gruppendaten dar, die dieselbe für alle Gruppenelemente sein sollten.  Technisch gesehen sind diese Objekte nicht Datensätze mit sich selbst, sondern Anwendung, vorhandenen, und Objektdaten enthalten für einen lokalen Cache.  Verwendung der PNRP\-Cloud wird sichergestellt, dass Objekte auf alle Knoten in der Zusammenarbeitssitzung oder im der PNRP\-Cloud weitergegeben werden.  Rekordreplikation zwischen Cloudmember verwendet SSL, um Verschlüsselung und Datenintegrität bereitzustellen.  
  
 Wenn ein Peer einer Cloud teilnimmt, wird sie nicht automatisch lokale Cachedaten vom Hostpeer, dem sie anfügen; und müssen zum Hostpeer abonnieren, um Updates in der Anwendung, im Vorhandensein und in den Objektdaten zu empfangen.  Nach der Erstsynchronisierung resynchronize Peers in regelmäßigen Abständen ihre replizierten Speicher, um sicherzustellen, dass alle Gruppenelemente einheitlich die gleiche Ansicht haben.  Die Zusammenarbeitssitzung oder Anwendungen innerhalb der Zusammenarbeitssitzung nehmen möglicherweise auch die gleiche Aufgabe erfüllt.  
  
 Nachdem eine Zusammenarbeitssitzung für eine Cloud gestartet wurde, können Anwendungen Peers registrieren und starten, ihre Informationen mithilfe der Sicherheit beim Veröffentlichen, die vom Cloudbereich definiert ist.  Wenn ein Peer einer Cloud teilnimmt, werden die Sicherheitsmechanismen für die Cloud den Peer angewendet und geben ihr einen Bereich, in dem teilnehmen.  Die Datensätze können im Kontext der Cloud dann sicher veröffentlicht werden.  Beachten Sie, dass Cloudbereich kann der nicht mit dem Zusammenarbeits\-Anwendungsbereich ist.  
  
 Peers können Interesse registrieren, an, Objekte aus anderen Peers zu empfangen.  Wenn ein Objekt aktualisiert wird, wird die Zusammenarbeits\-Anwendung benachrichtigt und das neue Objekt wird auf alle Abonnenten der Anwendung übergeben.  Beispielsweise kann ein Peer in einer Gruppenchat\-Anwendung Interesse registrieren, an, Anwendungsinformationen zu empfangen, die es alle Chatdatensätze als Anwendungsdaten sendet.  Dies ermöglicht die Bildschirmchataktivität innerhalb der Cloud.  
  
## Siehe auch  
 <xref:System.Net.PeerToPeer>