---
title: Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
ms.date: 12/21/2018
ms.openlocfilehash: e7ad76edb659fbacfc85cb398ec0c9fe9e3c66c9
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025250"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud

Heutzutage müssen Unternehmen in rasantem Tempo Innovationen entwickeln, um am Markt wettbewerbsfähig zu sein. Die Bereitstellung hochwertiger, moderner Anwendungen erfordert DevOps-Tools und -Prozesse, die für die Umsetzung dieses ständigen Innovationszyklus entscheidend sind. Mit den richtigen DevOps-Tools können Entwickler Continuous Deployment optimieren und innovative Anwendungen schneller in die Hände der Anwender bringen.

Obwohl die Methoden von Continuous Integration und Deployment gut etabliert sind, führt die Einführung von Containern zu neuen Überlegungen, insbesondere wenn Sie mit Anwendungen mit mehreren Containern arbeiten.

Azure DevOps Services unterstützt Continuous Integration und Deployment von Anwendungen mit mehreren Containern in einer Vielzahl von Umgebungen mithilfe der offiziellen Azure DevOps Services-Bereitstellungsvorgänge:

- [Bereitstellen in einer Azure-Web-App für Container](/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [Bereitstellen in Azure Kubernetes Service](/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

Sie können aber auch in [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) oder DC/OS bereitstellen, indem Sie skriptbasierte Aufgaben von Azure DevOps Services verwenden.

Um die Flexibilität der Bereitstellung weiter zu erhöhen, bieten diese Tools hervorragende „Entwicklung-zu-Test-zu-Produktion“-Bereitstellungserfahrungen für Containerworkloads mit einer Auswahl an Entwicklungs- und CI/CD-Lösungen.

In Abbildung 4-12 wird eine Continuous Deployment-Pipeline bei der Bereitstellung in einem Kubernetes-Cluster in Azure Container Service gezeigt.

![Screenshot von Azure DevOps Services bei der Bereitstellung in einem Kubernetes-Cluster.](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

**Abbildung 4-12.** Continuous Deployment-Pipeline in Azure DevOps Services bei der Bereitstellung in einem Kubernetes-Cluster

>[!div class="step-by-step"]
>[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Weiter](migrate-to-hybrid-cloud-scenarios.md)
