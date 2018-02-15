---
title: Aktualisieren Sie Ihre app-Lebenszyklus mit CI-CD-Pipelines und DevOps-Tools in der cloud
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Aktualisieren Sie Ihre app-Lebenszyklus mit CI-CD-Pipelines und DevOps-Tools in der cloud"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c0b87d01c1305695dacaf3ba112b387de2ee0cc1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Aktualisieren Sie Ihre app-Lebenszyklus mit CI-CD-Pipelines und DevOps-Tools in der cloud

Moderne Unternehmen müssen Innovationsbereitschaft mit einer schnellen Geschwindigkeit im Marketplace Wettbewerber sein. Bereitstellen von hoher Qualität, moderne Anwendungen erfordert, DevOps-Tools und Prozesse, die zum Implementieren dieser slm Innovationen von entscheidender Bedeutung sind. Entwickler können mit den richtigen DevOps-Tools optimieren Sie die kontinuierliche Bereitstellung und innovative Anwendungen in die Hände von Benutzern schneller abrufen.

Obwohl continuous Integration und kontinuierlicher Bereitstellung Practices Bereich etabliert sind, ergeben sich die Einführung von Containern neue Faktoren, besonders bei der Arbeit mit Multi-containeranwendungen.

Visual Studio Team Services unterstützt die fortlaufende Integration und Bereitstellung von Multi-containeranwendungen mit einer Vielzahl von Umgebungen über die offiziellen Team Services-Bereitstellungsaufgaben:

-   [Die eigenständige Version von Docker-Host-VM bereitstellen](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux- oder WindowsServer 2016 oder höher)

-   [Bereitstellen von Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [Bereitstellen Sie auf Azure-Container Service – Kubernetes](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

Aber auch zu bereitstellen [Docker Containerhostclustern](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) oder DC/OS mit Team Services skriptbasierte Aufgaben.

Zum Fortsetzen des Vorgangs Erleichterung der Bereitstellung Flexibilität bieten diese Tools ausgezeichnete Dev auf Test, Produktions-Bereitstellung für Container-Arbeitslasten mithilfe einer Auswahl von Entwicklungs- und CI-CD Lösungen auftritt.

Abbildung 4-12 zeigt eine dauerhafte Bereitstellung-Pipeline, die zu einem Cluster Kubernetes im Azure-Container-Dienst bereitstellt.

![Visual Studio Team Services dauerhafte Bereitstellungspipeline zu einem Cluster Kubernetes bereitstellen](./media/image12.png)

> **Abbildung 4-12.** Visual Studio Team Services dauerhafte Bereitstellungspipeline zu einem Cluster Kubernetes bereitstellen

>[!div class="step-by-step"]
[Zurück](modernize-your-apps-with-monitoring-and-telemetry.md)
[Weiter](migrate-to-hybrid-cloud-scenarios.md)
