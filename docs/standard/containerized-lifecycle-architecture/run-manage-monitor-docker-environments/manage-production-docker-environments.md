---
title: Verwalten Sie Docker produktionsumgebungen
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 5686dcb0932d4a8580fd5ad3daf9e3f5cf52fff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="manage-production-docker-environments"></a>Verwalten Sie Docker produktionsumgebungen

Die Clusterverwaltungs- und Orchestrierung versteht man eine Gruppe von Hosts zu steuern. Dies kann umfassen, hinzufügen und Entfernen von Hosts in einem Cluster, Abrufen von Informationen zu den aktuellen Status des Hosts und -Container starten und Beenden von Prozessen. Clusterverwaltung und Orchestrierung sind eng mit der Planung, da das Zeitplanungsmodul Zugriff auf jedem Host im Cluster benötigen, um Dienste zu planen. Aus diesem Grund wird häufig die gleichen Konfigurationstool für beide Zwecke verwendet.

## <a name="container-service-and-management-tools"></a>Container-Dienst und Verwaltungstools

Containerdienst bietet eine schnelle Bereitstellung von Lösungen für beliebte Open Source-Container clustering und Orchestrierung. Docker-Images verwendet, um sicherzustellen, dass die Anwendungscontainer vollständig portabel sind. Mit Containerdienst, können Sie DC/OS (mit Unterstützung von Mesosphere und Apache Mesos) bereitstellen und Docker Containerhostclustern-Clustern mit Vorlagen für Azure-Ressourcen-Manager oder Azure-Portal um sicherzustellen, dass diese Anwendungen auf Tausende skaliert werden können – sogar Tausenden von – von Container.

Sie diesen Clustern mithilfe von Azure VM-Skalierungsgruppen bereitstellen und die Cluster Nutzen der Azure-Netzwerk und Speicher-Angebote. Für den Zugriff auf die Container-Dienst benötigen Sie ein Azure-Abonnement. Mit Containerdienst können Sie der Unternehmensklasse Funktionen von Azure nutzen und gleichzeitig die Anwendungsportabilität, einschließlich der auf die Orchestrierung Ebenen.

Tabelle 6 – 1 listet allgemeiner Verwaltungstools, die im Zusammenhang mit ihren Orchestrators, Planern und clustering-Plattform.

Tabelle 6 – 1: Docker-Verwaltungstools


| Verwaltungstools      | Beschreibung           | Verwandte orchestrators |
|-----------------------|-----------------------|-----------------------|
| Containerdienst\(UI-Verwaltung in Azure-Portal) | [Containerdienst](https://azure.microsoft.com/en-us/services/container-service/) bietet eine lassen sich leichter ermitteln können gestartet [ein Container-Clusters in Azure bereitstellen](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) basierend auf beliebte Orchestrators wie Mesosphere DC/OS, Kubernetes und Docker Containerhostclustern. <br /><br /> Containerdienst wird die Konfiguration von diesen Plattformen optimiert. Sie müssen nur auswählen, die Größe, die Anzahl der Hosts und die Auswahl der Orchestrator-Tools, und Containerdienst behandelt alles andere. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Punktschwarms |
| Universelle Steuerungsebene Docker\(einer lokalen oder Cloud) | [Universelle Steuerungsebene Docker](https://docs.docker.com/v1.11/ucp/overview/) der Unternehmensklasse Cluster Management-Lösung von Docker ist. Sie hilft bei der gesamte Cluster aus einer einzelnen Stelle zu verwalten. <br /><br /> Universelle Steuerungsebene Docker ist Bestandteil des kommerziellen Produkts, die mit dem Namen Docker Rechenzentrum ein, der Docker Containerhostclustern, universelle Steuerungsebene Docker und Docker Trusted Registry bereitstellt. <br /><br /> Docker Datacenter installierten lokalen sein oder von einer öffentlichen Cloud wie Azure bereitgestellt. | Docker Containerhostclustern\(von Containerdienst unterstützt) |
| Docker Cloud\(auch bekannt als Tutum, Cloud SaaS) | [Docker Cloud](https://docs.docker.com/docker-cloud/) ist ein gehosteter Verwaltungsdienst (SaaS), die Funktionen der Orchestrierung und einen Docker-Registrierung mit Builds und Tests Einrichtungen für Dockerized Anwendungsbilder, Tools helfen Ihnen beim Einrichten und Verwalten der Hostinfrastruktur des bereitstellt und Bereitstellungsfeatures zum Automatisieren der Bilder für Ihre konkrete Infrastruktur bereitstellen. Sie können Ihr Konto SaaS Docker Cloud für Ihre Infrastruktur in Container-Dienst mit einem Docker Containerhostclustern Cluster verbinden. | Docker Containerhostclustern\(von Containerdienst unterstützt) |
| Mesosphere Marathon\(einer lokalen oder Cloud) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) ist eine Plattform für das Container Produktions-Grade der Orchestrierung und der Planer für Mesosphere des DC/OS und Apache Mesos. <br /><br /> Generische Vergleich funktioniert mit Mesos (DC/OS basiert auf Apache Mesos) steuern lang ausgeführte Dienste und stellt eine [Weboberfläche für die Verwaltung von Prozess- und Container](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Es bietet ein Web-UI-Verwaltungstool | Mesosphere DC/OS\(basierend auf Apache Mesos; vom Containerdienst unterstützt) |
| Google-Kubernetes | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access) orchestriert, plant und -Cluster-Infrastruktur umfasst. Es ist eine Open-Source-Plattform für die Automatisierung der Bereitstellung, Skalierung und Vorgänge des Anwendungscontainer über Clustern der Hosts, Container-orientierte Infrastruktur bereitgestellt. | Google Kubernetes\(von Containerdienst unterstützt) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Eine andere Auswahl für die Cluster-Bereitstellung und Verwaltung wird Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/en-us/services/service-fabric/) ist eine Microsoft-Microservices-Plattform, die Container-Orchestrierung als auch für Entwickler enthält-Programmiermodelle, hochgradig skalierbare Microservices Anwendungen zu erstellen. Service Fabric unterstützt Docker in aktuellen Versionen von Linux-Vorschau an, wie in der [Service Fabric-Vorschau unter Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere), und für Windows-Container [in der nächsten Version](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric-Verwaltungstools für folgen:

-   [Azure-Portal für Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) clusterbezogene Vorgänge (erstellen/aktualisieren/löschen) einen Cluster oder Konfigurieren der Infrastruktur (VMs, Lastenausgleich, Netzwerke usw.).

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) ist eine spezielle Web-UI-Tool, die Einblicke und bestimmte Vorgänge in der Service Fabric-Cluster aus Sicht der Knoten-VMs und aus der Sicht Anwendung und Dienste bereitstellt.


>[!div class="step-by-step"]
[Vorherigen] (Run-microservices-based-applications-in-production.md) [weiter] (Monitor-Containern-Anwendung-services.md)
