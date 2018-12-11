---
title: Docker-Terminologie
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 1efb2fa567bd452f0a0a5ee5afb6f759511e4145
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151308"
---
# <a name="docker-terminology"></a>Docker-Terminologie

Dieser Abschnitt enthält die Begriffe und Definitionen, die mit dem Sie mit Docker systemimplementierung tiefer, bevor vertraut sollte (Weitere Definitionen finden Sie im umfangreichen [Glossar](https://docs.docker.com/glossary/) von Docker unter bereitgestellten <https://docs.docker.com/glossary/>:

-   **Container-Abbild** ein Paket mit allen Abhängigkeiten und Informationen zum Erstellen eines Containers benötigt. Ein Image enthält alle Abhängigkeiten (z.B. Frameworks) sowie Bereitstellung und Konfiguration von einer containerruntime verwendet werden. Wird Sie in der Regel ein Bild aus mehreren zugrundeliegenden Images abgeleitet, dass die Schichten auf die andere zum Dateisystem des Containers bilden gestapelt werden. Ein Image ist unveränderlich, nachdem es erstellt wurde.

-   **Container** eine Instanz eines Docker-Images. Ein Container stellt eine Laufzeit für eine einzelne Anwendung, Prozess oder Dienst dar. Es besteht aus den Inhalt eines Docker-Images, eine Laufzeitumgebung bereitgestellt wird und einen standardmäßigen Satz von Anweisungen. Beim Skalieren eines Diensts erstellen Sie mehrere Instanzen eines Containers aus dem gleichen Image. Oder ein Batch-Auftrag kann mehrere Container aus dem gleichen Image, und übergeben unterschiedliche Parameter für jede Instanz erstellen.

-   **Tag** eine Markierung oder eine Bezeichnung, die Sie auf Images anwenden können, damit verschiedene Images oder Versionen desselben Images (abhängig von der Versionsnummer oder der zielumgebung) identifiziert werden können.

-   **Dockerfile-Datei** eine Textdatei, die Anweisungen zum Erstellen ein Docker-Images enthält.

-   **Erstellen Sie** die Aktion zum Erstellen eines containerimages auf Basis der Informationen und Kontext durch die dockerfile-Datei sowie zusätzliche Dateien im Ordner, in dem das Image erstellt wird. Sie können Images erstellen, mit dem Docker Docker Build-Befehl.

-   **Repository (auch bekannt als Repository)** eine Auflistung von zugehörigen Docker-Images, die mit der Bezeichnung mit einem Tag, der die Version des Images angibt. Einige Repositorys enthalten mehrere Varianten eines bestimmtes Images, z. B. ein Bild mit SDKs (schwerer), ein Bild mit nur Runtimes (leichter), und so weiter. Diese Varianten können mit Tags markiert werden. Ein einziges Repository kann Plattformvarianten, z. B. ein Linux-Image und ein Windows-Image enthalten.

-   **Registrierung** ein Dienst, der Zugriff auf Repositorys bereitstellt. Die Standardregistrierung für die meisten öffentlichen Images ist der [Docker-Hub](https://hub.docker.com/) (im Besitz des Docker-Unternehmens). Eine Registrierung enthält in der Regel Repositorys mehrerer Teams. Unternehmen haben häufig private Registrierungen zum Speichern und Verwalten von Images, die sie erstellt haben. *Azure-Containerregistrierung* ist ein weiteres Beispiel.

-   **Docker-Hub** eine öffentliche Registrierung zum Hochladen von Bildern und mit ihnen arbeiten. Docker-Hub bietet Docker-Imagehosts, öffentliche oder private Registrierungen, Buildtrigger, Web-Hooks und Integration mit GitHub und Bitbucket.

-   **Azure-Containerregistrierung** eine öffentliche Ressource für die Arbeit mit Docker-Images und deren Komponenten in Azure. Dies stellt eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure zur Verfügung. Sie erhalten somit Kontrolle über den Zugriff und können Ihre Azure Active Directory-Gruppen und -Berechtigungen verwenden.

-   **Docker Trusted Registry (DTR)** ein Docker-Registrierungsdienst (von Docker), die Sie installieren können lokal, damit er sich in der Organisation Datencenter und Netzwerk befindet. Er ist praktisch für private Images, die innerhalb des Unternehmens verwaltet werden sollen. Docker Trusted Registry ist als Bestandteil im Produkt Docker Datacenter enthalten. Weitere Informationen finden Sie unter [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker Community Edition (CE)** Entwicklungstools für Windows und MacOS zum Erstellen, ausführen und Testen von Containern lokal. Docker CE für Windows bietet Entwicklungsumgebungen für Linux- und Windows-Container. Der Linux-Docker-Host auf Windows basiert auf einer [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) VM. Der Host für die Windows-Container basiert direkt auf Windows. Docker CE für Mac basiert auf dem Apple Hypervisor-Framework und die [Xhyve-Hypervisor](https://github.com/mist64/xhyve), die eine Linux-Docker-Host-VM auf Mac OS x Docker-CE für Windows und für Mac ersetzt Docker Toolbox, das auf Oracle VirtualBox basiert.

-   **Docker Enterprise Edition (EE)** eine unternehmensweite-Version von Docker-Tools für Linux und Windows-Entwicklung.

-   **Compose** ein Befehlszeilentool und YAML-Dateiformat mit Metadaten zum Definieren und Ausführen von Anwendungen mit mehreren Containern. Sie definieren eine einzelne Anwendung basierend auf mehreren Images mit einer oder mehreren .yml-Dateien, die Werte abhängig von der Umgebung überschreiben können. Nachdem Sie die Definitionen erstellt haben, können Sie die gesamte mit mehreren Containern Anwendung bereitstellen, mit einem einzigen Befehl (Docker-compose einrichten), einen Container pro Image auf Docker-Host erstellt.

-   **Cluster** eine Auflistung von Docker-Hosts, die verfügbar gemacht, als wären sie einen einzelnen virtuellen Docker-Host, damit die Anwendung skaliert werden kann, um mehrere Instanzen der Dienste auf mehreren Hosts im Cluster verteilt. Sie können Docker-Cluster mithilfe von Docker Swarm, Mesosphere DC/OS, Kubernetes und Azure Service Fabric erstellen. (Wenn Sie Docker Swarm zur Verwaltung eines Clusters verwenden, verweisen Sie in der Regel auf das Cluster als *Schwarm* anstelle eines Clusters.)

-   **Orchestrator** ein Tool, das vereinfacht die Verwaltung von Clustern und Docker-Hosts. Orchestratoren können Sie ihre Images, Container und Hosts über eine Befehlszeilenschnittstelle oder über eine grafische Benutzeroberfläche verwalten. Sie können u.a. Containernetzwerke, Konfigurationen, den Lastenausgleich, die Dienstermittlung, die Hochverfügbarkeit und die Konfiguration des Docker-Hosts verwalten. Ein Orchestrator ist verantwortlich für die Ausführung, Verteilung, Skalierung und Reparatur von Workloads in einer Knotensammlung. Orchestratorprodukte sind in der Regel die gleichen Produkte, die Clusterinfrastruktur wie Mesosphere DC/OS, Kubernetes, Docker Swarm und Azure Service Fabric bereitstellen.

>[!div class="step-by-step"]
>[Zurück](what-is-docker.md)
>[Weiter](docker-containers-images-and-registries.md)