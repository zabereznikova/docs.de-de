---
title: Verwalten von Docker-Produktionsumgebungen
description: Lernen Sie die wichtigsten Aspekte beim Verwalten einer containerbasierten Produktionsumgebung kennen.
ms.date: 08/06/2020
ms.openlocfilehash: dbc5f541478410060420f95f32e4ff5291354075
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160644"
---
# <a name="manage-production-docker-environments"></a>Verwalten von Docker-Produktionsumgebungen

Clusterverwaltung und Orchestrierung sind der Vorgang der Steuerung einer Gruppe von Hosts. Dies kann das Hinzufügen von Hosts zu einem Cluster und Entfernen aus ihm beinhalten, das Abrufen von Informationen über den aktuellen Status von Hosts und Containern und das Starten und Beenden von Prozessen. Clusterverwaltung und Orchestrierung hängen eng mit Planung zusammen, da der Planer Zugriff auf jeden Host im Cluster benötigt, um Dienste planen zu können. Aus diesem Grund wird für beide Zwecke oftmals das gleiche Tool verwendet.

## <a name="container-service-and-management-tools"></a>Containerdienst- und Verwaltungstools

Container Service ermöglicht eine schnelle Bereitstellung beliebter Open-Source-Lösungen für Container-Clustering und die Orchestrierung. Er verwendet Docker-Images, um sicherzustellen, dass Ihre Anwendungscontainer vollständig portabel sind. Mithilfe von Container Service können Sie DC/OS (gestützt durch Mesosphere und Apache Mesos) und Docker Swarm-Cluster mit Azure Resource Manager-Vorlagen oder dem Azure-Portal bereitstellen, um sicherzustellen, dass Sie diese Anwendungen auf Tausende – sogar auf Zehntausende – Container skalieren können.

Sie stellen diese Cluster mithilfe von Azure VM-Skalierungsgruppen bereit. Für die Cluster werden Azure-Netzwerk- und -Speicherangebote genutzt. Für den Zugriff auf Container Service benötigen Sie ein Azure-Abonnement. Mit Container Service können Sie die für den Unternehmenseinsatz geeigneten Azure-Funktionen nutzen, während gleichzeitig die Anwendungsportabilität erhalten bleibt, auch auf den Orchestrierungsebenen.

Tabelle 6–1 listet gängige Verwaltungstools und ihre Beziehung zu Orchestratoren, Planern und der Clusterplattform auf.

**Tabelle 6–1**. Docker-Verwaltungstools

| Verwaltungstools | Beschreibung | Verwandte Orchestratoren |
|------------------|-------------|-----------------------|
| [Azure Monitor für Container](/azure/monitoring/monitoring-container-insights-overview) | Dediziertes Kubernetes-Verwaltungstool von Azure | Azure Kubernetes Services (AKS) |
| [Kubernetes Web UI (Dashboard)](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) | Kubernetes-Verwaltungstool, kann lokale Kubernetes-Cluster überwachen und verwalten | Azure Kubernetes Service (AKS)<br/>Lokales Kubernetes |
| [Azure-Portal für Service Fabric](/azure/service-fabric/service-fabric-cluster-creation-via-portal)<br/>[Azure Service Fabric Explorer](/azure/service-fabric/service-fabric-visualizing-your-cluster) | Online- und Desktopversion zum Verwalten von Service Fabric-Clustern auf Azure, lokal, in der lokalen Entwicklung und in anderen Clouds | Azure Service Fabric |
| [Containerüberwachung (Azure Monitor)](/azure/azure-monitor/insights/containers) | Allgemeine Lösung zur Verwaltung und Überwachung von Containern. Kann Kubernetes-Cluster mithilfe von [Azure Monitor für Container](/azure/monitoring/monitoring-container-insights-overview) verwalten. | Azure Service Fabric<br/>Azure Kubernetes Service (AKS)<br/>Mesosphere DC/OS und andere. |

## <a name="azure-service-fabric"></a>Azure Service Fabric

Eine weitere Möglichkeit für Clusterbereitstellung und -verwaltung ist Azure Service Fabric. [Service Fabric](https://azure.microsoft.com/services/service-fabric/) ist eine Microsoft-Microserviceplattform, die Containerorchestrierung sowie Programmiermodelle für Entwickler enthält, um hochgradig skalierbare Microserviceanwendungen zu erstellen. Service Fabric unterstützt Docker in Linux- und Windows-Containern und kann auf Windows- und Linux-Servern ausgeführt werden.

Im Folgenden finden Sie Verwaltungstools für Service Fabric:

- [Azure-Portal für Service Fabric](/azure/service-fabric/service-fabric-cluster-creation-via-portal) Vorgänge im Clusterkontext (Erstellen/Aktualisieren/Löschen von Clustern) oder Konfigurieren der Infrastruktur von Clustern (VMs, Load Balancer, Netzwerk usw.)

- [Azure Service Fabric Explorer](/azure/service-fabric/service-fabric-visualizing-your-cluster) ist ein spezialisiertes, plattformübergreifendes Tool für Desktop und Webbenutzeroberfläche, das Erkenntnisse und bestimmte Vorgänge auf dem Service Fabric-Cluster ermöglicht, aus der Knoten-/VM-Perspektive und aus der Anwendungs-/Dienstperspektive.

>[!div class="step-by-step"]
>[Zurück](run-microservices-based-applications-in-production.md)
>[Weiter](monitor-containerized-application-services.md)
