---
title: Erstellen von ASP.NET Core 2.2-Anwendungen, die als Linux-Container in AKS-/Kubernetes-Clustern bereitgestellt werden
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.date: 02/25/2019
ms.openlocfilehash: ab64a0423ceceb8285c159af276d6d97e12379d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70848758"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Erstellen von ASP.NET Core 2.2-Anwendungen, die als Linux-Container in einem AKS-/Kubernetes-Orchestrator bereitgestellt werden

Azure Kubernetes Services (AKS) ist der verwaltete Kubernetes-Orchestrierungsdienst von Azure, der die Bereitstellung und Verwaltung von Containern vereinfacht.

Dies sind die wichtigsten Features von AKS:

- Eine auf Azure gehostete Steuerungsebene
- Automatisierte Upgrades
- Selbstreparatur
- Vom Benutzer zu konfigurierende Skalierung
- Eine einfacheres Benutzererlebnis sowohl für Entwickler als auch für Clusterbetreiber.

Die folgenden Beispiele untersuchen die Erstellung einer ASP.NET Core 2.2-Anwendung, die unter Linux ausgeführt und auf einem AKS-Cluster in Azure bereitgestellt wird, während die Entwicklung in Visual Studio 2017 erfolgt.

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a>Erstellen des ASP.NET Core 2.2-Projekts mithilfe von Visual Studio 2017

ASP.NET Core ist eine universelle Entwicklungsplattform, die von Microsoft und der .NET-Community auf GitHub gepflegt wird. Sie ist plattformübergreifend, d.h. sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in Einbettungs- und IoT-Szenarios verwendet werden.

Dieses Beispiel verwendet ein einfaches Projekt, das auf einer Visual Studio Web-API-Vorlage basiert, sodass Sie zum Erstellen des Beispiels keine weiteren Kenntnisse benötigen. Sie müssen lediglich das Projekt mithilfe einer Standardvorlage erstellen, die alle Elemente zum Ausführen eines kleinen Projekts mit einer REST-API beinhaltet und ASP.NET Core 2.2-Technologie verwendet.

![Fenster zum Hinzufügen eines neuen Projekts in Visual Studio mit ausgewählter ASP.NET Core-Webanwendung.](media/create-aspnet-core-application.png)

**Abbildung 4–36**. Erstellen einer ASP.NET Core-Anwendung

Wählen Sie zum Erstellen des Beispielprojekts in Visual Studio **Datei** > **Neu** > **Projekt** aus, und wählen Sie dann im linken Bereich die **Web**-Projekttypen aus, gefolgt von **ASP.NET Core-Webanwendung**.

Visual Studio listet Vorlagen für Webprojekte auf. Wählen Sie für unser Beispiel **API** aus, um eine ASP.NET Web-API-Anwendung zu erstellen.

Vergewissern Sie sich, dass Sie ASP.NET Core 2.2 als Framework ausgewählt haben. .NET Core 2.2 ist in der letzten Version von Visual Studio 2017 enthalten und wird automatisch für Sie installiert und konfiguriert, wenn Sie Visual Studio 2017 installieren.

![Visual Studio-Dialogfeld zum Auswählen des Typs einer ASP.NET Core-Webanwendung mit ausgewählter API-Option.](media/create-web-api-application.png)

**Abbildung 4–37**. Auswählen des Projekttyps ASP.NET CORE 2.2 und Web-API

Wenn Sie über eine frühere Version von .NET Core verfügen, können Sie die Version 2.2 hier herunterladen und installieren: <https://dotnet.microsoft.com/download>.

Sie können Docker-Unterstützung beim Erstellen des Projekts oder später hinzufügen – Sie können Ihr Projekt also jederzeit „Dockern“. Um Docker-Unterstützung nach der Projekterstellung hinzuzufügen, klicken Sie mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und wählen Sie im Kontextmenü **Hinzufügen** > **Docker-Unterstützung** aus.

![Kontextmenüoption zum Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt: Mit der rechten Maustaste (auf dem Projekt) klicken > Hinzufügen > Docker-Unterstützung.](media/add-docker-support-to-project.png)

**Abbildung 4–38**. Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt

Um das Hinzufügen von Docker-Unterstützung abzuschließen, können Sie Windows oder Linux auswählen. Wählen Sie in diesem Fall **Linux** aus, da AKS keine Windows-Container unterstützt (Stand Ende 2018).

![Optionsdialogfeld für die Auswahl des Betriebssystems für Dockerfile.](media/select-linux-docker-support.png)

**Abbildung 4–39**. Auswählen von Linux-Containern.

Mit diesen einfachen Schritten haben Sie festgelegt, dass Ihre ASP.NET Core 2.2-Anwendung in einem Linux-Container ausgeführt wird.

Wie Sie sehen können, ist die Integration von Visual Studio 2017 und Docker völlig auf die Produktivität des Entwicklers ausgelegt.

Jetzt können Sie Ihre Anwendung mit der Taste **F5** oder der Schaltfläche **Wiedergabe** ausführen.

Nach dem Ausführen des Projekts können Sie die Images mithilfe des Befehls `docker images` auflisten. Sie sollten das Image `mssampleapplication` sehen, das von der automatischen Bereitstellung Ihres Projekts mit Visual Studio 2017 erstellt wurde.

```console
docker images
```

![Konsolenausgabe des docker images-Befehls, eine Liste mit diesem Inhalt: Repository, Tag, Image-ID, Erstellungsdatum und Größe.](media/docker-images-command.png)

**Abbildung 4–40**. Ansicht von Docker-Images

## <a name="register-the-solution-in-the-azure-container-registry"></a>Registrieren der Projektmappe in der Azure Container Registry

