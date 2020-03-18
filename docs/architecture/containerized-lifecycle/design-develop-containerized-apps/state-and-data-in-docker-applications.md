---
title: Zustand und Daten in Docker-Anwendungen
description: Lernen Sie die verfügbare Option zum Speichern des Status in containerbasierten Anwendungen kennen.
ms.date: 02/15/2019
ms.openlocfilehash: b2368efb0eff2bdce48b77b2addcc4de89822c74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394644"
---
# <a name="state-and-data-in-docker-applications"></a>Zustand und Daten in Docker-Anwendungen

In den meisten Fällen können Sie sich einen Container als Instanz eines Prozesses vorstellen. Ein Prozess behält keinen persistenten Zustand bei. Während ein Container in den lokalen Speicher schreiben kann, gleicht die Annahme, dass eine Instanz auf unbestimmte Zeit vorhanden ist, der Annahme, dass ein Speicherort im Arbeitsspeicher dauerhaft ist. Für Containerimages, z.B. Prozesse, sollte angenommen werden, dass sie über mehrere Instanzen verfügen und irgendwann abgebrochen werden. Wenn sie mit einem Containerorchestrator verwaltet werden, kann man davon ausgehen, dass sie von einem Knoten oder VM in einen anderen verschoben werden können.

Die folgenden Lösungen werden verwendet, um persistente Daten in Docker-Anwendungen zu verwalten:

