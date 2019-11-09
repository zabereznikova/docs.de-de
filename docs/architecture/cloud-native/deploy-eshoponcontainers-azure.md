---
title: Bereitstellen von eShopOnContainers in Azure
description: Bereitstellen der eshoponcontainers-Anwendung mithilfe von Azure Kubernetes Service, Helm und Devspaces.
ms.date: 06/30/2019
ms.openlocfilehash: 21033cc904dc595193c69f3452ce2522740f8ff6
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840490"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Bereitstellen von eShopOnContainers in Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die Logik, die die eshoponcontainers-Anwendung unterstützt, kann von Azure mithilfe einer Vielzahl von Diensten unterstützt werden. Die empfohlene Vorgehensweise ist die Nutzung von Kubernetes mit Azure Kubernetes Service (AKS). Dies kann mit der Helm-Bereitstellung kombiniert werden, um eine leicht wiederholende Infrastruktur Konfiguration sicherzustellen Optional können Entwickler im Rahmen Ihres Entwicklungsprozesses Azure dev Spaces für Kubernetes nutzen. Eine weitere Möglichkeit besteht darin, die Funktionen der App mithilfe von Features von Azure Server less wie Azure Functions und Azure Logic apps zu hosten.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Wenn Sie die Anwendung eshoponcontainers in Ihrem eigenen AKS-Cluster hosten möchten, besteht der erste Schritt darin, den Cluster zu erstellen. Hierzu können Sie das Azure-Portal verwenden, das Sie durch die erforderlichen Schritte führt, oder Sie können die Azure CLI verwenden. Achten Sie dabei darauf, dass Sie die rollenbasierte Access Control (Role-Based, RBAC) und das Anwendungs Routing aktivieren. In der Dokumentation zu eshoponcontainers werden die Schritte zum Erstellen eines eigenen AKS-Clusters beschrieben. Nachdem der Cluster erstellt wurde, müssen Sie den Zugriff auf das Kubernetes-Dashboard aktivieren. an diesem Punkt sollten Sie zum Kubernetes-Dashboard navigieren können, um den Cluster zu verwalten.

Nachdem der Cluster erstellt und konfiguriert wurde, können Sie die Anwendung mithilfe von Helm und Tiller bereitstellen.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>Bereitstellen in Azure Kubernetes Dienst mithilfe von Helm

Bei einfachen bereit Stellungen für AKS können benutzerdefinierte CLI-Skripts oder einfache Bereitstellungs Dateien verwendet werden. komplexere Anwendungen sollten jedoch ein Tool für die Abhängigkeits Verwaltung wie Helm verwenden. Helm wird von der Cloud Native Computing Foundation verwaltet und unterstützt Sie beim definieren, installieren und Upgraden von Kubernetes-Anwendungen. Helm besteht aus einem Befehlszeilen Client, Helm, der Helm-Diagramme verwendet, und einer in-Cluster-Komponente (Tiller). Helm-Diagramme verwenden standardmäßige YAML-formatierte Dateien, um einen zugehörigen Satz von Kubernetes-Ressourcen zu beschreiben, und werden in der Regel neben der von Ihnen beschriebenen Anwendung versioniert. Helm-Diagramme reichen von einfachen bis zu komplexen Anforderungen, je nach den Anforderungen der von Ihnen beschriebenen Installation.

Sie finden die eshoponcontainers Helm-Diagramme im Ordner "/k8s/Helm". In Abbildung 2-6 wird dargestellt, wie die verschiedenen Komponenten der Anwendung in einer Ordnerstruktur angeordnet sind, die von Helm zum Definieren und Verwalten von bereit Stellungen verwendet wird.

![eshoponcontainers-Architektur](./media/eshoponcontainers-helm-folder.png)
**Abbildung 2-6**. Der Ordner "eshoponcontainers Helm".

