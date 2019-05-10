---
title: Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Modernisieren des Lebenszyklus Ihrer app mit CI-/CD-Pipelines und DevOps-Tools in der cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 7f2637db3ed43f98d5b3b0cac43f7221388770fc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611669"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernisieren des Lebenszyklus Ihrer App mit CI-/CD-Pipelines und DevOps-Tools in der Cloud

Heutige Unternehmen müssen Innovationen mit einer schnellen Geschwindigkeit im Marketplace konkurrenzfähig sein. Bereitstellung qualitativ hochwertiger, moderne Anwendungen erfordert, DevOps-Tools und Prozesse, die zum Implementieren dieser Konstanten Zyklus der Innovation von entscheidender Bedeutung sind. Entwickler können mit den richtigen DevOps-Tools kontinuierliche Bereitstellung optimieren und schneller, innovative Anwendungen in die Hände von Benutzern zu erhalten.

Obwohl continuous Integration und Continuous Deployment-Verfahren etabliert sind, ergeben sich die Einführung von Containern neue Faktoren, insbesondere dann, wenn Sie mit Anwendungen mit mehreren Containern arbeiten.

Azure DevOps-Services unterstützt continuous Integration und Bereitstellung von Anwendungen mit mehreren Containern mit einer Vielzahl von Umgebungen über die offiziellen Azure DevOps-Dienste-Bereitstellungsaufgaben:

- [Für eigenständige Docker-Host-VM bereitstellen](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux oder WindowsServer 2016 oder höher)

- [Bereitstellen in Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

- [Bereitstellen von Azure Container Service – Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

Aber auch zu bereitstellen [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS, mithilfe von Azure DevOps-Dienste skriptbasierte Aufgaben.

Zum Fortsetzen des Vorgangs Erleichterung der Bereitstellung Flexibilität bieten diese Tools ausgezeichnete Entwicklung, Test, Produktion Deployment für containerworkloads mit einer Auswahl von Entwicklung und CI/CD-Lösungen auftritt.

Abbildung 4-12 zeigt eine continuous Deployment-Pipeline, die in einem Kubernetes-Cluster in Azure Container Service bereitstellt.

![Azure DevOps-Dienste continuous Deployment-Pipeline, um einen Kubernetes-Cluster bereitstellen](./media/image12.png)

> **Abbildung 4-12.** Azure DevOps-Dienste continuous Deployment-Pipeline, um einen Kubernetes-Cluster bereitstellen

>[!div class="step-by-step"]
>[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Weiter](migrate-to-hybrid-cloud-scenarios.md)