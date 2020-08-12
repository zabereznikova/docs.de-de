---
title: Schritte im Outer-Loop-DevOps-Workflow für eine Docker-Anwendung
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.date: 08/06/2020
ms.openlocfilehash: 1a973407d59484899f99fb6e326b8d7c8e97079b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915223"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Erstellen von CI/CD-Pipelines in Azure DevOps Services für eine .NET Core-Anwendung für Container und anschließendes Bereitstellen in einem Kubernetes-Cluster

In Abbildung 5–12 können Sie das DevOps-Szenario End-to-End betrachten, das Codeverwaltung, Codekompilierung, das Erstellen von Docker-Images, das Hochladen von Docker-Images in eine Docker-Registrierung und schließlich die Bereitstellung auf einem Kubernetes-Cluster in Azure umfasst.

![Workflow: Beginnt auf dem Entwicklungscomputer. Mit dem Hochladen in ein Repository beginnt die Build/CI-Aufgabe, die ein benutzerdefiniertes Image verwendet, das in eine Docker-Registrierung hochgeladen und schließlich von der CD/Bereitstellungsaufgabe für das Hochladen auf AKS verwendet wird.](media/docker-workflow-ci-cd-aks.png)

**Abbildung 5-12**. CI/CD-Szenario, in dem Docker-Images erstellt und auf einem Kubernetes-Cluster in Azure bereitgestellt werden

Es ist wichtig, hervorzuheben, dass die zwei Pipelines Build/CI und Release/CD durch die Docker-Registrierung (z.B. Docker Hub oder Azure Container Registry) verbunden sind. Die Docker-Registrierung stellt einen der wichtigsten Unterschiede im Vergleich mit einem herkömmlichen CI/CD-Prozess ohne Docker dar.

Wie in Abbildung 5–13 dargestellt, ist die erste Phase die Build/CI-Pipeline. In Azure DevOps Services können Sie Build/CI-Pipelines erstellen, die das Kompilieren des Codes, das Erstellen der Docker-Images und das Hochladen in eine Docker-Registrierung wie Docker Hub oder Azure Container Registry übernehmen.

![Browseransicht von Azure DevOps, Aufgabendefinition des Buildprozesses.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Abbildung 5-13**. Build/CI-Pipeline in Azure DevOps beim Erstellen von Docker-Images und Pushen von Images in eine Docker-Registrierung

In der zweiten Phase wird eine Bereitstellungs-/Releasepipeline erstellt. In Azure DevOps Services können Sie auf einfache Weise eine Bereitstellungspipeline mit einem Kubernetes-Cluster als Ziel erstellen, indem Sie die Kubernetes-Aufgaben für Azure DevOps Services verwenden, wie in Abbildung 5–14 dargestellt.

![Browseransicht von Azure DevOps, Aufgabendefinition von „Für Kubernetes bereitstellen“](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Abbildung 5-14**. Release/CD-Pipeline in Azure DevOps Services bei der Bereitstellung auf einem Kubernetes-Cluster

> [!Exemplarische Vorgehensweise] Bereitstellung von eShopModernized für Kubernetes:
>
> Eine ausführliche exemplarische Vorgehensweise zur Bereitstellung in Kubernetes mithilfe von Azure DevOps-CI/CD-Pipelines finden Sie in diesem Beitrag: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Zurück](docker-application-outer-loop-devops-workflow.md)
>[Weiter](../run-manage-monitor-docker-environments/index.md)
