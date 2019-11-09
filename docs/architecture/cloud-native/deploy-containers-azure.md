---
title: Bereitstellen von Containern in Azure
description: Bereitstellen von Containern in Azure mit Azure Container Registry, Azure Kubernetes Service und Azure dev Spaces.
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840484"
---
# <a name="deploying-containers-in-azure"></a>Bereitstellen von Containern in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Container bieten viele Vorteile, von denen eine Portabilität ist. Sie können problemlos denselben Container nutzen, den Sie lokal entwickelt und getestet haben, und ihn in Azure bereitstellen, wo er Ihre APP in Staging-und Produktionsumgebungen ausführen kann. Azure bietet eine Reihe von Optionen für das Container basierte App-Hosting und unterstützt ebenso verschiedene Möglichkeiten der Bereitstellung. Der häufigste und flexibelste Ansatz besteht darin, Ihre Container in Azure Container Registry (ACR) bereitzustellen, wo Sie von allen Diensten zugänglich sind, die Sie zum Hosten verwenden möchten. Azure Web-App für Container, Azure Kubernetes Services (AKS) und Azure Container instance (ACI) können auf Container Images zugreifen, die per pushübertragung an ACR übermittelt wurden.

## <a name="azure-container-registry"></a>Azure Container Registry

Mit Azure Container Registry (ACR) können Sie Images für alle Ihre Container Bereitstellungen erstellen, speichern und verwalten. Es gibt auch andere Container Registrierungen (öffentlich und privat), auf denen Sie Container bereitstellen können. Der Vorteil von ACR gegenüber anderen Optionen besteht darin, dass Sie Ihre Images in der Nähe Ihrer Produktionsumgebung halten und die Build-und Bereitstellungs Zeiten verbessern können. Sie können diese auch mit denselben Sicherheitsverfahren sichern, die Sie für die restlichen Azure-Ressourcen verwenden, um die Sicherheit zu verbessern und den Ressourcen Verwaltungsaufwand zu verringern.

Sie [erstellen eine Container Registrierung über das Azure-Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) oder [mithilfe der Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) oder [PowerShell-Tools](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell). Zum Erstellen einer neuen Container Registrierung sind nur ein Azure-Abonnement, eine Ressourcengruppe und ein eindeutiger Name erforderlich. In Abbildung 3-11 werden die grundlegenden Optionen zum Erstellen einer Registrierung gezeigt, die unter " *registryname*. azurecr.IO" gehostet werden.

![Erstellen der Container Registrierung](./media/create-container-registry.png)
**Abbildung 3-11**. Erstellen einer Container Registrierung

Nachdem Sie eine Registrierung erstellt haben, müssen Sie sich damit authentifizieren, bevor Sie Sie verwenden können. In der Regel melden Sie sich mit dem Azure CLI Befehl bei der Registrierung an:

```azurecli
az acr login --name *registryname*
```

Nachdem Sie eine Registrierung in Azure Container Registry erstellt haben, können Sie Container Images mithilfe von Docker-Befehlen per Push darauf überführen. Bevor Sie dies tun können, müssen Sie jedoch zuerst das Image mit dem voll qualifizierten Namen (URL) Ihres ACR-Anmelde Servers markieren. Dies hat das Format " *registryname*. azurecr.IO".

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

Nachdem Sie das Image markiert haben, verwenden Sie den `docker push`-Befehl, um das Image per Push an Ihre ACR-Instanz zu überführen.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

Wenn Sie ein Image per Push in die Registrierung übersetzen, empfiehlt es sich, das Image mit diesem Befehl aus der lokalen docker-Umgebung zu entfernen:

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