Jede einzelne Komponente wird mit einem `helm install` Befehl installiert. Diese Befehle können problemlos in Skripts geschrieben werden, und eshoponcontainers stellt ein "alle bereitstellen"-Skript bereit, das die verschiedenen Komponenten durchläuft und Sie mithilfe der jeweiligen Helm-Diagramme installiert. Das Ergebnis ist ein wiederholbarer Prozess, der mit der Anwendung in der Quell Code Verwaltung versioniert ist, die jeder Person im Team mit einem einzeiligen Skript Befehl in einem AKS-Cluster bereitstellen kann. Insbesondere in Kombination mit Azure dev Spaces ist es für Entwickler einfach, Ihre individuellen Änderungen an Ihren auf dem eigenen Dienst basierenden cloudbasierten apps zu diagnostizieren und zu testen.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Azure dev Spaces unterstützt einzelne Entwickler bei der Entwicklung bei der Host Ausführung ihrer eigenen eindeutigen Version der AKS-Cluster in Azure. Dies minimiert die Anforderungen an den lokalen Computer und ermöglicht es Teammitgliedern, schnell zu sehen, wie sich Ihre Änderungen in einer echten AKS-Umgebung Verhalten. Azure dev Spaces bietet eine Befehlszeilenschnittstelle, mit der Entwickler ihre Entwickler Räume verwalten und bei Bedarf auf einem bestimmten untergeordneten Entwicklungsbereich bereitstellen können. Auf jeden untergeordneten Entwicklungsbereich wird unter Verwendung einer eindeutigen URL-Unterdomäne verwiesen. Dies ermöglicht die parallele Bereitstellung von geänderten Clustern, sodass einzelne Entwickler Konflikte zwischen den einzelnen in Bearbeitung befindlichen Aufgaben vermeiden können. In Abbildung 2-7 können Sie sehen, wie Entwickler Susie ihre eigene Version des Bikes-mikroservice in Ihrem Entwicklungsbereich bereitgestellt haben. Sie kann Ihre Änderungen dann mithilfe einer benutzerdefinierten URL testen, beginnend mit dem Namen Ihres Platzes (Susie.s.dev.MyApp.EUS.azds.IO).

![eshoponcontainers-Architektur](./media/azure-devspaces-one.png)
**Abbildung 2-7**. Developer Susie stellt eine eigene Version des Bikes-mikroservice bereit und testet Sie.

Gleichzeitig passt der Entwickler John den "Reservierungen"-mikroservice an und muss seine Änderungen testen. Er ist in der Lage, seine Änderungen in seinem eigenen Entwicklungsbereich bereitzustellen, ohne in Konflikt mit den Änderungen von Susie zu stehen, wie in Abbildung 2-8 dargestellt. Er kann seine Änderungen mit seiner eigenen URL testen, der der Name seines leer Zeichens (John.s.dev.MyApp.EUS.azds.IO) vorangestellt ist.

![eshoponcontainers-Architektur](./media/azure-devspaces-two.png)
**Abbildung 2-8**. Entwickler John stellt seine eigene Version des Reservierungs-und Test Dienstanbieter bereit und testet diese, ohne mit anderen Entwicklern in Konflikt zu geraten.

Mithilfe Azure dev Spaces können Teams direkt mit AKS arbeiten, während Sie Ihre Änderungen unabhängig voneinander ändern, bereitstellen und testen. Diese Vorgehensweise verringert den Bedarf an separaten dedizierten gehosteten Umgebungen, da jeder Entwickler effektiv über eine eigene AKS-Umgebung verfügt. Entwickler können mit der Befehlszeilenschnittstelle Azure dev Spaces arbeiten oder Ihre Anwendung starten, um direkt von Visual Studio aus zu Azure dev Spaces. [Erfahren Sie mehr darüber, wie Azure dev Spaces funktioniert und konfiguriert ist.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions und Logic Apps (Server lose)

Das eshoponcontainers-Beispiel bietet Unterstützung für die Nachverfolgung von Online Marketingkampagnen. Eine Azure-Funktion wird zum Abrufen von Marketingkampagnen Details für eine bestimmte Kampagnen-ID verwendet. Anstatt zu diesem Zweck eine komplette ASP.net Core Anwendung zu erstellen, ist ein einzelner Azure-Funktions Endpunkt einfacher und ausreichend. Azure Functions haben ein viel einfacheres Build-und Bereitstellungs Modell als vollständige ASP.net Core Anwendungen, insbesondere, wenn es für die Verwendung in Kubernetes konfiguriert ist. Das Bereitstellen der Funktion erfolgt mithilfe von Azure Resource Manager (Arm)-Vorlagen und der Azure CLI. Dieser felddetailsmikrodienst ist nicht kundenseitig und hat nicht die gleichen Anforderungen wie der Online Shop, sodass er für Azure Functions geeignet ist. Die Funktion erfordert, dass einige Konfigurationen ordnungsgemäß funktionieren, wie z. b. Daten bankverbindungs Zeichenfolgen-Daten und URI-Basis Einstellungen Sie konfigurieren Azure Functions im Azure-Portal.

## <a name="references"></a>Verweise

- [eshoponcontainers: Erstellen eines Kubernetes-Clusters in AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eshoponcontainers: Azure dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[Zurück](map-eshoponcontainers-azure-services.md)
>[Weiter](centralized-configuration.md)