Über den Docker-Host als [Docker-Volumes](https://docs.docker.com/engine/admin/volumes/):

- **Volumes** werden in einem Bereich des Hostdateisystems gespeichert, der von Docker verwaltet wird.

- **Einbindungen über „Bind“** können jedem Ordner im Hostdateisystem zugeordnet werden, sodass der Zugriff nicht von einem Docker-Prozess gesteuert werden kann – dies wäre ein Sicherheitsrisiko, weil ein Container auf vertrauliche Betriebssystemordner zugreifen könnte.

- **Einbindungen über tmpfs** sind ähnlich wie virtuelle Ordner, die nur im Arbeitsspeicher des Hosts vorhanden sind und nie in das Dateisystem geschrieben werden.

Über den Remotespeicher:

- [Azure Storage](https://azure.microsoft.com/documentation/services/storage/), stellt geografisch verteilbaren Speicher und eine geeignete Lösung für langfristige Persistenz für Containern bereit.

- Relationale Remotedatenbanken wie die [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database/), NoSQL-Datenbanken wie [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) oder Zwischenspeicherdienste wie [Redis](https://redis.io/).

Über den Docker-Container:

- Docker bietet ein Feature mit dem Namen *Overlay File System* (Dateisystem überlagern). Durch dieses Feature wird ein copy-on-write-Task (Bei Schreibvorgang kopieren) implementiert, der aktualisierte Informationen in das Stammdateisystem des Containers speichert. Diese Informationen „liegen oberhalb“ des ursprünglichen Images, auf dem der Container basiert. Wenn der Container aus dem System gelöscht wird, gehen diese Änderungen verloren. Aus diesem Grund ist es zwar möglich, den Zustand eines Containers in seinem lokalen Speicher zu speichern, doch das Entwerfen eines Systems auf der Grundlage dieses Features würde mit der Prämisse des Containerdesigns kollidieren, das standardmäßig zustandslos ist.

- Docker-Volumes stellen aber mittlerweile das bevorzugte Verfahren zum Behandeln von lokalen Daten in Docker dar. Wenn Sie weitere Informationen zum Speichern in Containern benötigen, lesen Sie [Docker storage drivers](https://docs.docker.com/engine/userguide/storagedriver/) (Docker-Speichertreiber) und [About images, containers, and storage drivers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/) (Über Images, Container und Speichertreiber).

Nachfolgend finden Sie weitere Details zu diesen Optionen.

**Volumes** sind Verzeichnisse, die vom Hostbetriebssystem den Verzeichnissen in Containern zugeordnet werden. Wenn Code im Container Zugriff auf das Verzeichnis hat, ist dies ein Zugriff auf ein Verzeichnis auf dem Hostbetriebssystem. Dieses Verzeichnis ist nicht an die Lebensdauer des Containers selbst gebunden, und es wird von Docker verwaltet und von der Kernfunktionalität des Hostcomputers isoliert. Deshalb sind diese Datenvolumes dazu entworfen, Daten unabhängig von der Lebensdauer des Containers beizubehalten. Wenn Sie einen Container oder ein Image aus dem Docker-Host löschen, werden die persistenten Daten im Datenvolume nicht gelöscht.

Volumes können benannt oder anonym sein (letzteres ist die Standardeinstellung). Benannte Volumes sind eine Weiterentwicklung von **Datenvolumecontainern** und vereinfachen die gemeinsame Nutzung von Daten durch Container. Volumes unterstützen auch Volumetreiber, mit denen Sie u.a. Daten auf Remotehosts speichern können.

**Einbindungen über „Bind“** sind schon lange verfügbar und ermöglichen die Zuordnung jedes Ordners zu einem Bereitstellungspunkt in einem Container. Einbindungen über „Bind“ weisen mehr Einschränkungen als Volumes sowie einige erhebliche Sicherheitsprobleme auf, daher sind Volumes die empfohlene Option.

**Einbindungen über `tmpfs`** sind virtuelle Ordner, die nur im Arbeitsspeicher des Hosts vorhanden sind und nie in das Dateisystem geschrieben werden. Sie sind schnell und sicher, verbrauchen aber Arbeitsspeicher und sind nur für nicht persistente Daten vorgesehen.

Wie in Abbildung 4-5 gezeigt, können reguläre Docker-Volumes außerhalb der Container selbst aber innerhalb der physischen Grenzen des Hostservers oder der VM gespeichert werden. Docker-Container können jedoch nicht von einem Hostserver oder einer VM auf ein Volume zugreifen. Anders gesagt: Bei diesen Volumes ist es nicht möglich, Daten zu verwalten, die von auf verschiedenen Docker-Hosts ausgeführten Containern gemeinsam verwendet werden. Dieses Szenario ließe sich allerdings mit einem Volumetreiber umsetzen, der Remotehosts unterstützt.

![Abbildung, die die Docker-Volumes zeigt, die außerhalb von Containern gespeichert sind.](./media/state-and-data-in-docker-applications/container-based-application-external-data-sources.png)

**Abbildung 4-5**. Volumes und externe Datenquellen für containerbasierte Anwendungen

Darüber hinaus können Docker-Container möglicherweise zwischen Hosts verschoben werden, wenn sie von einem Orchestrator verwaltet werden. Dies hängt von den vom Cluster durchgeführten Optimierungen ab. Aus diesem Grund wird nicht empfohlen, Datenvolumes für Geschäftsdaten zu verwenden. Dennoch sind sie ein guter Mechanismus zur Bearbeitung von Ablaufverfolgungsdateien, temporären Dateien oder ähnlichem, die keine Auswirkung auf die Konsistenz von Geschäftsdaten haben.

Tools für **Remotedatenquellen und -caches** wie Azure SQL-Datenbank, Azure Cosmos DB oder ein Remotecache wie Redis können in Containeranwendungen auf die gleiche Weise verwendet werden wie bei der Entwicklung ohne Container. Dies ist eine bewährte Möglichkeit zum Speichern von Geschäftsanwendungsdaten.

**Azure Storage.** Geschäftsdaten müssen in der Regel in externen Ressourcen oder Datenbanken wie Azure Storage abgelegt werden. Azure Storage bietet die folgenden Dienste in der Cloud:

- Blob Storage speichert unstrukturierte Objektdaten. Ein Blob kann jeder Text- oder Binärdatentyp sein, z.B. Dokumenten- oder Mediendaten (Bilder, Audio- und Videodateien). Blob Storage wird auch als Object Storage bezeichnet.

- File Storage bietet einen gemeinsam genutzten Speicher für Legacyanwendungen unter Verwendung des standardmäßigen SMB-Protokolls. Azure Virtual Machines und Clouddienste können Dateidaten mithilfe bereitgestellter Freigaben für mehrere Anwendungskomponenten freigeben. Lokale Anwendungen können über die REST-API des Dateidiensts auf Dateidaten in einer Freigabe zugreifen.

- File Storage speichert strukturierte Datasets. File Storage ist ein NoSQL-Schlüsselattributdatenspeicher, der schnelle Entwicklung sowie den schnellen Zugriff auf große Datenmengen ermöglicht.

**Relationale Datenbanken und NoSQL-Datenbanken.** Es gibt verschiedene Auswahlmöglichkeiten für externe Datenbanken, angefangen bei relationalen Datenbanken wie SQL Server, PostgreSQL, Oracle oder NoSQL-Datenbanken wie Azure Cosmos DB, MongoDB usw. Diese Datenbanken werden nicht im Rahmen dieses Leitfadens erklärt, da sie ein völlig anderes Themas darstellen.

>[!div class="step-by-step"]
>[Zurück](monolithic-applications.md)
>[Weiter](soa-applications.md)
