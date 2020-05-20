---
title: Bereitstellen von eShopOnContainers in Azure
description: Bereitstellen der eshoponcontainers-Anwendung mithilfe von Azure Kubernetes Service, Helm und Devspaces.
ms.date: 05/13/2020
ms.openlocfilehash: 93a2848f095d7593e1e169f4a6c6c1818a76217d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614096"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Bereitstellen von eShopOnContainers in Azure

Die eshoponcontainers-Anwendung kann auf einer Vielzahl von Azure-Plattformen bereitgestellt werden. Die empfohlene Vorgehensweise besteht darin, die Anwendung in Azure Kubernetes Services (AKS) bereitzustellen. Helm, ein Kubernetes-Bereitstellungs Tool, ist zur Verringerung der Bereitstellungs Komplexität verfügbar. Optional können Entwickler Azure dev Spaces für Kubernetes implementieren, um Ihren Entwicklungsprozess zu optimieren.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Der erste Schritt besteht darin, einen AKS-Cluster zu erstellen, um den eShop in AKS zu hosten. Hierzu können Sie das Azure-Portal verwenden, das Sie durch die erforderlichen Schritte führt. Sie können auch einen Cluster aus dem Azure CLI erstellen, indem Sie die rollenbasierte Access Control (Role-Based, RBAC) und das Anwendungs Routing aktivieren. In der Dokumentation zu eshoponcontainers werden die Schritte zum Erstellen eines eigenen AKS-Clusters ausführlich erläutert. Nach der Erstellung können Sie über das Kubernetes-Dashboard auf den Cluster zugreifen und ihn verwalten.

Sie können jetzt die eShop-Anwendung im Cluster bereitstellen, indem Sie Helm und Tiller nutzen.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>Bereitstellen in Azure Kubernetes Dienst mithilfe von Helm

Helm ist ein Anwendungspaket-Manager-Tool, das direkt mit Kubernetes arbeitet. Es hilft Ihnen beim definieren, installieren und Upgraden von Kubernetes-Anwendungen. Obwohl einfache Apps für AKS mit benutzerdefinierten CLI-Skripts oder einfachen Bereitstellungs Dateien bereitgestellt werden können, können komplexe apps viele Kubernetes-Objekte enthalten und von Helm profitieren.

Mithilfe von Helm enthalten Anwendungen textbasierte Konfigurationsdateien, die als Helm-Diagramme bezeichnet werden, die die Anwendung und Konfiguration in Helm-Paketen deklarativ beschreiben. In Diagrammen werden standardmäßige YAML-formatierte Dateien verwendet, um einen zugehörigen Satz von Kubernetes-Ressourcen zu beschreiben. Sie werden neben dem Anwendungscode, den Sie beschreiben, versioniert. Helm-Diagramme reichen von einfachen bis zu komplexen Anforderungen, je nach den Anforderungen der von Ihnen beschriebenen Installation.

Helm besteht aus einem Befehlszeilen-Client Tool, das Helm-Diagramme nutzt und Befehle für eine Serverkomponente mit dem Namen Tiller gestartet. Tiller kommuniziert mit der Kubernetes-API, um die korrekte Bereitstellung Ihrer containerisierten Workloads sicherzustellen. Helm wird von der Cloud Native Computing Foundation verwaltet.

Die folgende YAML-Datei stellt eine Helm-Vorlage dar:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: {{ .Values.app.svc.marketing }}
  labels:
    app: {{ template "marketing-api.name" . }}
    chart: {{ template "marketing-api.chart" . }}
    release: {{ .Release.Name }}
    heritage: {{ .Release.Service }}
spec:
  type: {{ .Values.service.type }}
  ports:
    - port: {{ .Values.service.port }}
      targetPort: http
      protocol: TCP
      name: http
  selector:
    app: {{ template "marketing-api.name" . }}
    release: {{ .Release.Name }}
