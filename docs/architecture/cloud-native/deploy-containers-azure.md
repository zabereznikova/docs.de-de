---
title: Bereitstellen von Containern in Azure
description: Bereitstellen von Containern in Azure mit Azure Container Registry, Azure Kubernetes Service und Azure dev Spaces.
ms.date: 04/13/2020
ms.openlocfilehash: 57a4739d39b8ad022d699d54255f56f16d305440
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895600"
---
# <a name="deploying-containers-in-azure"></a>Bereitstellen von Containern in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Wir haben die Container in diesem Kapitel und in Kapitel 1 erörtert. Wir haben festgestellt, dass Container viele Vorteile für cloudanwendungen bieten, einschließlich Portabilität. In der Azure-Cloud können Sie dieselben containerisierten Dienste in Staging-und Produktionsumgebungen bereitstellen. Azure bietet mehrere Optionen für das Hosting dieser containerisierten Workloads:

- Azure Kubernetes Services (AKS)
- Azure Container Instance (ACI)
- Azure-Web-Apps für Container

## <a name="azure-container-registry"></a>Azure Container Registry

Beim containerialisieren eines microservice müssen Sie zuerst einen Build-Container "Image" erstellen. Das Image ist eine binäre Darstellung des Dienst Codes, der Abhängigkeiten und der Laufzeit. Während Sie manuell ein Image mit dem `Docker Build` Befehl aus der Docker-API erstellen können, ist es besser, es im Rahmen eines automatisierten Buildprozesses zu erstellen.

Nach der Erstellung werden Container Images in Container Registrierungen gespeichert. Sie ermöglichen Ihnen das Erstellen, speichern und Verwalten von Container Images. Es sind zahlreiche Registrierungen verfügbar (öffentlich und privat). Azure Container Registry (ACR) ist ein vollständig verwalteter Container Registrierungsdienst in der Azure-Cloud. Sie speichert Ihre Images innerhalb des Azure-Netzwerks und verkürzt die Zeit für die Bereitstellung auf Azure-Container Hosts. Sie können diese auch mit denselben Sicherheits-und Identitäts Prozeduren sichern, die Sie auch für andere Azure-Ressourcen verwenden.

Sie erstellen eine Azure Container Registry mithilfe der Tools [Azure-Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)oder [PowerShell](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell). Das Erstellen einer Registrierung in Azure ist einfach. Hierfür sind ein Azure-Abonnement, eine Ressourcengruppe und ein eindeutiger Name erforderlich. In Abbildung 3-11 werden die grundlegenden Optionen zum Erstellen einer Registrierung gezeigt, die unter `registryname.azurecr.io`gehostet wird.

![Erstellen einer Containerregistrierung](./media/create-container-registry.png)

**Abbildung 3-11**. Erstellen einer Containerregistrierung

Nachdem Sie die Registrierung erstellt haben, müssen Sie sich damit authentifizieren, bevor Sie Sie verwenden können. In der Regel melden Sie sich mit dem Azure CLI Befehl bei der Registrierung an:

```azurecli
az acr login --name *registryname*
```

Nachdem Sie sich authentifiziert haben, können Sie Container Images mithilfe von Docker-Befehlen per Push darauf überführen. Bevor Sie dies tun können, müssen Sie das Image jedoch mit dem voll qualifizierten Namen (URL) Ihres ACR-Anmelde Servers markieren. Er hat das Format " *registryname*. azurecr.IO".

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

Nachdem Sie das Image markiert haben, verwenden Sie den `docker push` Befehl, um das Image per Push an Ihre ACR-Instanz zu überführen.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

Wenn Sie ein Image per Push in die Registrierung übersetzen, empfiehlt es sich, das Image mit diesem Befehl aus der lokalen docker-Umgebung zu entfernen:

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

