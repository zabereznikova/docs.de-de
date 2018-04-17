---
title: Zustand und Daten in Docker-Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 83094cd9a13d77f489df639096bb42b23ce152e7
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="state-and-data-in-docker-applications"></a>Zustand und Daten in Docker-Anwendungen

Ein primitiver Typ, der Container ist Unveränderlichkeit. Im Vergleich zu einem virtuellen Computer nicht Container nicht mehr als einem häufiger eintreten angezeigt. Ein virtuellen Computer möglicherweise nicht in verschiedenen Formen von inaktiver Prozesse überladene CPU oder einen Datenträger voll oder fehlerhaft gemeldet. Noch, wir erwarten, dass des virtuelle Computers verfügbar sein und RAID-Laufwerke sind inzwischen, um sicherzustellen, dass das Laufwerk Fehlern Daten zu verwalten.

Allerdings sind Container vorstellen, Instanzen von Prozessen. Ein Prozess verwalten nicht permanenten Status. Obwohl ein Container in seiner lokalen Speicher schreiben kann, entspräche vorausgesetzt, dass diese Instanz auf unbestimmte Zeit kann vorausgesetzt, dass eine einzelne Kopie Arbeitsspeicher dauerhaft ist. Sie sollten davon ausgehen, dass der Container, z. B. Prozesse, doppelt vorhanden sind, abgebrochen, oder, wenn mit einem Container Orchestrator verwaltet werden, sie verschoben werden können.

Docker verwendet eine Funktion, die als bezeichnet ein *overlay Dateisystem* aktualisiert Sie, einen Kopie-bei-Schreibvorgang-Prozess zu implementieren, die alle speichert Informationen in das Stammdateisystem eines Containers, im Vergleich zu dem ursprungsabbild auf dem es basiert. Diese Änderungen gehen verloren, wenn der Container anschließend aus dem System gelöscht wird. Ein Container besitzt aus diesem Grund nicht persistenten Speicher standardmäßig. Obwohl es möglich, den Zustand eines Containers zu speichern, wäre Entwerfen eines Systems, um diese in Konflikt mit dem Prinzip der Container-Architektur.

Zum Verwalten von permanenten Daten in Docker-Anwendungen stehen allgemeine Lösungen zur Verfügung:

-   [**Datenvolumes**](https://docs.docker.com/engine/tutorials/dockervolumes/) diese bereitstellen, auf dem Host wie soeben erwähnt.

-   [**Datenvolumecontainer**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) diese freigegebenen Speicher in Containern, die mit einer externen Container, der durchlaufen kann bereitstellen.

-   [**Volume-Plug-Ins**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) diese Volumes an Remotestandorten bereitstellen langfristige Dauerhaftigkeit bereitstellen.

-   **Remotedatenquellen** Beispiele umfassen SQL und NOSQL Datenbanken oder -Dienste wie Redis cache.

-   [**Azure-Speicher**](https://docs.microsoft.com/azure/storage/) dadurch verteilbarer Geo-Plattform als Dienst (PaaS) Speicher, und bietet das beste von Containern als langfristige Dauerhaftigkeit.

Datenvolumes sind speziell vorgesehen, Verzeichnisse in einem oder mehreren Containern, die umgehen der [Union Dateisystem](https://docs.docker.com/v1.8/reference/glossary#union-file-system). Datenvolumes dienen zum Verwalten von Daten, unabhängig von den Lebenszyklus des Containers. Docker löscht daher nie automatisch Volumes, wenn Sie einen Container zu entfernen und auch nicht werden "Sammeln von Garbage"-Volumes, die von einem Container nicht mehr verwiesen werden. Das Hostbetriebssystem können durchsuchen und bearbeiten die Daten in beliebigen Volumes frei, dies ist nur ein weiterer Grund für die Datenvolumes nur selten zu verwenden.

Ein [Volume Datencontainer](https://docs.docker.com/v1.8/userguide/dockervolumes/) stellt eine Verbesserung gegenüber regulären von Datenvolumes. Es ist im Wesentlichen eine ruhende Container, der eine oder mehrere Datenvolumes darin erstellt werden, (wie zuvor beschrieben) enthalten ist. Der Datenvolumecontainer bietet Zugriff auf Container von einem zentralen Bereitstellungspunkt aus. Der Vorteil dieser Methode des Zugriffs ist, dass sie den Speicherort der ursprünglichen Daten, machen dem Datencontainer logischen Bereitstellungspunkt abstrahiert. Darüber hinaus können den Zugriff auf die Container-Datenvolumen erstellt und zerstört werden, während die Daten in einem dedizierten Container persistent bleiben "Application"-Container.

Abbildung 4-5 zeigt, dass es sich bei regulären Docker Volumes auf Speicher aus den Containern selbst, aber innerhalb der physischen Host-Server-VM-Grenzen platziert werden können. *Docker Volumes nicht die Möglichkeit, ein Volume aus einem Host/Server-VM in eine andere verwendet haben*.

![](./media/image5.png)

Abbildung 4-5: Datenvolumes und externe Datenquellen für Container apps/Container

Aufgrund von nicht zum Verwalten von Daten, die gemeinsam von Containern, die auf separaten physischen Hosts ausgeführt werden können, wird empfohlen, dass keine Volumes für Geschäftsdaten zu verwenden, sofern der Docker-Host einer festen/VM, da bei Verwendung von Docker-Containern in einer Orchestrator Container werden erwartet, das Verschieben aus einem auf einen anderen Host, abhängig von den Optimierungen des Clusters ausgeführt werden.

Daher sind reguläre Datenvolumes einen guten Mechanismus zum Arbeiten mit Ablaufverfolgungsdateien, temporären Dateien oder alle ähnlichen Konzept, das die Datenkonsistenz Business nicht beeinflusst wird, wenn, oder wenn der Container auf mehreren Hosts verschoben werden.

Volume-Plug-ins wie [Flocker](https://clusterhq.com/flocker/) Daten auf allen Hosts in einem Cluster bereitstellen. Obwohl nicht alle Volume-Plug-ins gleichermaßen erstellt werden, bieten die Volume-Plug-ins in der Regel externalisierte zuverlässige persistenten Speicher in den Containern unveränderlichen.

Von Remotedatenquellen und wie SQL-Datenbank, DocumentDB oder eine remote-Cache wie Redis-Caches wäre identisch entwickeln, ohne den Container. Dies ist einer der bevorzugten und bewährten, Methoden zum Speichern von Geschäftsdaten-Anwendung.


>[!div class="step-by-step"]
[Vorherigen] (monolithischen applications.md) [weiter] (Soa-applications.md)