```

Beachten Sie, dass in der Vorlage ein dynamischer Satz von Schlüssel-Wert-Paaren beschrieben wird. Wenn die Vorlage aufgerufen wird, werden Werte, die in geschweiften Klammern eingeschlossen sind, aus anderen YAML-basierten Konfigurationsdateien abgerufen.

Sie finden die eshoponcontainers Helm-Diagramme im Ordner "/k8s/Helm". In Abbildung 2-6 wird dargestellt, wie die verschiedenen Komponenten der Anwendung in einer Ordnerstruktur angeordnet sind, die von Helm zum Definieren und Verwalten von bereit Stellungen verwendet wird.

![eshoponcontainers-Architektur ](./media/eshoponcontainers-helm-folder.png)
 **Abbildung 2-6**. Der Ordner "eshoponcontainers Helm".

Jede einzelne Komponente wird mithilfe eines- `helm install` Befehls installiert. der eShop umfasst das Skript "alle bereitstellen", mit dem die Komponenten durchlaufen und mithilfe der jeweiligen Helm-Diagramme installiert werden. Das Ergebnis ist ein wiederholbarer Prozess, der mit der Anwendung in der Quell Code Verwaltung versioniert ist, die jeder Person im Team mit einem einzeiligen Skript Befehl in einem AKS-Cluster bereitstellen kann.

> Beachten Sie, dass in Version 3 von Helm offiziell die Notwendigkeit der Tiller-Serverkomponente entfällt. Weitere Informationen zu dieser Erweiterung finden Sie [hier](https://medium.com/better-programming/why-is-tiller-missing-in-helm-3-2347c446714).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Native Cloud-Anwendungen können schnell und komplex wachsen, sodass beträchtliche Compute-Ressourcen ausgeführt werden müssen. In diesen Szenarien kann die gesamte Anwendung nicht auf einem Entwicklungs Computer (vor allem auf einem Laptop) gehostet werden. Azure dev Spaces ist darauf ausgelegt, dieses Problem mithilfe von AKS zu beheben. Es ermöglicht Entwicklern die Arbeit mit einer lokalen Version ihrer Dienste, während der Rest der Anwendung in einem AKS-Entwicklungs Cluster gehostet wird.

Entwickler verwenden eine ausgeführte (Entwicklungs-) Instanz in einem AKS-Cluster, der die gesamte containerisierte Anwendung enthält. Sie verwenden jedoch persönliche Plätze, die auf Ihrem Computer eingerichtet sind, um ihre Dienste lokal zu entwickeln. Wenn Sie fertig sind, testen Sie Sie von End-to-End im AKS-Cluster, ohne Abhängigkeiten zu replizieren. Azure dev Spaces führt Code vom lokalen Computer mit Diensten in AKS zusammen. Team Mitglieder können sehen, wie sich Ihre Änderungen in einer echten AKS-Umgebung Verhalten. Entwickler können Code schnell mithilfe von Visual Studio 2017 oder Visual Studio Code direkt in Kubernetes durchlaufen und Debuggen.

In Abbildung 2-7 können Sie sehen, dass Developer Susie eine aktualisierte Version des Bikes-mikroservice in Ihrem Entwicklungsbereich bereitgestellt hat. Sie kann Ihre Änderungen dann mithilfe einer benutzerdefinierten URL testen, beginnend mit dem Namen Ihres Platzes (Susie.s.dev.MyApp.EUS.azds.IO).

![eshoponcontainers-Architektur ](./media/azure-devspaces-one.png)
 **Abbildung 2-7**. Developer Susie stellt eine eigene Version des Bikes-mikroservice bereit und testet Sie.

Gleichzeitig passt der Entwickler John den "Reservierungen"-mikroservice an und muss seine Änderungen testen. Er stellt seine Änderungen in seinem eigenen Entwicklungsbereich bereit, ohne mit den Änderungen von Susie zu in Konflikt zu stehen, wie in Abbildung 2-8 dargestellt. John testet seine Änderungen dann mit seiner eigenen URL, der der Name seines leer Zeichens vorangestellt ist (John.s.dev.MyApp.EUS.azds.IO).

![eshoponcontainers-Architektur ](./media/azure-devspaces-two.png)
 **Abbildung 2-8**. Entwickler John stellt seine eigene Version des Reservierungs-und Test Dienstanbieter bereit und testet diese, ohne mit anderen Entwicklern in Konflikt zu geraten.

Mithilfe Azure dev Spaces können Teams direkt mit AKS arbeiten, während Sie Ihre Änderungen unabhängig voneinander ändern, bereitstellen und testen. Diese Vorgehensweise verringert den Bedarf an separaten dedizierten gehosteten Umgebungen, da jeder Entwickler effektiv über eine eigene AKS-Umgebung verfügt. Entwickler können mit der Befehlszeilenschnittstelle Azure dev Spaces arbeiten oder Ihre Anwendung starten, um direkt von Visual Studio aus zu Azure dev Spaces. [Erfahren Sie mehr darüber, wie Azure dev Spaces funktioniert und konfiguriert ist.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions und Logic Apps (Server lose)

Das eshoponcontainers-Beispiel bietet Unterstützung für die Nachverfolgung von Online Marketingkampagnen. Eine Azure-Funktion wird zum Nachverfolgen von Marketingkampagnen Details für eine bestimmte Kampagnen-ID verwendet. Anstatt einen vollständigen-mikrodienst zu erstellen, ist eine einzelne Azure-Funktion einfacher und ausreichend. Azure Functions über ein einfaches Build-und Bereitstellungs Modell verfügen, insbesondere, wenn es für die Verwendung in Kubernetes konfiguriert ist. Das Bereitstellen der Funktion erfolgt mithilfe von Azure Resource Manager (Arm)-Vorlagen und der Azure CLI. Dieser Kampagnen Dienst hat keinen Kunden Zugriff und Ruft einen einzelnen Vorgang auf, sodass er für Azure Functions hervorragend geeignet ist. Die-Funktion erfordert eine minimale Konfiguration, einschließlich Daten bankverbindungs Zeichenfolgen-Daten und URI-Basis Einstellungen für Images. Sie konfigurieren Azure Functions in der Azure-Portal.

>[!div class="step-by-step"]
>[Zurück](map-eshoponcontainers-azure-services.md)
>[Weiter](centralized-configuration.md)