Laden Sie das Image in eine beliebige Docker-Registrierung hoch, wie etwa [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) oder Docker Hub, damit die Images aus dieser Registrierung auf dem AKS-Cluster bereitgestellt werden können. In diesem Fall laden wir das Image in die Azure Container Registry hoch.

### <a name="create-the-image-in-release-mode"></a>Erstellen des Images im Releasemodus

Wir erstellen jetzt das Image im **Releasemodus** (für die Produktion bereit), indem wir zu **Release** wechseln, wie in Abbildung 4–41 dargestellt, und die Anwendung ausführen wie zuvor.

![Symbolleistenoption in Visual Studio zum Erstellen im Releasemodus.](media/select-release-mode.png)

**Abbildung 4–41**. Auswählen des Releasemodus

Wenn Sie den Befehl `docker image` ausführen, sehen Sie, dass beide Images erstellt werden, eins für den `debug`- und das andere für den `release`-Modus.

### <a name="create-a-new-tag-for-the-image"></a>Erstellen eines neuen Tags für das Image

Jedes Containerimage muss mit dem `loginServer`-Namen der Registrierung gekennzeichnet werden. Dieses Tag wird beim Übertragen von Containerimages per Push in eine Imageregistrierung für das Routing verwendet.

Sie können den Namen des `loginServer` im Azure-Portal anzeigen, indem Sie die Informationen aus der Azure Container Registry übernehmen.

![Browseransicht des Namens in der Azure Container Registry rechts oben.](media/loginServer-name.png)

**Abbildung 4–42**. Ansicht des Namens der Registry

Alternativ können Sie den folgenden Befehl ausführen:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des Befehls oben.](media/az-cli-loginServer-name.png)

**Abbildung 4–43**. Rufen Sie den Namen der Registrierung mithilfe von PowerShell ab

In beiden Fällen erhalten Sie den Namen. In unserem Beispiel `mssampleacr.azurecr.io`.

Jetzt können Sie das Image mit einem Tag kennzeichnen, indem Sie für das aktuellste Image (das Releaseimage) diesen Befehl ausführen:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Nach dem Ausführen des `docker tag`-Befehls können Sie die Images mit dem Befehl `docker images` auflisten, dann sollten Sie das Image mit dem neuen Tag sehen.

![Konsolenausgabe des docker images-Befehls.](media/tagged-docker-images-list.png)

**Abbildung 4–44**. Ansicht von mit Tags gekennzeichneten Images

### <a name="push-the-image-into-the-azure-acr"></a>Pushen des Images in die Azure ACR

Melden Sie sich bei der Azure Container Registry an.

```console
az acr login --name mssampleacr
```

Übertragen Sie das Image mit dem folgenden Befehl per Push in die Azure ACR:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Dieser Befehl benötigt etwas Zeit zum Hochladen von Images, gibt Ihnen aber Feedback zum Verlauf.

![Konsolenausgabe des docker push-Befehls: Zeigt einen zeichenbasierten Verlaufsbalken für jede Schicht an.](media/uploading-image-to-acr.png)

**Abbildung 4–45**. Hochladen des Images in die ACR

Unten sehen Sie das Ergebnis, das Sie nach Abschluss des Prozesses erhalten sollten:

![Konsolenausgabe des docker push-Befehls nach dem Abschluss mit Anzeige aller Schichten oder Knoten.](media/uploading-docker-images-complete.png)

**Abbildung 4–46**. Ansicht von Knoten

Der nächste Schritt besteht im Bereitstellen Ihres Containers in Ihrem AKS Kubernetes-Cluster. Dazu benötigen Sie eine Datei (**YML-Bereitstellungsdatei**), die folgende Informationen enthält:

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - name: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.

Jetzt sind Sie fast zur Bereitstellung mit **Kubectl** bereit, zunächst müssen Sie jedoch die Anmeldeinformationen für den AKS-Cluster mit diesem Befehl abrufen:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Konsolenausgabe des Befehls oben: Merge von „MSSampleK8Cluster“ als aktueller Kontext in „/root/.kube/config“](media/getting-aks-credentials.png)

**Abbildung 4–47**. Abrufen von Anmeldeinformationen

Verwenden Sie anschließend den `kubectl create`-Befehl, um die Bereitstellung zu starten.

```console
kubectl create -f mssample-deploy.yml
```

![Konsolenausgabe des Befehls oben: „deployment ‚mssamplesbook‘ created. service ‚mssample-kub-app‘ created“.](media/kubectl-create-command.png)

**Abbildung 4–48**. Bereitstellen in Kubernetes

Wenn die Bereitstellung abgeschlossen ist, können Sie mit einem lokalen Proxy, auf den Sie zeitweilig mit diesem Befehl zugreifen können, auf die Kubernetes-Konsole zugreifen:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

Und greifen Sie auf die URL `http://127.0.0.1:8001` zu.

![Browseransicht des Kubernetes-Dashboards mit Bereitstellungen, Pods, Replikatsätzen und Diensten.](media/kubernetes-cluster-information.png)

**Abbildung 4–49**. Anzeigen von Kubernetes-Clusterinformationen

Sie haben jetzt Ihre Anwendung auf Azure bereitgestellt und dazu einen Linux-Container und einen AKS Kubernetes-Cluster verwendet. Sie können auf Ihre App zugreifen, indem Sie zur öffentlichen IP-Adresse Ihres Diensts navigieren, die Sie im Azure-Portal abrufen können.

> [!NOTE]
> Informationen zum Erstellen des AKS-Clusters für dieses Beispiel finden Sie in Abschnitt [**Bereitstellen für Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) in diesem Handbuch.

>[!div class="step-by-step"]
>[Zurück](set-up-windows-containers-with-powershell.md)
>[Weiter](../docker-devops-workflow/index.md)
