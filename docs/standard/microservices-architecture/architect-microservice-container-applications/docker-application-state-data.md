---
title: Status und die Daten in Docker-Anwendungen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Status und die Daten in Docker-Anwendungen"
keywords: Docker, Microservices "," ASP.NET "," Container "," SQL "," CosmosDB "," Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 36d0fb9f27ef56b36c380e2fc972c79cff77003e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="state-and-data-in-docker-applications"></a>Status und die Daten in Docker-Anwendungen

In den meisten Fällen können Sie einen Container als eine Instanz eines Prozesses vorstellen. Ein Prozess behält nicht persistenten Status bei. Während ein Containers in den lokalen Speicher schreiben kann, wäre vorausgesetzt, dass eine Instanz auf unbestimmte Zeit kann z. B. vorausgesetzt, dass eine einzelne Position im Arbeitsspeicher dauerhaft ist. Containerimages, z. B. Prozesse, sollte als gegeben angenommen, mehrere Instanzen oder, die sie werden schließlich abgebrochen; Wenn sie mit einem Container Orchestrator verwaltet werden, sollte davon ausgegangen, dass sie von einem Knoten oder virtuellen Computer in eine andere verschoben werden können.

Docker bietet eine Funktion mit dem Namen der *overlay Dateisystem*. Dadurch wird eine Kopie-bei-Schreibvorgang-Aufgabe, die speichert Informationen in das Stammverzeichnis Dateisystem des Containers aktualisiert implementiert. Diese Informationen werden darüber hinaus das ursprüngliche Bild auf dem der Container basiert. Wenn der Container aus dem System gelöscht wird, werden diese Änderungen verloren. Aus diesem Grund es zwar möglich, den Status eines Containers in den lokalen Speicher zu speichern, würde Entwerfen eines Systems umgehen dieses die Prämisse eines Container-Entwurf Konflikt mit dem standardmäßigen zustandslos ist.

Die folgenden Lösungen werden verwendet, um persistenter Daten in Docker-Anwendungen zu verwalten:

