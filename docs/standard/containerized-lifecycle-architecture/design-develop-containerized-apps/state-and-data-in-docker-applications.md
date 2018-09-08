---
title: Zustand und Daten in Docker-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 78db191bdec4c25c11728d819d89eaaaff4bd7da
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44181614"
---
# <a name="state-and-data-in-docker-applications"></a>Zustand und Daten in Docker-Anwendungen

Ein primitiver Typ, der Container ist Unveränderlichkeit. Im Vergleich zu einem virtuellen Computer keine Container als häufiger eintreten nicht mehr angezeigt. Ein virtuellen Computer möglicherweise in verschiedenen Formen von inaktiver Prozesse, überladene CPU oder einen vollständigen oder fehlerhaften Datenträger. Noch wir erwarten, dass des virtuelle Computers verfügbar sein und RAID-Laufwerke sind in aller Munde, um sicherzustellen, dass Laufwerksfehlern Daten zu verwalten.

Allerdings sind Container vorstellen, Prozesse Instanzen sein. Ein Prozess verwalten nicht permanenten Status. Auch wenn ein Container für den lokalen Speicher schreiben kann, wäre vorausgesetzt, dass diese Instanz auf unbestimmte Zeit vorhanden ist gleichwertig, vorausgesetzt, dass eine einzelnen Kopie Arbeitsspeicher dauerhaft ist. Sie sollten davon ausgehen, dass der Container, z.B. Prozesse, dupliziert werden, wird abgebrochen, oder, wenn mit einem containerorchestrator verwaltet werden, sie verschoben werden können.

Docker verwendet die Funktion-ein *Dateisystem überlagern* einen Kopie-bei-Schreibvorgang-Prozess zu implementieren, die alle speichert Informationen auf dem Stammdateisystem der einen Container im Vergleich zum ursprünglichen Image auf dem es basiert aktualisiert. Diese Änderungen gehen verloren, wenn der Container anschließend aus dem System gelöscht wird. Ein Container, muss daher nicht beständigen Speicher benötigen standardmäßig. Obwohl es möglich, den Zustand eines Containers zu speichern, wäre in Konflikt mit dem Prinzip der Container-Architektur Entwerfen eines Systems Umgehung dieses Problems.

Um persistente Daten in Docker-Anwendungen zu verwalten, stehen gängige Lösungen:

-   [**Datenvolumes**](https://docs.docker.com/engine/tutorials/dockervolumes/) diese in den Host, wie soeben erwähnt eingebunden.

-   [**Datenvolumecontainer**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) diese freigegebenen Speicher in Containern, die über einen externen Container, mit der Hardwareinventurzyklus kann bieten.

-   [**Volume-Plug-Ins**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) diese Bereitstellen von Volumes an Remotestandorte, langfristige Persistenz bereitstellen.

-   **Remotedatenquellen** Beispiele umfassen die SQL- und NOSQL-Datenbanken oder zwischenspeicherdienste wie Redis.

-   [**Azure-Speicher**](https://docs.microsoft.com/azure/storage/) dadurch geografisch verteilbaren Plattform als Dienst (PaaS) Speicher, können Sie das beste von Containern als langfristige Persistenz.

Datenvolumes sind speziell vorgesehen, Verzeichnisse innerhalb eines oder mehrerer Container, die die umgehen der [Union Dateisystem](https://docs.docker.com/glossary/?term=Union%20file%20system). Datenvolumes dienen zum Verwalten von Daten, unabhängig von der Lebenszyklus des Containers. Docker löscht daher nie automatisch Volumes, wenn Sie einen Container zu entfernen, noch werden sie zu "Sammeln von Garbage"-Volumes, die von einem Container nicht mehr referenziert werden. Host-Betriebssystem können durchsuchen und bearbeiten die Daten in ein Volume frei, dies ist nur ein weiterer Grund für die Datenvolumes nur selten zu verwenden.

Ein [datenvolumecontainer](https://docs.docker.com/glossary/?term=volume) ist eine Verbesserung gegenüber regulären Datenvolumes. Es ist im Wesentlichen ein ruhende Container, die eine oder mehrere Datenvolumes darin erstellt werden, (wie zuvor beschrieben). Der Datenvolumecontainer bietet Zugriff auf Container von einem zentralen Bereitstellungspunkt aus. Der Vorteil dieser Methode des Zugriffs ist, dass sie den Speicherort der ursprünglichen Daten, sodass Datencontainer logische Bereitstellungspunkt abstrahiert. Darüber hinaus können "Application"-Container, die Zugriff auf das Datenvolumen der Container erstellt und zerstört werden, wobei die Daten dauerhaft in einem dedizierten Container werden sollen.

Abbildung 4-5 zeigt, dass reguläre Docker-Volumes in Storage, aus dem Container selbst aber innerhalb der physischen Grenzen des Host-Server-VM platziert werden können. *Docker-Volumes nicht die Möglichkeit, ein Volume von einem Host/Server-VM in ein anderes verwenden, haben*.

![](./media/image5.png)

Abbildung 4 – 5: Datenvolumes und externe Datenquellen für Container-apps/Container

Aufgrund der nicht zum Verwalten von Daten, die gemeinsam von Containern, die auf separaten physischen Hosts ausgeführt werden können, wird empfohlen, keine Volumes für Geschäftsdaten zu verwenden, wenn der Docker-Host mit einer festen Host/VM ist da bei Verwendung von Docker-Container in einem Orchestrator, Container sollten von einer bis zu einem anderen Host, abhängig von der Optimierungen, die vom Cluster ausgeführt werden, verschoben werden.

Daher sind die regulären Datenvolumes gute Mechanismen für die Arbeit mit Ablaufverfolgungsdateien, temporären Dateien oder alle ähnliches Konzept, das die Konsistenz von Geschäftsdaten nicht beeinflusst wird, wenn, oder wenn Ihr Container auf mehreren Hosts verschoben werden.

[Volume-Plug-ins](https://docs.docker.com/engine/extend/plugins_volume/) Daten auf allen Hosts in einem Cluster bereitstellen. Obwohl nicht alle Volume-Plug-ins gleichermaßen erstellt werden, bieten Volume-Plug-ins in der Regel externalisierte persistente und zuverlässige Speicherung von unveränderlichen Containern.

Remotedatenquellen und-Caches wie SQL-Datenbank, DocumentDB oder ein Remotecache wie Redis wäre identisch mit der Entwicklung ohne Container. Dies ist einer der bevorzugten und bewährten Methoden zum Speichern von Geschäftsanwendungsdaten.


>[!div class="step-by-step"]
[Zurück](monolithic-applications.md)
[Weiter](soa-applications.md)
