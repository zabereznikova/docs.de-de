---
title: Weitere Optionen für die Container Bereitstellung
description: Weitere Bereitstellungs Optionen für Container mithilfe von Azure
ms.date: 05/13/2020
ms.openlocfilehash: acb022e3d4fd4862c592fa571894e1b8ce17f465
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613758"
---
# <a name="other-container-deployment-options"></a>Weitere Optionen für die Container Bereitstellung

Abgesehen von Azure Kubernetes Service (AKS) können Sie Container auch zum Azure App Service für Container und Azure Container Instances bereitstellen.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>Wann ist es sinnvoll, App Service für Container bereitzustellen?

Einfache Produktionsanwendungen, für die keine Orchestrierung erforderlich ist, eignen sich gut für die Azure App Service von Containern.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Bereitstellen in App Service für Container

Zum Bereitstellen von [für Azure App Service für Container](https://azure.microsoft.com/services/app-service/containers/)benötigen Sie eine Azure Container Registry (ACR)-Instanz und Anmelde Informationen für den Zugriff darauf. Übertragen Sie Ihr Container Image per Push in das ACR-Repository, damit es in ihren Azure App Service abgerufen werden kann. Nach Abschluss des Vorgangs können Sie die APP für die kontinuierliche Bereitstellung konfigurieren. Auf diese Weise werden Updates automatisch bereitgestellt, wenn das Image in ACR geändert wird.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>Wann ist es sinnvoll, für Azure Container Instances bereitzustellen?

Mit [Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) können Sie docker-Container in einer verwalteten, Server losen cloudumgebung ausführen, ohne virtuelle Computer oder Cluster einrichten zu müssen. Es ist eine gute Lösung für Workloads mit kurzer Laufzeit, die in einem isolierten Container ausgeführt werden können. Beachten Sie ACI für einfache Dienste, Testszenarien, Aufgabenautomatisierung und buildaufträge. ACI dreht eine Container Instanz ein, führt die Aufgabe aus und führt Sie dann aus.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Bereitstellen einer APP für Azure Container Instances

Zum Bereitstellen auf [Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)benötigen Sie eine Azure Container Registry (ACR) und Anmelde Informationen für den Zugriff darauf. Sobald Sie Ihr Container Image per Push in das Repository überbringen, ist es für das Abrufen in ACI verfügbar. Sie können mit ACI arbeiten, indem Sie die Azure-Portal oder die Befehlszeilenschnittstelle verwenden. ACR bietet eine enge Integration mit ACI. In Abbildung 3-14 wird gezeigt, wie Sie ein einzelnes Container Image per Push an ACR übersetzen.

![Azure Container Registry Lauf Instanz](./media/acr-runinstance-contextmenu.png)

**Abbildung 3-14**. Azure Container Registry Lauf Instanz

Das Erstellen einer Instanz in ACI kann schnell erfolgen. Geben Sie die Abbild Registrierung, die Azure-Ressourcengruppen Informationen, den zuzuordnenden Arbeitsspeicher und den Port an, der überwacht werden soll. In dieser Schnellstartanleitung erfahren Sie [, wie Sie mithilfe der Azure-Portal eine Container Instanz in ACI](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal)bereitstellen.

Nachdem die Bereitstellung abgeschlossen ist, suchen Sie die IP-Adresse des neu bereitgestellten Containers, und kommunizieren Sie über den Port, den Sie angegeben haben.

Azure Container Instances bietet die schnellste Möglichkeit, einfache containerworkloads in Azure auszuführen. Sie müssen keinen App Service, Orchestrator oder virtuellen Computer konfigurieren. Für Szenarien, in denen Sie eine vollständige Container Orchestrierung, Dienst Ermittlung, automatische Skalierung oder koordinierte Upgrades benötigen, empfehlen wir Azure Kubernetes Service (AKS).

## <a name="references"></a>Referenzen

- [Was ist Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Installieren von Kubernetes mit minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [Minikube im Vergleich zu docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio-Tools für Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [Grundlegendes zum Server losen Kaltstart](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Vorwärmte Azure Functions Instanzen](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Erstellen einer Funktion in Linux mit einem benutzerdefinierten Image (Vorschau)](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Ausführen von Azure Functions in einem docker-Container](https://markheath.net/post/azure-functions-docker)
- [Erstellen einer Funktion in Linux mit einem benutzerdefinierten Image (Vorschau)](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions mit Kubernetes-ereignisgesteuerte automatische Skalierung](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)
- [Canary-Release](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure dev Spaces mit vs Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Azure dev Spaces mit Visual Studio](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)
- [AKS-Pools mit mehreren Knoten](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [AKS-Cluster-AutoScaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [Tutorial: Skalieren von Anwendungen in AKS](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Skalierung und Hosting von Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-scale)
- [Azure Container Instances-Dokumentation](https://docs.microsoft.com/azure/container-instances/)
- [Bereitstellen einer Container Instanz über ACR](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Zurück](scale-containers-serverless.md)
>[Weiter](communication-patterns.md)
