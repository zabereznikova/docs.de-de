---
title: Docker-Terminologie
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Docker-Terminologie"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 885b1fbd3369dec54ebde21a5378630c764f852d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="docker-terminology"></a>Docker-Terminologie

In diesem Abschnitt werden die Begriffe und Definitionen, denen Sie mit vertraut sein sollten, bevor die erste tiefer in Docker aufgelistet. Weitere Definitionen finden Sie das umfangreiche [Glossar](https://docs.docker.com/v1.11/engine/reference/glossary/) von Docker bereitgestellt.

**Container-Abbild**: ein Paket mit den Abhängigkeiten und die benötigten Informationen zum Erstellen eines Containers. Ein-Image enthält alle Abhängigkeiten (z. B. Frameworks) sowie die Bereitstellung und Ausführung der Konfiguration durch eine containerlaufzeit verwendet werden. Mehrere zugrundeliegenden Images, die übereinander zum Bilden des Containers Filesystem Ebenen sind in der Regel ein Bild abgeleitet. Ein Image ist unveränderlich, nachdem es erstellt wurde.

**Container**: eine Instanz des Docker-Images. Ein Container stellt die Ausführung einer einzelnen Anwendung, Prozess oder Dienst dar. Er besteht aus den Inhalt des ein Docker Bild, eine ausführungsumgebung und einen standardmäßigen Satz von Anweisungen. Bei einen Dienst zu skalieren, erstellen Sie mehrere Instanzen eines Containers aus dem gleichen Image. Oder Batchauftrag kann mehrere Container aus dem gleichen Bild, das Übergeben von anderen Parametern für jede Instanz erstellen.

**Tag**: eine Markierung oder eine Bezeichnung, die Sie können für Bilder gelten, damit verschiedene Bilder oder Versionen desselben Images (abhängig von der Versionsnummer oder die zielumgebung) identifiziert werden können.

**Dockerfile-Datei**: eine Textdatei, die Anweisungen zum Erstellen eines Images von Docker enthält.

**Erstellen Sie**: die Aktion zum Erstellen eines containerimages auf Grundlage der Informationen und Kontext durch die dockerfile-Datei sowie weitere Dateien in den Ordner, in dem das Image erstellt wird. Sie können Bilder mit dem Befehl "Docker Docker Build" erstellen.

**Repository (Repository)**: eine Auflistung von zugehörigen Docker-Images, mit der Bezeichnung mit dem Tag, der die Version des Bilds angibt. Einige Repositorys enthalten mehrere Varianten für ein bestimmtes Abbild, z. B. ein Image mit SDKs (größere), ein Bild enthält nur Laufzeiten (heller) usw. an. Diese Varianten können mit Tags markiert werden. Einem einzelnen Repository kann Plattform Varianten, z. B. ein Linux-Image und ein Windows-Image enthalten.

**Registrierung**: ein Dienst, den Zugriff auf Repositorys bereitstellt. Die Standard-Registrierung für die meisten öffentliche Images ist [Docker Hub](https://hub.docker.com/) (im Besitz von Docker in einer Organisation enthalten). Eine Registrierung enthält in der Regel über mehrere Teams Repositorys. Unternehmen haben häufig private Registrierungen zum Speichern und Verwalten von Images, die sie erstellt haben. Azure-Container-Registrierung ist ein weiteres Beispiel.

**Docker Hub**: einer öffentlichen Registrierung zum Hochladen von Images und mit ihnen arbeiten. Docker Hub bietet Docker Bild zu hosten, öffentlichen oder privaten Registrierungen Buildtrigger und Web-Hooks und Integration in GitHub und Bitbucket.

**Azure Containerregistrierung**: eine öffentliche Ressource für die Arbeit mit Docker-Images und seiner Komponenten in Azure. Dies bietet eine Registrierung ist in der Nähe Ihrer Bereitstellungen in Azure und die Steuerung zugreifen, wodurch es möglich ist, verwenden Sie die Azure Active Directory-Gruppen und Berechtigungen.

**Docker Trusted Registry (DTR)**: ein Docker Registrierung-Dienst (von Docker), werden kann, installiert lokal, sodass sie innerhalb der Organisation Datencenter und Netzwerk aktiv ist. Es ist praktisch für private Images, die innerhalb des Unternehmens verwaltet werden sollen. Docker Trusted Registry ist Bestandteil des Produkts Docker Datacenter. Weitere Informationen finden Sie unter [Docker Trusted Registry (DTR)](https://docs.docker.com/docker-trusted-registry/overview/).

**Docker-Community Edition (CE)**: Entwicklungstools für Windows und MacOS zum Erstellen, ausführen und Testen von Containern lokal. Docker CE für Windows bietet entwicklungsumgebungen für Linux und Windows-Containern. Die Linux-Docker-Host unter Windows basiert auf einer [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) virtuellen Computer. Der Host für die Windows-Containern basiert direkt unter Windows. Docker CE für Mac basiert auf der Apple-Hypervisor-Framework und die [Xhyve Hypervisor](https://github.com/mist64/xhyve), Docker-Toolbox auf die Oracle stellt auf einer Linux-Docker-Host-VM auf Mac OS x Docker-CE für Windows und für Mac ersetzt VirtualBox.

**Docker Enterprise Edition (EE)**: eine Enterprise-Skalierung-Version des Docker-Tools für Linux und Windows-Entwicklung.

**Verfassen**: ein Befehlszeilentool und YAML Dateiformat mit Metadaten zum Definieren und Ausführen von Anwendungen mit mehreren Container. Sie definieren eine einzelne Anwendung basierend auf mehrere Abbilder mit einer oder mehreren .yml-Dateien, die Werte abhängig von der Umgebung überschreiben können. Nachdem Sie die Definitionen erstellt haben, können Sie die gesamte mit mehreren Steuerelementcontainer-Anwendung mit einem einzigen Befehl bereitstellen (Docker-verfassen oben), der einen Container pro Bild auf dem Docker-Host erstellt.

**Cluster**: eine Auflistung von Docker-Hosts, die verfügbar gemacht, als handele es sich um einen einzelnen virtuellen Docker-Host, sodass die Anwendung werden, um mehrere Instanzen der Dienste skaliert kann auf mehreren Hosts im Cluster verteilt. Docker-Clustern können mit Docker Containerhostclustern, Mesosphere DC/OS, Kubernetes und Azure Service Fabric erstellt werden. (Wenn Sie Docker Containerhostclustern für die Verwaltung von einem Cluster verwenden, in der Regel finden Sie in den Cluster als ein *containerhostclustern* anstelle eines Clusters.)

**Orchestrator**: ein Tool, das vereinfacht die Verwaltung von Clustern und Docker-Hosts. Orchestrators ermöglichen es Ihnen, ihre Bilder, die Container und die Hosts über eine Befehlszeilenschnittstelle (CLI) zu verwalten oder eine grafische Benutzeroberfläche. Sie können containernetzwerk-Funktionen, Konfigurationen, Lastenausgleich, Dienstermittlung, hohe Verfügbarkeit, Konfiguration des Docker-Hosts und mehr verwalten. Ein Orchestrator ist verantwortlich für ausgeführt sowie die Verteilung, Skalierung und Reparatur Arbeitslasten über eine Auflistung von Knoten. Orchestrator-Produkte werden in der Regel die gleichen Produkte, die Clusterinfrastruktur, z. B. Mesosphere DC/OS, Kubernetes Docker Containerhostclustern und Azure Service Fabric bereitstellen.


>[!div class="step-by-step"]
[Vorherigen] (Docker-defined.md) [weiter] (Docker-Container-Images-registries.md)
