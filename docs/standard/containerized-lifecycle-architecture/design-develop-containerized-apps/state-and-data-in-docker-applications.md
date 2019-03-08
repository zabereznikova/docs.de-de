---
title: Zustand und Daten in Docker-Anwendungen
description: Erfahren Sie, die verfügbare Option Status in containeranwendungen zu speichern.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 30dde3ce44aa61fff3fad1841ae4a8b941573877
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678080"
---
# <a name="state-and-data-in-docker-applications"></a>Zustand und Daten in Docker-Anwendungen

In den meisten Fällen können Sie sich einen Container als Instanz eines Prozesses vorstellen. Ein Prozess behält keinen persistenten Zustand bei. Während ein Container für den lokalen Speicher schreiben kann, wird vorausgesetzt, dass eine Instanz auf unbestimmte Zeit vorhanden ist, wie die Annahme, dass ein einzelner Speicherort im Arbeitsspeicher dauerhaft ist. Containerimages, z.B. Prozesse, sollte angenommen werden, dass mehrere Instanzen haben und, das sie irgendwann abgebrochen werden; Wenn sie mit einem containerorchestrator verwaltet werden, sollte davon ausgegangen, dass sie von einem Knoten oder virtuellen Computer auf einen anderen verschoben werden können.

Die folgenden Lösungen werden verwendet, um persistente Daten in Docker-Anwendungen zu verwalten:

