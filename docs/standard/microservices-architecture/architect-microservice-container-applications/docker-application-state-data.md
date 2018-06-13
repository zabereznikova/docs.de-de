---
title: Zustand und Daten in Docker-Anwendungen
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Zustand und Daten in Docker-Anwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: c5cfe617335d8150d069149ac87f79206b1b5eca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578654"
---
# <a name="state-and-data-in-docker-applications"></a>Zustand und Daten in Docker-Anwendungen

In den meisten Fällen können Sie sich einen Container als Instanz eines Prozesses vorstellen. Ein Prozess behält keinen persistenten Zustand bei. Während ein Container in den lokalen Speicher schreiben kann, gleicht die Annahme, dass eine Instanz auf unbestimmte Zeit vorhanden ist, der Annahme, dass ein Speicherort im Arbeitsspeicher dauerhaft ist. Für Containerimages, z.B. Prozesse, sollte angenommen werden, dass sie über mehrere Instanzen verfügen oder irgendwann abgebrochen werden. Wenn sie mit einem Containerorchestrator verwaltet werden, kann man davon ausgehen, dass sie von einem Knoten oder VM in einen anderen verschoben werden können.

Docker bietet ein Feature mit dem Namen *Overlay File System* (Dateisystem überlagern). Dadurch wird ein copy-on-write-Task (Bei Schreibvorgang kopieren) implementiert, die aktualisierte Informationen in das Stammdateisystem des Containers speichert. Diese Informationen kommen zum ursprünglichen Image hinzu, auf dem der Container basiert. Wenn der Container aus dem System gelöscht wird, gehen diese Änderungen verloren. Aus diesem Grund ist es zwar möglich, den Zustand eines Containers in seinem lokalen Speicher zu speichern, doch das Entwerfen eines umgehenden Systems würde mit der Prämisse des Containerdesigns kollidieren. Dieses Design ist standardmäßig zustandslos.

Die folgenden Lösungen werden verwendet, um persistente Daten in Docker-Anwendungen zu verwalten:

