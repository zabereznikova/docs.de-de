---
title: Docker-Terminologie
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a622b2949c1d2277bb3e82617a5bc2d8cb432263
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="docker-terminology"></a>Docker-Terminologie

Dieser Abschnitt listet Begriffe und Definitionen, die mit dem Sie mit vor befassen tiefer in Docker vertraut sollten (Weitere Definitionen finden Sie das umfangreiche [Glossar](https://docs.docker.com/glossary/) Docker am gebotenen <https:// docs.docker.com/glossary/>:

-   **Container-Abbild** ein Paket mit der alle Abhängigkeiten und Informationen erforderlich, um einen Container zu erstellen. Ein-Image enthält alle Abhängigkeiten (z. B. Frameworks) plus Bereitstellung und Konfiguration von einem containerlaufzeit verwendet werden. Ein Bild abgeleitet in der Regel mehrere Basisimages, dass Ebenen über die zweite für das Dateisystem des Containers bilden gestapelt werden. Ein Image ist unveränderlich, nachdem es erstellt wurde.

-   **Container** eine Instanz des Docker-Images. Ein Container stellt eine Laufzeit für eine einzelne Anwendung, Prozess oder Dienst dar. Er besteht aus den Inhalt des ein Docker Bild, eine Laufzeitumgebung und einen standardmäßigen Satz von Anweisungen. Bei einen Dienst zu skalieren, erstellen Sie mehrere Instanzen eines Containers aus dem gleichen Image. Alternativ können Batchauftrag kann mehrere Container aus dem gleichen Bild, das Übergeben von anderen Parametern für jede Instanz erstellen.

-   **Tag** eine Markierung oder eine Bezeichnung, die auf Bilder angewendet werden kann, damit verschiedene Bilder oder Versionen desselben Images (abhängig von der Versionsnummer oder der zielumgebung) identifiziert werden können.

-   **Dockerfile** eine Textdatei, die Anweisungen zum Erstellen eines Images von Docker enthält.

-   **Erstellen Sie** die Aktion zum Erstellen eines containerimages auf Grundlage der Informationen und Kontext durch die dockerfile-Datei sowie weitere Dateien in den Ordner, in dem das Image erstellt wird. Sie können Images erstellen, mit dem Befehl "Docker Docker Build".

-   **Repository (auch bekannt als Repository)** eine Auflistung von zugehörigen Docker-Images, die mit der Bezeichnung mit dem Tag, der die Version des Bilds angibt. Einige Repositorys enthalten mehrere Varianten für ein bestimmtes Abbild, z. B. ein Bild mit SDKs (größere), ein Bild enthält nur die Laufzeiten (heller), und so weiter. Diese Varianten können mit Tags markiert werden. Ein einzelnes Repository kann Plattform Varianten, z. B. ein Linux-Image und ein Windows-Image enthalten.

-   **Registrierung** ein Dienst, den Zugriff auf Repositorys bereitstellt. Die Standard-Registrierung für die meisten öffentliche Images ist [Docker Hub](https://hub.docker.com/) (im Besitz von Docker in einer Organisation enthalten). Eine Registrierung enthält in der Regel über mehrere Teams Repositorys. Unternehmen haben häufig private Registrierungen zum Speichern und Verwalten von Images, die sie erstellt haben. *Azure Containerregistrierung* ist ein weiteres Beispiel.

-   **Docker Hub** einer öffentlichen Registrierung zum Hochladen von Images und mit ihnen arbeiten. Docker Hub bietet Docker Bild zu hosten, öffentlichen oder privaten Registrierungen Buildtrigger und Web-Hooks und Integration in GitHub und Bitbucket.

-   **Azure Containerregistrierung** eine öffentliche Ressource für die Arbeit mit Docker-Images und seiner Komponenten in Azure. Dies bietet eine Registrierung ist in der Nähe Ihrer Bereitstellungen in Azure und die Steuerung zugreifen, wodurch es möglich ist, verwenden Sie die Azure Active Directory-Gruppen und Berechtigungen.

-   **Docker Trusted Registry (DTR)** ein Docker-Registrierung (von Docker), die Sie installieren können lokale so, dass er im Datencenter und das Netzwerk der Organisation gespeichert. Es ist praktisch für private Images, die innerhalb des Unternehmens verwaltet werden sollen. Docker Trusted Registry ist Bestandteil des Produkts Docker Datacenter. Weitere Informationen finden Sie unter [https://docs.docker.com/docker-trusted-registry/overview/](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker-Community Edition (CE)** Entwicklungstools für Windows und MacOS zum Erstellen, ausführen und Testen von Containern lokal. Docker CE für Windows bietet entwicklungsumgebungen für Linux und Windows-Containern. Die Linux-Docker-Host unter Windows basiert auf einem [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) VM. Der Host für die Windows-Containern basiert direkt unter Windows. Docker CE für Mac basiert auf der Apple-Hypervisor-Framework und die [Xhyve Hypervisor](https://github.com/mist64/xhyve), Docker-Toolbox auf die Oracle-VirtualBox stellt auf einen Linux-Docker-Host-VM auf Mac OS x Docker-CE für Windows und für Mac ersetzt.

-   **Docker Enterprise Edition (EE)** eine Enterprise-Skalierung-Version des Docker-Tools für Linux und Windows-Entwicklung.

-   **Verfassen** ein Befehlszeilentool und YAML Dateiformat mit Metadaten zum Definieren und Ausführen von multicontainer Anwendungen. Sie definieren eine einzelne Anwendung basierend auf mehrere Abbilder mit einer oder mehreren .yml-Dateien, die Werte abhängig von der Umgebung überschreiben können. Nachdem Sie die Definitionen erstellt haben, können Sie die gesamte multicontainer Anwendung bereitstellen, mit einem einzigen Befehl (Docker-verfassen oben), der einen Container pro Bild auf dem Docker-Host erstellt.

-   **Cluster** eine Auflistung von Docker-Hosts, die verfügbar gemacht, als wären sie einen einzelnen virtuellen Docker-Host, damit die Anwendung skaliert werden kann, um mehrere Instanzen der Dienste auf mehreren Hosts im Cluster verteilt. Sie können die Docker-Cluster erstellen, mit Docker Containerhostclustern, Mesosphere DC/OS, Kubernetes und Azure Service Fabric. (Wenn Sie Docker Containerhostclustern für die Verwaltung von einem Cluster verwenden, in der Regel finden Sie in den Cluster als ein *containerhostclustern* anstelle eines Clusters.)

-   **Orchestrator** ein Tool, das vereinfacht die Verwaltung von Clustern und Docker-Hosts. Orchestrators können Sie ihre Bilder, die Container und die Hosts über eine CLI oder eine grafische Benutzeroberfläche verwalten. Sie können containernetzwerk-Funktionen, Konfigurationen, Lastenausgleich, Dienstermittlung, hohe Verfügbarkeit, Konfiguration des Docker-Hosts und mehr verwalten. Ein Orchestrator ist verantwortlich für ausgeführt sowie die Verteilung, Skalierung und Reparatur Arbeitslasten über eine Auflistung von Knoten. Orchestrator-Produkte werden in der Regel die gleichen Produkte, die Clusterinfrastruktur, z. B. Mesosphere DC/OS, Kubernetes Docker Containerhostclustern und Azure Service Fabric bereitstellen.


>[!div class="step-by-step"]
[Vorherigen] (Was-ist-docker.md) [weiter] (Docker-Container-Images-und-registries.md)