-   [Datenvolumes](https://docs.docker.com/engine/tutorials/dockervolumes/) , die an den Host bereitstellen.

-   [Datenvolumecontainer](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container) , freigegebenen Speicher in Containern, die mit einer externen Container bereitstellen.

-   [Volume-Plug-Ins](https://docs.docker.com/engine/tutorials/dockervolumes/) , die Volumes auf remote-Dienste bereitstellen langfristige Dauerhaftigkeit bereitstellen.

-   [Azure-Speicher](https://docs.microsoft.com/azure/storage/), stellt geografische verteilbarer Speicher, eine geeignete Lösung für langfristige Dauerhaftigkeit für Container bereitstellen.

-   Relationale Remotedatenbanken wie [Azure SQL-Datenbank](https://azure.microsoft.com/services/sql-database/) oder NoSQL-Datenbanken wie [Azure Cosmos-DB](https://docs.microsoft.com/azure/cosmos-db/introduction), oder -Dienste wie zwischenspeichern [Redis](https://redis.io/).

Nachfolgend erhalten Sie weitere Details zu diesen Optionen.

**Datenvolumes** Verzeichnisse aus dem Hostbetriebssystem Verzeichnisse in Containern zugeordnet sind. Wenn Code im Container Zugriff auf das Verzeichnis hat, Zugriff tatsächlich ein Verzeichnis auf dem Host-Betriebssystem ist. Dieses Verzeichnis ist nicht an die Lebensdauer des Containers selbst gebunden, oder und das Verzeichnis zugegriffen werden kann, aus Code direkt auf das Hostbetriebssystem ausgeführt wird, um durch einen anderen Container zugeordnet, die den gleichen Hostverzeichnis auf sich selbst. Deshalb dienen Datenvolumes Daten unabhängig von der Lebensdauer des Containers beibehalten. Wenn Sie einen Container löschen oder ein Bild aus dem Docker-Host, die Daten in persistent wird die Datenmenge nicht gelöscht werden. Die Daten in ein Volume können vom Hostbetriebssystem sowie zugegriffen werden.

**Datenvolumecontainer** eine Weiterentwicklung der regulären Datenvolumes sind. Ein Daten-Volume-Container ist eine einfache Container, der eine oder mehrere Datenvolumes darin enthalten ist. Die Data-Volume-Container bietet Zugriff auf Container, von einem zentralen Bereitstellungspunkt. Diese Methode des Datenzugriffs liegt daran, dass es sich um den Speicherort der ursprünglichen Daten abstrahiert. Als dem ist das Verhalten ähnlich dem von einem regulären Datenvolume, damit Daten in diesem dedizierten Container unabhängig von den Lebenszyklus von Containern der Anwendung beibehalten werden.

Wie in Abbildung 4-5 gezeigt, können reguläre Docker Volumes außerhalb der Container selbst aber innerhalb der physischen Grenzen des dem Hostserver oder einen virtuellen Computer gespeichert werden. Jedoch zugreifen nicht Docker-Containern zu einem anderen ein Volume aus einem Host-Server oder virtuellen Computer. Das heißt, ist mit diesen Volumes es nicht möglich zum Verwalten von Daten, die gemeinsam von Containern, die auf verschiedenen Docker-Hosts ausgeführt werden soll.

![](./media/image5.png)

**Abbildung 4-5**. Datenvolumes und externe Datenquellen für Container-basierte Anwendungen

Darüber hinaus, wenn Docker-Containern durch ein Orchestrator verwaltet werden, möglicherweise Container "zwischen Hosts, je nach den vom Cluster durchgeführten Optimierungen, verschieben". Aus diesem Grund wird nicht empfohlen, Daten-Volumes für Geschäftsdaten zu verwenden. Aber sie sind ein Mechanismus zur Bearbeitung von Ablaufverfolgungsdateien, die temporären Dateien oder vergleichbar, die hat keine Auswirkung auf Datenkonsistenz Business.

**Volume-Plug-Ins** wie [Flocker](https://clusterhq.com/flocker/) Datenzugriff auf allen Hosts in einem Cluster bereitstellen. Während nicht alle Volume-Plug-Ins gleichermaßen erstellt werden, bieten Volume-Plug-Ins in der Regel externalisierte zuverlässige Speicherung von Containern unveränderlich.

**Remotedatenquellen und Cache** Tools wie Azure SQL-Datenbank, Azure-Cosmos-Datenbank oder eine remote-Cache, wie in Redis verwendet werden kann Anwendungen Container verwendet die gleiche Weise, sie werden bei der Entwicklung ohne Container verwendet. Dies ist eine bewährte Möglichkeit zum Speichern von Geschäftsdaten-Anwendung.

**Azure-Speicher.** Geschäftsdaten müssen in der Regel in externe Ressourcen oder Datenbanken, wie Azure-Speicher abgelegt werden soll. Azure-Speicher in konkret, bietet die folgenden Dienste in der Cloud:

-   BLOB-Speicher speichert unstrukturierte Daten. Ein Blob kann jeden Datentyp Text- oder Binärdaten, z. B. Dokument oder ein Medium (Bilder, Audio- und Videofunktionen Format)-Dateien sein. BLOB-Speicher wird auch als Objektspeicher bezeichnet.

-   Speichern von Dateien bietet freigegebenen Speicher für Legacyanwendungen mithilfe von SMB-Standardprotokolls. Azure Virtual Machines und Cloud-Dienste können Dateidaten mithilfe bereitgestellter Freigaben Anwendungskomponenten freigeben. Auf lokale Anwendungen können Dateidaten in einer Freigabe über die Dateidienst-REST-API zugreifen.

-   Tabellenspeicher speichert strukturierte Datasets. Tabellenspeicher ist ein NoSQL-Schlüsselattribut-Datenspeicher, der schnelle Entwicklung sowie den schnellen Zugriff auf große Mengen von Daten ermöglicht.

**Relationale Datenbanken und NoSQL-Datenbanken.** Es gibt verschiedene Auswahlmöglichkeiten für externe Datenbanken, angefangen bei relationalen Datenbanken wie SQL Server, PostgreSQL, Oracle oder NoSQL-Datenbanken wie Azure-Cosmos-DB, MongoDB usw. ein. Diese Datenbanken sind nicht weiter als Teil dieses Handbuch erklärt werden, sie in einen Betreff völlig unterschiedlich sind.


>[!div class="step-by-step"]
[Vorherigen] (containerize-monolithischen-applications.md) [weiter] (Service-oriented-architecture.md)
