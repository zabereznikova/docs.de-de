---
title: Docker-Terminologie
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Docker-Terminologie
ms.date: 01/30/2020
ms.openlocfilehash: 5ffc7e791df8cbc999c6ababf62670bae46e1d5e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502838"
---
# <a name="docker-terminology"></a>Docker-Terminologie

In diesem Abschnitt werden die Begriffe und Definitionen aufgelistet, mit denen Sie vertraut sein sollten, bevor Sie sich ausführlicher mit Docker beschäftigen. Weitere Definitionen finden Sie im umfangreichen, von Docker bereitgestellten [Glossar](https://docs.docker.com/glossary/).

**Containerimage:** Ein Paket mit allen benötigten Abhängigkeiten und Informationen zum Erstellen eines Containers. Ein Image enthält alle Abhängigkeiten (z.B. Frameworks) sowie die Bereitstellung und Ausführung der Konfiguration, die von einer Containerruntime verwendet werden. In der Regel wird ein Image aus mehreren zugrundeliegenden Images abgeleitet, die in Schichten übereinander liegen und das Dateisystem des Containers bilden. Ein Image ist unveränderlich, nachdem es erstellt wurde.

**Docker-Datei:** Eine Textdatei, die Anweisungen zum Erstellen eines Docker-Images enthält. Wie bei einem Stapelverarbeitungsskript gibt die erste Zeile zunächst das Basisimage an, dann folgen die Anweisungen zum Installieren von erforderlichen Programmen, Kopieren von Dateien usw., bis Sie zu der benötigten Arbeitsumgebung gelangen.

**Build:** Die Aktion zum Erstellen eines Containerimages auf der Grundlage der Informationen und des Kontexts der Docker-Datei sowie weiteren Dateien im Ordner, in dem das Image erstellt wird. Sie können Images mit dem Docker-Befehl **docker build** erstellen.

**Container:** Eine Instanz eines Docker-Images. Ein Container stellt die Ausführung einer einzelnen Anwendung, eines Prozesses oder Diensts dar. Er besteht aus den Inhalten eines Docker-Images, einer Ausführungsumgebung und mehreren Standardanweisungen. Beim Skalieren eines Diensts erstellen Sie mehrere Instanzen eines Containers aus dem gleichen Image. Alternativ kann ein Batchauftrag mehrere Container aus dem gleichen Image erstellen und dabei verschiedene Parameter an jede Instanz übergeben.

**Volumes:** Sie bieten ein Dateisystem mit Schreibzugriff, das vom Container verwendet werden kann. Da Images schreibgeschützt sind, die meisten Programme aber in das Dateisystem schreiben müssen, fügen Volumes eine beschreibbare Schicht oberhalb des Containerimages hinzu, so dass die Programme Zugriff auf ein beschreibbares Dateisystem haben. Das Programm hat keine Informationen darüber, dass es auf ein geschichtetes Dateisystem zugreift, es sieht nur das gewohnte Dateisystem. Volumes befinden sich auf dem Hostsystem und werden von Docker verwaltet.

**Tag:** Eine Markierung oder eine Bezeichnung, die Sie auf Images anwenden können, damit verschiedene Images oder Versionen desselben Images (abhängig von der Versionsnummer oder der Zielumgebung) identifiziert werden können.

**Mehrstufige Builds:** Ein Feature seit Docker 17.05 oder höher, das dabei hilft, die Größe der endgültigen Images zu verringern. Kurz gesagt können Sie mit einem mehrstufigen Build beispielsweise ein großes Basisimage verwenden, das das SDK enthält, um die Anwendung zu kompilieren und zu veröffentlichen, und den Veröffentlichungsordner anschließend mit einem kleinen Basisimage verwenden, das nur als Runtime dient, um ein viel kleineres endgültiges Image zu erzeugen.

**Repositoryname (Repo):** Eine Auflistung von zugehörigen Docker-Images mit dem Tag, das die Version des Images angibt. Einige Repositorys enthalten mehrere Varianten eines bestimmtes Images, z.B. ein Image mit SDKs (schwerer), ein Image nur mit Runtimes (leichter), usw. Diese Varianten können mit Tags markiert werden. Ein Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image.

**Registrierung:** Ein Dienst, der Zugriff auf Repositorys bereitstellt. Die Standardregistrierung für die meisten öffentlichen Images ist der [Docker-Hub](https://hub.docker.com/) (im Besitz des Docker-Unternehmens). Eine Registrierung enthält in der Regel Repositorys mehrerer Teams. Unternehmen haben häufig private Registrierungen zum Speichern und Verwalten von Images, die sie erstellt haben. Azure Container Registry ist ein weiteres Beispiel.

**Images für mehrere Architekturen:** Die Eignung für mehrere Architekturen ist ein Feature, das die Auswahl des passenden Images je nach Plattform erleichtert, auf der Docker ausgeführt wird. Wenn ein Dockerfile beispielsweise ein Basisimage **FROM mcr.microsoft.com/dotnet/core/sdk:3.1** aus der Registrierung anfordert, erhält es tatsächlich **3.1-sdk-nanoserver-1909**, **3.1-sdk-nanoserver-1809** oder **3.1-sdk-buster-slim**, je nach Betriebssystem und Version, mit dem bzw. der Docker ausgeführt wird.

**Docker-Hub:** Eine öffentliche Registrierung zum Hochladen von und Arbeiten mit Images. Docker-Hub bietet Docker-Imagehosts, öffentliche oder private Registrierungen, Buildtrigger, Web-Hooks und Integration mit GitHub und Bitbucket.

**Azure Container Registry:** Eine öffentliche Ressource zur Arbeit mit Docker-Images und deren Komponenten in Azure. Dies stellt eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure zur Verfügung. Sie erhalten somit Kontrolle über den Zugriff und können Ihre Azure Active Directory-Gruppen und -Berechtigungen verwenden.

**Docker Trusted Registry (DTR):** Ein Docker-Registrierungsdienst (von Docker), der lokal installiert werden kann, sodass er innerhalb des Datencenters und Netzwerks des Unternehmens aktiv ist. Er ist praktisch für private Images, die innerhalb des Unternehmens verwaltet werden sollen. Docker Trusted Registry ist als Bestandteil im Produkt Docker Datacenter enthalten. Weitere Informationen finden Sie unter [Docker Trusted Registry (DTR)](https://docs.docker.com/docker-trusted-registry/overview/).

**Docker Community Edition (CE):** Entwicklungstools für Windows und macOS zum lokalen Erstellen, Ausführen und Testen von Containern. Docker CE für Windows bietet Entwicklungsumgebungen für Linux- und Windows-Container. Der Linux-Docker-Host auf Windows basiert auf einer [Hyper-V](https://www.microsoft.com/cloud-platform/server-virtualization)-VM. Der Host für die Windows-Container basiert direkt auf Windows. Docker CE für Mac basiert auf dem Apple Hypervisor-Framework und dem [Xhyve-Hypervisor](https://github.com/mist64/xhyve), der eine Linux-Docker-Host-VM auf Mac OS X bereitstellt. Docker CE für Windows und für Mac ersetzt Docker Toolbox, das auf Oracle VirtualBox basiert.

**Docker Enterprise Edition (EE):** Eine Version der Docker-Tools für Unternehmen für die Linux- und Windows-Entwicklung.

**Compose:** Ein Befehlszeilentool und YAML-Dateiformat mit Metadaten zum Definieren und Ausführen von Anwendungen mit mehreren Container. Sie definieren eine einzelne Anwendung basierend auf mehreren Images mit einer oder mehreren .yml-Dateien, die Werte abhängig von der Umgebung überschreiben können. Nachdem Sie die Definitionen erstellt haben, können Sie die gesamte Anwendung mit mehreren Containern mit einem einzigen Befehl (docker-compose up) bereitstellen, der einen Container pro Image auf dem Docker-Host erstellt.

**Cluster:** Eine Sammlung von zur Verfügung gestellten Docker-Hosts, als handele es sich um einen einzelnen, virtuellen Docker-Host, sodass die Anwendung mehrere Instanzen der Dienste skalieren kann, die auf mehrere Hosts im Cluster verteilt sind. Docker-Cluster können mit Kubernetes, Azure Service Fabric, Docker Swarm und Mesosphere DC/OS erstellt werden.

**Orchestrator:** Ein Tool, das die Verwaltung von Clustern und Docker-Hosts vereinfacht. Orchestratoren ermöglichen es Ihnen, Ihre Images, Container und Hosts über eine CLI oder eine grafische Benutzeroberfläche zu verwalten. Sie können u.a. Containernetzwerke, Konfigurationen, den Lastenausgleich, die Dienstermittlung, die Hochverfügbarkeit und die Konfiguration des Docker-Hosts verwalten. Ein Orchestrator ist verantwortlich für die Ausführung, Verteilung, Skalierung und Reparatur von Workloads in einer Knotensammlung. Orchestratorprodukte sind in der Regel die gleichen Produkte, die Clusterinfrastruktur bereitstellen, wie Kubernetes und Azure Service Fabric, nebst anderen Angeboten am Markt.

>[!div class="step-by-step"]
>[Zurück](docker-defined.md)
>[Weiter](docker-containers-images-registries.md)