Entwickler sollten selten direkt von ihren Computern in eine Container Registrierung pushen. Stattdessen sollte eine in einem Tool wie Azure devops definierte Buildpipeline für diesen Prozess verantwortlich sein. Weitere Informationen finden Sie im [Kapitel "Cloud-Native devops](devops.md)".

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Wenn Ihre Container basierte Anwendung mehrere Container umfasst, möchten Sie wahrscheinlich die Interaktionen zwischen den Containern mithilfe eines *Orchestrator* wie Kubernetes definieren und verwalten. Nachdem Sie Ihre Container Images in ACR bereitgestellt haben, können Sie Azure Kubernetes Services problemlos so konfigurieren, dass aktualisierte Images automatisch von ACR bereitgestellt werden. Mit einer vollständigen CI/CD-Pipeline können Sie eine Canary- [Release](https://martinfowler.com/bliki/CanaryRelease.html) -Strategie konfigurieren, um das Risiko bei der schnellen Bereitstellung von Updates zu minimieren. Die neue Version der APP wird anfänglich in der Produktion konfiguriert, ohne dass Datenverkehr an Sie weitergeleitet wird, und dann wird eine kleine Anzahl von Benutzern an die neu bereitgestellte Version der APP weitergeleitet. Wenn das Team Vertrauen in die neue Version der Software erlangt, werden weitere Instanzen der neuen Version eingeführt, und die Instanzen der früheren Version werden zurückgezogen. AKS unterstützt diese Art der Bereitstellung problemlos.

Wie bei den meisten Ressourcen in Azure können Sie Azure Kubernetes-Cluster über das Portal oder mithilfe von Befehlszeilen Tools oder Infrastruktur Automatisierungstools wie Helm oder TERRAFORM erstellen. Um mit einem neuen Cluster zu beginnen, müssen Sie die folgenden Informationen angeben:

- Azure-Abonnement
- Ressourcengruppe
- Kubernetes Cluster Name
- Region
- Kubernetes-Version
- DNS-Namens Präfix
- Knoten Größe
- Knoten Anzahl

Diese Informationen sind für den Einstieg ausreichend. Im Rahmen des Erstellungs Prozesses im Azure-Portal können Sie auch Optionen für die folgenden Cluster Features konfigurieren:

- Skalieren
- Authentifizierung
- Netzwerk
- Überwachung
- Tags

In dieser Schnellstartanleitung wird die Bereitstellung [eines AKS-Clusters mithilfe der Azure-Portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)erläutert.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Komplexe Kubernetes Cluster können bedeutende Ressourcen zum Hosten erfordern, was es Entwicklern erschwert, die gesamte Anwendung auf einem einzelnen Computer (insbesondere einem Laptop) auszuführen. Azure dev Spaces bietet eine Lösung dafür, dass Entwickler mit ihren eigenen Versionen von Azure Kubernetes-Clustern arbeiten können, die in Azure gehostet werden. Azure dev Spaces wurde entwickelt, um die Entwicklung von auf einem Dienst basierenden Anwendungen mit AKS zu vereinfachen.

Um den Wert Azure dev Spaces zu verstehen, lassen Sie mich dieses Zitat von der "Gabe Monroy", "PM"-Führung von Containern bei Microsoft Azure Teilen:

"Stellen Sie sich vor, Sie sind ein neuer Mitarbeiter, der versucht, einen Fehler in einer komplexen mikroservicesanwendung zu beheben, bestehend aus Dutzenden von Komponenten, die jeweils über eigene Konfigurations-und Sicherungsdienste verfügen. Um zu beginnen, müssen Sie Ihre lokale Entwicklungsumgebung so konfigurieren, dass Sie die Produktion imitieren kann, einschließlich der Einrichtung Ihrer IDE, der Erstellung von Toolkette, der Dienst Abhängigkeiten in Containern, einer lokalen Kubernetes-Umgebung, von Mobs zum Sichern von Diensten usw. Mit der gesamten Zeit, die zum Einrichten der Entwicklungsumgebung erforderlich ist, kann die Behebung des ersten Fehlers einige Tage in Anspruch nehmen.

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

Als nächstes können Sie den Befehl "`azds prep`" verwenden, um die erforderlichen docker-und Helm-Diagramm Ressourcen für die Ausführung der Anwendung zu generieren. Anschließend führen Sie den Code in AKS mithilfe von `azds up`aus. Wenn Sie diesen Befehl zum ersten Mal ausführen, wird das Helm-Diagramm installiert, und die Container werden gemäß Ihren Anweisungen erstellt und bereitgestellt. Dies kann bei der ersten Ausführung einige Minuten dauern. Nachdem Sie jedoch Änderungen vorgenommen haben, können Sie mithilfe `azds space select` eine Verbindung mit Ihrem eigenen untergeordneten Entwicklungsbereich herstellen und dann Ihre Updates in Ihrem isolierten untergeordneten Entwicklungsbereich bereitstellen und Debuggen. Sobald Sie Ihren Entwicklungsbereich eingerichtet haben, können Sie Updates an ihn senden, indem Sie den `azds up` Befehl erneut ausgeben, oder Sie können die integrierten Tools in Visual Studio oder Visual Studio Code verwenden. Mit vs Code verwenden Sie die Befehls Palette, um eine Verbindung mit dem Entwicklungsbereich herzustellen. In Abbildung 3-12 wird gezeigt, wie Sie Ihre Webanwendung mithilfe von Azure dev Spaces in Visual Studio starten.

![Herstellen einer Verbindung mit Azure dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Abbildung 3-12**. Herstellen einer Verbindung mit Azure dev Spaces in Visual Studio

## <a name="references"></a>Verweise

- [Canary-Release](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure dev Spaces mit vs Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Azure dev Spaces mit Visual Studio](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
>[Zurück](combine-containers-serverless-approaches.md)
>[Weiter](scale-containers-serverless.md)