-   [Datenvolumes](https://docs.docker.com/engine/tutorials/dockervolumes/), die in den Host eingebunden werden.

-   [Datenvolumecontainer](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container), die freigegebenen Speicher in Containern bereitstellen, die einen externen Container verwenden.

-   [Volume-Plug-Ins](https://docs.docker.com/engine/tutorials/dockervolumes/), die Volumes in Remotedienste einbinden und so langfristige Persistenz bereitstellen.

-   [Azure Storage](https://docs.microsoft.com/azure/storage/), das geografisch verteilbaren Speicher und eine geeignete Lösung für langfristige Persistenz für Container bereitstellt.

-   Relationale Remotedatenbanken wie die [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database/) oder NoSQL-Datenbanken wie [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) oder Zwischenspeicherdienste wie [Redis](https://redis.io/).

Nachfolgend erhalten Sie weitere Details zu diesen Optionen.

**Datenvolumes** sind Verzeichnisse, die vom Hostbetriebssystem den Verzeichnissen in Containern zugeordnet werden. Wenn Code im Container Zugriff auf das Verzeichnis hat, ist dies ein Zugriff auf ein Verzeichnis auf dem Hostbetriebssystem. Dieses Verzeichnis ist nicht an die Lebensdauer des Containers selbst gebunden, und der Zugriff auf das Verzeichnis erfolgt durch Code, der direkt auf dem Hostbetriebssystem ausgeführt wird, oder durch einen anderen Container, der sich selbst das gleiche Hostverzeichnis zuordnet. Deshalb sind diese Datenvolumes dazu entworfen, Daten unabhängig von der Lebensdauer des Containers beizubehalten. Wenn Sie einen Container oder ein Image aus dem Docker-Host löschen, werden die persistenten Daten im Datenvolume nicht gelöscht. Es kann auch vom Hostbetriebssystem auf die Daten in einem Volume zugegriffen werden.

**Datenvolumecontainer** sind eine Weiterentwicklung der regulären Datenvolumes. Ein Datenvolumecontainer ist ein einfacher Container, der mindestens ein Datenvolume enthält. Der Datenvolumecontainer bietet Zugriff auf Container von einem zentralen Bereitstellungspunkt aus. Diese Methode des Datenzugriffs ist praktisch, da sie den Speicherort der ursprünglichen Daten abstrahiert. Davon abgesehen ähnelt das Verhalten dem eines regulären Datenvolumes, damit Daten in diesem dedizierten Container unabhängig vom Lebenszyklus von Containern der Anwendung beibehalten werden.

Wie in Abbildung 4-5 gezeigt, können reguläre Docker-Volumes außerhalb der Container selbst aber innerhalb der physischen Grenzen des Hostservers oder der VM gespeichert werden. Docker-Container können jedoch nicht von einem Hostserver oder einer VM auf ein Volume zugreifen. Das heißt, mit diesen Volumes ist es nicht möglich, Daten zu verwalten, die zwischen Containern freigegeben werden, die auf verschiedenen Docker-Hosts ausgeführt werden.

![](./media/image5.png)

**Abbildung 4-5**. Datenvolumes und externe Datenquellen für containerbasierte Anwendungen

Darüber hinaus können Container möglicherweise zwischen Hosts „verschoben“ werden, wenn Docker-Container von einem Orchestrator verwaltet werden, je nach den vom Cluster durchgeführten Optimierungen. Aus diesem Grund wird nicht empfohlen, Datenvolumes für Geschäftsdaten zu verwenden. Dennoch sind sie ein guter Mechanismus zur Bearbeitung von Ablaufverfolgungsdateien, temporären Dateien oder ähnlichem, die keine Auswirkung auf die Konsistenz von Geschäftsdaten haben.

**Volume-Plug-Ins** wie [Flocker](https://clusterhq.com/flocker/) bieten Datenzugriff auf allen Hosts in einem Cluster. Obwohl nicht alle Volume-Plug-Ins gleichermaßen erstellt werden, bieten Volume-Plug-Ins in der Regel ausgelagerte, persistente und zuverlässige Speicherung von unveränderlichen Containern.

Tools für **Remotedatenquellen und -caches** wie Azure SQL-Datenbank, Azure Cosmos DB oder ein Remotecache wie Redis können in Containeranwendungen auf die gleiche Weise verwendet werden wie bei der Entwicklung ohne Container. Dies ist eine bewährte Möglichkeit zum Speichern von Geschäftsanwendungsdaten.

**Azure Storage.** Geschäftsdaten müssen in der Regel in externen Ressourcen oder Datenbanken wie Azure Storage abgelegt werden. Azure Storage bietet konkret die folgenden Dienste in der Cloud:

-   Blob Storage speichert unstrukturierte Objektdaten. Ein Blob kann jeder Text- oder Binärdatentyp sein, z.B. Dokumenten- oder Mediendaten (Bilder, Audio- und Videodateien). Blob Storage wird auch als Object Storage bezeichnet.

-   File Storage bietet freigegebenen Speicher für Legacyanwendungen mithilfe von SMB-Standardprotokollen. Azure Virtual Machines und Clouddienste können Dateidaten mithilfe bereitgestellter Freigaben für mehrere Anwendungskomponenten freigeben. Lokale Anwendungen können über die REST-API des Dateidiensts auf Dateidaten in einer Freigabe zugreifen.

-   File Storage speichert strukturierte Datasets. File Storage ist ein NoSQL-Schlüsselattributdatenspeicher, der schnelle Entwicklung sowie den schnellen Zugriff auf große Datenmengen ermöglicht.

**Relationale Datenbanken und NoSQL-Datenbanken.** Es gibt verschiedene Auswahlmöglichkeiten für externe Datenbanken, angefangen bei relationalen Datenbanken wie SQL Server, PostgreSQL, Oracle oder NoSQL-Datenbanken wie Azure Cosmos DB, MongoDB usw. Diese Datenbanken werden nicht in diesem Leitfaden erklärt, da sie Teil eines völlig anderen Themas sind.


>[!div class="step-by-step"]
[Zurück] (containerize-monolithic-applications.md) [Weiter] (service-oriented-architecture.md)
