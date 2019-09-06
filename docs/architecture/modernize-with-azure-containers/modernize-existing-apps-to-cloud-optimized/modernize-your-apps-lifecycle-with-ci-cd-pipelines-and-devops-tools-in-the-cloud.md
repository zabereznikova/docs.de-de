---
title: Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Modernisieren Sie den Lebenszyklus Ihrer APP mit CI/CD-Pipelines und devops-Tools in der Cloud
ms.date: 04/30/2018
ms.openlocfilehash: 62b6c541780ed3bf82c55e576fa485f811b55b17
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374141"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud

Die heutigen Unternehmen müssen in rasantem Tempo Innovationen entwickeln, um im Marketplace wettbewerbsfähig zu sein. Die Bereitstellung hochwertiger, moderner Anwendungen erfordert devops-Tools und-Prozesse, die für die Implementierung dieses Konstanten Innovations Zeitraums wichtig sind. Mit den richtigen devops-Tools können Entwickler Continuous Deployment optimieren und innovative Anwendungen schneller in die Hand nehmen.

Obwohl Continuous Integration und Bereitstellungs Methoden gut festgelegt sind, führt die Einführung von Containern zu neuen Überlegungen, insbesondere wenn Sie mit Anwendungen mit mehreren Containern arbeiten.

Azure DevOps Services unterstützt Continuous Integration und die Bereitstellung von Anwendungen mit mehreren Containern in einer Vielzahl von Umgebungen über die offiziellen Azure DevOps Services Bereitstellungs Aufgaben:

- [Bereitstellen in einem Azure-Web-App für Container](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [Bereitstellen auf Azure Container Service – Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

Sie können jedoch auch in [docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS bereitstellen, indem Sie Azure DevOps Services skriptbasierten Tasks verwenden.

Um die Flexibilität der Bereitstellung weiterhin zu vereinfachen, bieten diese Tools eine ausgezeichnete Entwicklungsumgebung für die Bereitstellung von Anwendungen für containerworkloads, die eine Auswahl von Entwicklungs-und CI/CD-Lösungen bietet.

In Abbildung 4-12 wird eine Continuous Deployment Pipeline gezeigt, die in Azure Container Service in einem Kubernetes-Cluster bereitgestellt wird.

![Azure DevOps Services Continuous Deployment Pipeline, Bereitstellung in einem Kubernetes-Cluster](./media/image12.png)

**Abbildung 4-12.** Azure DevOps Services Continuous Deployment Pipeline, Bereitstellung in einem Kubernetes-Cluster

>[!div class="step-by-step"]
>[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Weiter](migrate-to-hybrid-cloud-scenarios.md)