Als bewährte Verfahrensweise sollten Entwickler Images nicht manuell in eine Container Registrierung übersetzen. Stattdessen sollte eine Buildpipeline, die in einem Tool wie GitHub oder Azure devops definiert ist, für diesen Prozess verantwortlich sein. Weitere Informationen finden Sie im [Kapitel "Cloud-Native devops](devops.md)".

## <a name="acr-tasks"></a>ACR-Aufgaben

[ACR-Aufgaben](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) sind eine Reihe von Funktionen, die im Azure Container Registry verfügbar sind. Es erweitert den [Entwicklungs Durchlauf der inneren Schleife](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) durch das entwickeln und Verwalten von Container Images in der Azure-Cloud. Anstatt einen `docker build` und lokal auf `docker push` dem Entwicklungs Computer aufzurufen, werden diese automatisch von ACR-Aufgaben in der Cloud verarbeitet.

Mit dem folgenden Befehl AZ CLI wird ein Container Image erstellt und per Push an ACR übertragen:

```azurecli
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container regsitry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

Wie Sie aus dem vorherigen Befehls Block sehen können, ist es nicht erforderlich, docker Desktop auf Ihrem Entwicklungs Computer zu installieren. Außerdem können Sie ACR-Task-Trigger so konfigurieren, dass Container Images sowohl auf Quell Code-als auch auf Basis Image Updates neu erstellt werden.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

In diesem Kapitel wurde Azure Kubernetes Service (AKS) ausführlich erläutert. Wir haben gesehen, dass es sich um den de-facto-containerorchestrator handelt, der Container in der Cloud native Anwendungen verwaltet.

Nachdem Sie ein Abbild in einer Registrierung wie ACR bereitgestellt haben, können Sie AKS so konfigurieren, dass es automatisch per Pull und bereitgestellt wird. Wenn eine CI/CD-Pipeline vorhanden ist, können Sie eine [Canary-Release](https://martinfowler.com/bliki/CanaryRelease.html) -Strategie konfigurieren, um das Risiko bei der schnellen Bereitstellung von Updates zu minimieren. Die neue Version der APP wird anfänglich in der Produktion konfiguriert, ohne dass Datenverkehr an Sie weitergeleitet wird. Anschließend leitet das System einen kleinen Prozentsatz der Benutzer an die neu bereitgestellte Version weiter. Wenn das Team Vertrauen in die neue Version erhält, kann es mehr Instanzen einführen und das alte abkoppeln. AKS unterstützt diese Art der Bereitstellung problemlos.

Wie bei den meisten Ressourcen in Azure können Sie einen Azure Kubernetes Service-Cluster erstellen, indem Sie das Portal, die Befehlszeile oder die Automatisierungstools wie Helm oder TERRAFORM verwenden. Um mit einem neuen Cluster zu beginnen, müssen Sie die folgenden Informationen angeben:

- Azure-Abonnement
- Resource group
- Kubernetes-Clustername
- Region
- Kubernetes-Version
- DNS-Namenspräfix
- Knotengröße
- Knotenanzahl

Diese Informationen sind für den Einstieg ausreichend. Im Rahmen des Erstellungs Prozesses in der Azure-Portal können Sie auch Optionen für die folgenden Features Ihres Clusters konfigurieren:

- Skalieren
- Authentifizierung
- Netzwerk
- Überwachung
- Tags

In dieser Schnellstartanleitung wird die Bereitstellung [eines AKS-Clusters mithilfe der Azure-Portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)erläutert.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Native Cloud-Anwendungen können schnell und komplex wachsen, sodass beträchtliche Compute-Ressourcen ausgeführt werden müssen. In diesen Szenarien kann die gesamte Anwendung nicht auf einem Entwicklungs Computer (vor allem auf einem Laptop) gehostet werden. Azure dev Spaces ist darauf ausgelegt, dieses Problem mithilfe von AKS zu beheben. Es ermöglicht Entwicklern die Arbeit mit einer lokalen Version ihrer Dienste, während der Rest der Anwendung in einem AKS-Entwicklungs Cluster gehostet wird.

Entwickler verwenden eine ausgeführte (Entwicklungs-) Instanz in einem AKS-Cluster, der die gesamte containerisierte Anwendung enthält. Sie verwenden jedoch persönliche Plätze, die auf Ihrem Computer eingerichtet sind, um ihre Dienste lokal zu entwickeln. Wenn Sie fertig sind, testen Sie Sie von End-to-End im AKS-Cluster, ohne Abhängigkeiten zu replizieren. Azure dev Spaces führt Code vom lokalen Computer mit Diensten in AKS zusammen. Entwickler können Code mithilfe von Visual Studio oder Visual Studio Code schnell direkt in Kubernetes durchlaufen und Debuggen.

Um den Wert Azure dev Spaces zu verstehen, lassen Sie mich dieses Zitat von der "Gabe Monroy", "PM"-Führung von Containern bei Microsoft Azure Teilen:

> "Stellen Sie sich vor, Sie sind ein neuer Mitarbeiter, der versucht, einen Fehler in einer komplexen mikroservicesanwendung zu beheben, bestehend aus Dutzenden von Komponenten, die jeweils über eigene Konfigurations-und Sicherungsdienste verfügen. Um zu beginnen, müssen Sie Ihre lokale Entwicklungsumgebung so konfigurieren, dass Sie die Produktion imitieren kann, einschließlich der Einrichtung Ihrer IDE, der Erstellung von Toolkette, der Dienst Abhängigkeiten in Containern, einer lokalen Kubernetes-Umgebung, von Mobs zum Sichern von Diensten usw. Mit der gesamten Zeit, die zum Einrichten der Entwicklungsumgebung erforderlich ist, kann die Behebung des ersten Fehlers einige Tage in Anspruch nehmen.
> Oder Sie können dev Spaces und AKS verwenden. "

Der Prozess zum Arbeiten mit Azure dev Spaces umfasst die folgenden Schritte:

1. Erstellen Sie den Entwicklungsbereich.
2. Konfigurieren Sie den Stamm Entwicklerbereich.
3. Konfigurieren Sie einen untergeordneten Entwicklungsbereich (für Ihre eigene Version des Systems).
4. Stellen Sie eine Verbindung mit dem Entwicklungsbereich her.

Alle diese Schritte können mit dem Azure CLI und den neuen `azds` Befehlszeilen Tools ausgeführt werden. Wenn Sie z. b. einen neuen Azure dev-Speicher für einen bestimmten Kubernetes-Cluster erstellen möchten, verwenden Sie einen Befehl wie den folgenden:

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

Als nächstes können Sie den `azds prep` Befehl verwenden, um die erforderlichen docker-und Helm-Diagramm Ressourcen für die Ausführung der Anwendung zu generieren. Anschließend führen Sie den Code in AKS mithilfe `azds up`von aus. Wenn Sie diesen Befehl zum ersten Mal ausführen, wird das Helm-Diagramm installiert. Die Container werden gemäß Ihren Anweisungen erstellt und bereitgestellt. Diese Aufgabe kann einige Minuten in Anspruch nehmen, wenn Sie zum ersten Mal ausgeführt wird. Nachdem Sie jedoch Änderungen vorgenommen haben, können Sie mithilfe `azds space select` von eine Verbindung mit Ihrem eigenen untergeordneten Entwicklungsbereich herstellen und dann Ihre Updates in Ihrem isolierten untergeordneten Entwicklungsbereich bereitstellen und Debuggen. Sobald Sie Ihren Entwicklungsbereich eingerichtet haben, können Sie Updates an ihn senden, indem Sie den `azds up` Befehl erneut ausgeben, oder Sie können integrierte Tools in Visual Studio oder Visual Studio Code verwenden. Mit vs Code verwenden Sie die Befehls Palette, um eine Verbindung mit dem Entwicklungsbereich herzustellen. In Abbildung 3-12 wird gezeigt, wie Sie Ihre Webanwendung mithilfe von Azure dev Spaces in Visual Studio starten.

![Stellen Sie in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
in**Abbildung 3-12**eine Verbindung mit Azure dev Spaces her. Herstellen einer Verbindung mit Azure dev Spaces in Visual Studio

>[!div class="step-by-step"]
>[Zurück](combine-containers-serverless-approaches.md)
>[Weiter](scale-containers-serverless.md)
