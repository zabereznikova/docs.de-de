---
title: Verwalten von Docker-produktionsumgebungen
description: Lernen Sie wichtige Punkte für die Verwaltung einer produktionsumgebung containerbasierte kennen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 54e2b999f744600d3b6853442bb9ccca004f4e76
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219489"
---
# <a name="manage-production-docker-environments"></a>Verwalten von Docker-produktionsumgebungen

Clusterverwaltung und Orchestrierung ist der Prozess, eine Gruppe von Hosts zu steuern. Dies kann beinhalten, hinzufügen und Entfernen von Hosts in einem Cluster, das Abrufen von Informationen zu den aktuellen Zustand des Hosts und Containern, und starten und Beenden von Prozessen. Clusterverwaltung und Orchestrierung sind eng mit planen, da der Scheduler den Zugriff auf jedem Host im Cluster benötigen, um Dienste zu planen. Aus diesem Grund wird das gleiche Tool häufig für beide Zwecke verwendet.

## <a name="container-service-and-management-tools"></a>Container Service und Verwaltungstools

Container Service bietet eine schnelle Bereitstellung von Lösungen für beliebte Open-Source-Container clustering und die Orchestrierung. Docker-Images verwendet, um sicherzustellen, dass Ihre Anwendungscontainer vollständig portierbar sind. Mithilfe von Container Service können Sie DC/OS (unterstützt von Mesosphere und Apache Mesos) bereitstellen und Docker Swarm-Clustern mit Azure Resource Manager-Vorlagen oder im Azure-Portal um sicherzustellen, dass Sie diese Anwendungen auf Tausende skalieren können – sogar Tausende – von Container.

Sie diesen Clustern mit Azure Virtual Machine Scale Sets bereitstellen, und die Cluster profitieren Sie von Azure-Netzwerk und Speicher-Angebote. Für den Zugriff auf Container Service benötigen Sie ein Azure-Abonnement. Mit Container Service können Sie professionelle Funktionen von Azure nutzen und gleichzeitig die Anwendungsportabilität, einschließlich der auf den orchestrierungsebenen.

Tabelle 6 – 1 listet allgemeiner Verwaltungstools, die im Zusammenhang mit ihrer orchestratoren, Planer und clustering-Plattform.

Tabelle 6 – 1: Docker-Verwaltungstools


| Verwaltungstools      | Beschreibung           | Verwandte orchestratoren |
|-----------------------|-----------------------|-----------------------|
| Container Service\(UI-Verwaltung in Azure-Portal) | [Containerdienst](https://azure.microsoft.com/services/container-service/) bietet eine schnelle abzurufenden Schritte können [Bereitstellen eines Container-Clusters in Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) basierend auf beliebte orchestratoren wie Mesosphere DC/OS, Kubernetes und Docker Swarm. <br /><br /> Container Service optimiert die Konfiguration dieser Plattformen. Sie müssen nur die Größe, die Anzahl der Hosts und Auswahl der orchestrationstools und Container Service übernimmt den Rest. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker Universal Control Plane\(lokal oder in der Cloud) | [Docker Universal Control Plane](https://docs.docker.com/v1.11/ucp/overview/) ist die professionelle Unternehmens-Cluster-verwaltungslösung von Docker. Sie können Sie Ihren gesamten Cluster von einem zentralen Ort zu verwalten. <br /><br /> Docker Universal Control Plane ist Bestandteil der kommerziellen Produkt Docker Datacenter bietet Docker Swarm, Docker Universal Control Plane und Docker Trusted Registry. <br /><br /> Docker Datacenter kann lokal installiert oder von einer öffentlichen Cloud wie Azure bereitgestellt. | Docker Swarm\(von Container Service unterstützt) |
| Docker Cloud\(auch bekannt als Tutum; SaaS-Cloud) | [Docker Cloud](https://docs.docker.com/docker-cloud/) ist ein gehosteter Dienst (SaaS), das Erstellen und Testen Funktionen für die in docker bereitgestellte Anwendungsbilder, Tools zum Einrichten und Verwalten Ihrer Hostinfrastruktur bietet Orchestrierungsfunktionen und eine Docker-Registrierung und von Bereitstellungsfunktionen zum Automatisieren Ihrer Images für Ihre konkrete Infrastruktur bereitstellen. Sie können Ihr Konto SaaS Docker Cloud für Ihre Infrastruktur in Container Service mit Docker Swarm-Cluster verbinden. | Docker Swarm\(von Container Service unterstützt) |
| Mesosphere Marathon\(lokal oder in der Cloud) | [Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) ist eine Plattform für das Container Produktionsniveau der Orchestrierung und der Scheduler von Mesosphere DC/OS und Apache Mesos. <br /><br /> Es funktioniert mit Mesos (DC/OS basiert auf Apache Mesos) steuern lang ausgeführte Dienste eine [-web-UI für die Verwaltung von Prozess und Container](https://mesosphere.github.io/marathon/docs/marathon-ui.html). Es bietet ein Web-UI-Verwaltungstool | Mesosphere DC/OS\(basierend auf Apache Mesos; von Container Service unterstützt) |
| Google Kubernetes | [Kubernetes](https://kubernetes.io/docs/user-guide/ui/#dashboard-access) umfasst die Orchestrierung, Planung und -Cluster-Infrastruktur. Es ist ein Open Source-Plattform für die Automatisierung von Bereitstellung, Skalierung und Betrieb von anwendungscontainern für Hostcluster, Container ausgerichtete Infrastruktur bereitstellen. | Google Kubernetes\(von Container Service unterstützt) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Eine weitere Option für die Cluster-Bereitstellung und Verwaltung ist Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) ist eine Microservices-Plattform von Microsoft, die containerorchestrierung als auch für Entwickler enthält Programmiermodelle nutzen, um hochgradig skalierbare microserviceanwendungen erstellen. Service Fabric unterstützt Docker in den aktuellen Linux Preview-Versionen, wie in der [Service Fabric-Vorschauversion unter Linux](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere), und für Windows-Container [in der nächsten Version](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric-Management-Tools für folgen:

-   [Azure-Portal für Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) clusterbezogenen Vorgänge (erstellen/aktualisieren/löschen) einen Cluster oder konfigurieren die Infrastruktur (virtuelle Computer, Load Balancer, Netzwerke usw.)

-   [Azure Service Fabric Explorer](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) ist eine spezielle Web-Benutzeroberflächentool, die Einblicke und bestimmte Operationen mit Service Fabric-Cluster aus Sicht der Knoten/VMs und aus der Sicht Anwendungen und Dienste bereitstellt.

>[!div class="step-by-step"]
>[Zurück](run-microservices-based-applications-in-production.md)
>[Weiter](monitor-containerized-application-services.md)