Über den Docker-Host als [Docker-Volumes](https://docs.docker.com/engine/admin/volumes/):

- **Volumes** werden in einem Bereich des Hostdateisystems gespeichert, der von Docker verwaltet wird.

- **Binden Sie Bereitstellungen** können zu einem beliebigen Ordner in das Dateisystem Host zuordnen, damit Zugriff kann nicht aus einem Docker-Prozess gesteuert werden und kann ein Sicherheitsrisiko darstellen, wie ein Container Zugriff auf vertrauliche OS-Ordner konnte.

- **Einbindungen über tmpfs** sind ähnlich wie virtuelle Ordner, die nur im Arbeitsspeicher des Hosts vorhanden sind und nie in das Dateisystem geschrieben werden.

Über den Remotespeicher:

- [Azure-Speicher](https://azure.microsoft.com/documentation/services/storage/) bietet geografisch verteilbaren Speicher, eine gute Lösung für langfristige Persistenz für Container bereitstellen.

- Relationale Remotedatenbanken wie [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database/), NoSQL-Datenbanken wie [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction), oder zwischenspeicherdienste wie [Redis](https://redis.io/).

Über den Docker-Container:

- Docker bietet ein Feature mit dem Namen *Overlay File System* (Dateisystem überlagern). Dieses Feature implementiert, eine Kopie-bei-Schreibvorgang-Aufgabe, speichert die Informationen auf das Stammdateisystem des Containers aktualisiert wird. Diese Informationen zeigt"auf" das Originalbild, die auf dem der Container basiert. Wenn der Container aus dem System gelöscht wird, gehen diese Änderungen verloren. Aus diesem Grund Es ist, zwar möglich, den Zustand eines Containers in seinem lokalen Speicher zu speichern würde Entwerfen eines Systems basierend auf dieser Funktion mit der Prämisse des Container-Entwurf in Konflikt stehen die standardmäßig zustandslos ist.

- Docker Volumes ist jedoch jetzt die bevorzugte Methode zum Behandeln von lokaler Daten in Docker. Wenn Sie weitere Informationen zum Speicher in Containern benötigen, überprüfen Sie auf [Docker-Speichertreiber](https://docs.docker.com/engine/userguide/storagedriver/) und [über Images, Container und Speichertreiber](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).

Im folgenden finden weiteren Details zu diesen Optionen.

**Volumes** sind Verzeichnisse, die vom Hostbetriebssystem den Verzeichnissen in Containern zugeordnet werden. Wenn Code im Container Zugriff auf das Verzeichnis hat, ist dies ein Zugriff auf ein Verzeichnis auf dem Hostbetriebssystem. Dieses Verzeichnis ist nicht an die Lebensdauer des Containers selbst gebunden, und es wird von Docker verwaltet und von der Kernfunktionalität des Hostcomputers isoliert. Deshalb sind diese Datenvolumes dazu entworfen, Daten unabhängig von der Lebensdauer des Containers beizubehalten. Wenn Sie einen Container oder ein Image aus dem Docker-Host löschen, werden die persistenten Daten im Datenvolume nicht gelöscht.

Volumes können benannt oder anonym sein (letzteres ist die Standardeinstellung). Benannte Volumes sind eine Weiterentwicklung von **Datenvolumecontainern** und vereinfachen die gemeinsame Nutzung von Daten durch Container. Datenträger unterstützen auch Volumetreiber, mit denen Sie zum Speichern von Daten auf Remotehosts, neben anderen Optionen.

**Binden Sie Bereitstellungen** waren lange Zeit verfügbar und ermöglichen die Zuordnung von einem beliebigen Ordner in einen Bereitstellungspunkt in einem Container. Einbindungen über „Bind“ weisen mehr Einschränkungen als Volumes sowie einige erhebliche Sicherheitsprobleme auf, daher sind Volumes die empfohlene Option.

**`tmpfs` bindet** sind virtuelle Ordner, die nur in den Arbeitsspeicher des Hosts live und nie in das Dateisystem geschrieben werden. Sie sind schnell und sicher, verbrauchen aber Arbeitsspeicher und sind nur für nicht persistente Daten vorgesehen.

Wie in Abbildung 4-5 gezeigt, können reguläre Docker-Volumes außerhalb der Container selbst aber innerhalb der physischen Grenzen des Hostservers oder der VM gespeichert werden. Docker-Container können jedoch nicht von einem Hostserver oder einer VM auf ein Volume zugreifen. Anders gesagt: Bei diesen Volumes ist es nicht möglich, Daten zu verwalten, die von auf verschiedenen Docker-Hosts ausgeführten Containern gemeinsam verwendet werden. Dieses Szenario ließe sich allerdings mit einem Volumetreiber umsetzen, der Remotehosts unterstützt.

![Volumes können von Containern gemeinsam genutzt werden, allerdings nur auf demselben Host, es sei denn, Sie verwenden einen Remotetreiber, der Remotehosts unterstützt. ](./media/image5.png)

**Abbildung 4-5**. Volumes und externe Datenquellen für containerbasierte Anwendungen

Darüber hinaus können Docker-Container möglicherweise zwischen Hosts verschoben werden, wenn sie von einem Orchestrator verwaltet werden. Dies hängt von den vom Cluster durchgeführten Optimierungen ab. Aus diesem Grund wird nicht empfohlen, Datenvolumes für Geschäftsdaten zu verwenden. Aber sie sind ein guter Mechanismus zur Bearbeitung von Ablaufverfolgungsdateien, temporären Dateien arbeiten, oder ähnlich, die hat keine Auswirkung auf die Konsistenz von Geschäftsdaten.

Tools für **Remotedatenquellen und -caches** wie Azure SQL-Datenbank, Azure Cosmos DB oder ein Remotecache wie Redis können in Containeranwendungen auf die gleiche Weise verwendet werden wie bei der Entwicklung ohne Container. Dies ist eine bewährte Möglichkeit zum Speichern von Geschäftsanwendungsdaten.

**Azure Storage.** Business-Daten müssen in der Regel in externen Ressourcen oder Datenbanken wie Azure Storage befinden. Azure Storage bietet die folgenden Dienste in der Cloud:

- Blob Storage speichert unstrukturierte Objektdaten. Ein Blob kann jeder Text- oder Binärdatentyp sein, z.B. Dokumenten- oder Mediendaten (Bilder, Audio- und Videodateien). Blob Storage wird auch als Object Storage bezeichnet.

- File Storage bietet freigegebenen Speicher für Legacyanwendungen unter Verwendung des SMB-Standardprotokolls. Azure Virtual Machines und Clouddienste können Dateidaten mithilfe bereitgestellter Freigaben für mehrere Anwendungskomponenten freigeben. Auf lokale Anwendungen können Dateidaten in einer Freigabe über die Dateidienst-REST-API zugreifen.

- File Storage speichert strukturierte Datasets. File Storage ist ein NoSQL-Schlüsselattributdatenspeicher, der schnelle Entwicklung sowie den schnellen Zugriff auf große Datenmengen ermöglicht.

**Relationale Datenbanken und NoSQL-Datenbanken.** Es gibt verschiedene Auswahlmöglichkeiten für externe Datenbanken, angefangen bei relationalen Datenbanken wie SQL Server, PostgreSQL, Oracle oder NoSQL-Datenbanken wie Azure Cosmos DB, MongoDB usw. Diese Datenbanken werden nicht weiter als Teil dieses Handbuchs erläutert werden, da sie einem anderen Thema vollständig sind.

>[!div class="step-by-step"]
>[Zurück](monolithic-applications.md)
>[Weiter](soa-applications.md)
