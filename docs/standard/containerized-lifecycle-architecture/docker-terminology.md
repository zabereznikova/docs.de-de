---
title: Docker-Terminologie
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 7a8ec2233b7927c1e3f85f5a3536a889a6a55e22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574029"
---
# <a name="docker-terminology"></a>Docker-Terminologie

Dieser Abschnitt listet Begriffe und Definitionen, die mit dem Sie mit vor befassen tiefer in Docker vertraut sollten (Weitere Definitionen finden Sie das umfangreiche [Glossar](https://docs.docker.com/glossary/) Docker am gebotenen <https://docs.docker.com/glossary/>:

-   **Container-Abbild** ein Paket mit der alle Abhängigkeiten und Informationen erforderlich, um einen Container zu erstellen. Ein-Image enthält alle Abhängigkeiten (z. B. Frameworks) plus Bereitstellung und Konfiguration von einem containerlaufzeit verwendet werden. Ein Bild abgeleitet in der Regel mehrere Basisimages, dass Ebenen über die zweite für das Dateisystem des Containers bilden gestapelt werden. Ein Image ist unveränderlich, nachdem es erstellt wurde.

-   **Container** eine Instanz des Docker-Images. Ein Container stellt eine Laufzeit für eine einzelne Anwendung, Prozess oder Dienst dar. Er besteht aus den Inhalt des ein Docker Bild, eine Laufzeitumgebung und einen standardmäßigen Satz von Anweisungen. Beim Skalieren eines Diensts erstellen Sie mehrere Instanzen eines Containers aus dem gleichen Image. Alternativ können Batchauftrag kann mehrere Container aus dem gleichen Bild, das Übergeben von anderen Parametern für jede Instanz erstellen.

-   **Tag** eine Markierung oder eine Bezeichnung, die auf Bilder angewendet werden kann, damit verschiedene Bilder oder Versionen desselben Images (abhängig von der Versionsnummer oder der zielumgebung) identifiziert werden können.

-   **Dockerfile** eine Textdatei, die Anweisungen zum Erstellen eines Images von Docker enthält.

-   **Erstellen Sie** die Aktion zum Erstellen eines containerimages auf Grundlage der Informationen und Kontext durch die dockerfile-Datei sowie weitere Dateien in den Ordner, in dem das Image erstellt wird. Sie können Images erstellen, mit dem Befehl "Docker Docker Build".

-   **Repository (auch bekannt als Repository)** eine Auflistung von zugehörigen Docker-Images, die mit der Bezeichnung mit dem Tag, der die Version des Bilds angibt. Einige Repositorys enthalten mehrere Varianten für ein bestimmtes Abbild, z. B. ein Bild mit SDKs (größere), ein Bild enthält nur die Laufzeiten (heller), und so weiter. Diese Varianten können mit Tags markiert werden. Ein einzelnes Repository kann Plattform Varianten, z. B. ein Linux-Image und ein Windows-Image enthalten.

-   **Registrierung** ein Dienst, den Zugriff auf Repositorys bereitstellt. Die Standardregistrierung für die meisten öffentlichen Images ist der [Docker-Hub](https://hub.docker.com/) (im Besitz des Docker-Unternehmens). Eine Registrierung enthält in der Regel Repositorys mehrerer Teams. Unternehmen haben häufig private Registrierungen zum Speichern und Verwalten von Images, die sie erstellt haben. *Azure Containerregistrierung* ist ein weiteres Beispiel.

-   **Docker Hub** einer öffentlichen Registrierung zum Hochladen von Images und mit ihnen arbeiten. Docker-Hub bietet Docker-Imagehosts, öffentliche oder private Registrierungen, Buildtrigger, Web-Hooks und Integration mit GitHub und Bitbucket.

-   **Azure Containerregistrierung** eine öffentliche Ressource für die Arbeit mit Docker-Images und seiner Komponenten in Azure. Dies stellt eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure zur Verfügung. Sie erhalten somit Kontrolle über den Zugriff und können Ihre Azure Active Directory-Gruppen und -Berechtigungen verwenden.

-   **Docker Trusted Registry (DTR)** ein Docker-Registrierung (von Docker), die Sie installieren können lokale so, dass er im Datencenter und das Netzwerk der Organisation gespeichert. Er ist praktisch für private Images, die innerhalb des Unternehmens verwaltet werden sollen. Docker Trusted Registry ist als Bestandteil im Produkt Docker Datacenter enthalten. Weitere Informationen finden Sie unter [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker-Community Edition (CE)** Entwicklungstools für Windows und MacOS zum Erstellen, ausführen und Testen von Containern lokal. Docker CE für Windows bietet Entwicklungsumgebungen für Linux- und Windows-Container. Die Linux-Docker-Host unter Windows basiert auf einem [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) VM. Der Host für die Windows-Container basiert direkt auf Windows. Docker CE für Mac basiert auf der Apple-Hypervisor-Framework und die [Xhyve Hypervisor](https://github.com/mist64/xhyve), Docker-Toolbox auf die Oracle-VirtualBox stellt auf einen Linux-Docker-Host-VM auf Mac OS x Docker-CE für Windows und für Mac ersetzt.

-   **Docker Enterprise Edition (EE)** eine Enterprise-Skalierung-Version des Docker-Tools für Linux und Windows-Entwicklung.

-   **Verfassen** ein Befehlszeilentool und YAML Dateiformat mit Metadaten zum Definieren und Ausführen von multicontainer Anwendungen. Sie definieren eine einzelne Anwendung basierend auf mehreren Images mit einer oder mehreren .yml-Dateien, die Werte abhängig von der Umgebung überschreiben können. Nachdem Sie die Definitionen erstellt haben, können Sie die gesamte multicontainer Anwendung bereitstellen, mit einem einzigen Befehl (Docker-verfassen oben), der einen Container pro Bild auf dem Docker-Host erstellt.

-   **Cluster** eine Auflistung von Docker-Hosts, die verfügbar gemacht, als wären sie einen einzelnen virtuellen Docker-Host, damit die Anwendung skaliert werden kann, um mehrere Instanzen der Dienste auf mehreren Hosts im Cluster verteilt. Sie können die Docker-Cluster erstellen, mit Docker Containerhostclustern, Mesosphere DC/OS, Kubernetes und Azure Service Fabric. (Wenn Sie Docker Swarm zur Verwaltung eines Clusters verwenden, verweisen Sie in der Regel auf das Cluster als *Schwarm* anstelle eines Clusters.)

-   **Orchestrator** ein Tool, das vereinfacht die Verwaltung von Clustern und Docker-Hosts. Orchestrators können Sie ihre Bilder, die Container und die Hosts über eine CLI oder eine grafische Benutzeroberfläche verwalten. Sie können u.a. Containernetzwerke, Konfigurationen, den Lastenausgleich, die Dienstermittlung, die Hochverfügbarkeit und die Konfiguration des Docker-Hosts verwalten. Ein Orchestrator ist verantwortlich für die Ausführung, Verteilung, Skalierung und Reparatur von Workloads in einer Knotensammlung. Orchestratorprodukte sind in der Regel die gleichen Produkte, die Clusterinfrastruktur wie Mesosphere DC/OS, Kubernetes, Docker Swarm und Azure Service Fabric bereitstellen.


>[!div class="step-by-step"]
[Vorherigen] (Was-ist-docker.md) [weiter] (Docker-Container-Images-und-registries.md)
