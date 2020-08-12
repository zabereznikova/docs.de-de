---
title: Erstellen von ASP.NET Core-Anwendungen, die als Linux-Container in AKS-/Kubernetes-Clustern bereitgestellt werden
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.date: 08/06/2020
ms.openlocfilehash: 4b04e5d56c73918c665ad6e2825205870aac9606
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916399"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Erstellen von als Linux-Container in einem AKS-/Kubernetes-Orchestrator bereitgestellten ASP.NET Core-Anwendungen

Azure Kubernetes Services (AKS) ist der verwaltete Kubernetes-Orchestrierungsdienst von Azure, der die Bereitstellung und Verwaltung von Containern vereinfacht.

Dies sind die wichtigsten Features von AKS:

- Eine auf Azure gehostete Steuerungsebene
- Automatisierte Upgrades
- Selbstreparatur
- Durch den Benutzer konfigurierbare Skalierung
- Einfacheres Benutzererlebnis sowohl für Entwickler als auch für Clusterbetreiber.

Die folgenden Beispiele untersuchen die Erstellung einer ASP.NET Core 3.1-Anwendung, die unter Linux ausgeführt und auf einem AKS-Cluster in Azure bereitgestellt wird, während die Entwicklung in Visual Studio 2019 erfolgt.

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a>Erstellen des ASP.NET Core 2019-Projekts mithilfe von Visual Studio 2019

ASP.NET Core ist eine universelle Entwicklungsplattform, die von Microsoft und der .NET-Community auf GitHub gepflegt wird. Sie ist plattformübergreifend, d.h. sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in Einbettungs- und IoT-Szenarios verwendet werden.

In diesem Beispiel werden einige einfache Projekte verwendet, die auf Visual Studio-Vorlagen basieren, sodass Sie zum Erstellen des Beispiels nicht viel zusätzliches Wissen benötigen. Sie müssen das Projekt nur mit einer Standardvorlage erstellen, die alle Elemente enthält, um ein kleines Projekt mit einer REST-API und einer Web-App mit Razor Pages unter Verwendung von ASP.NET Core 3.1-Technologie auszuführen.

![Fenster zum Hinzufügen eines neuen Projekts in Visual Studio mit ausgewählter ASP.NET Core-Webanwendung.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

**Abbildung 4–35**. Erstellen einer ASP.NET Core-Webanwendung in Visual Studio 2019.

Um das Beispielprojekt in Visual Studio zu erstellen, wählen Sie **Datei** > **Neu** > **Projekt** aus, wählen Sie den Projekttyp **Web** und dann die Vorlage **ASP.NET Core-Webanwendung** aus. Sie können auch nach der Vorlage suchen, wenn Sie sie benötigen.

Geben Sie dann den Namen und den Speicherort der Anwendung wie in der nächsten Abbildung gezeigt ein.

![Geben Sie den Projektnamen und den Speicherort ein.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

**Abbildung 4–36**. Geben Sie den Projektnamen und den Speicherort in Visual Studio 2019 ein.

Vergewissern Sie sich, dass Sie ASP.NET Core 3.1 als Framework ausgewählt haben. .NET Core 3.1 ist im neuesten Release von Visual Studio 2019 enthalten und wird automatisch für Sie installiert und konfiguriert, wenn Sie Visual Studio installieren.

![Visual Studio-Dialogfeld zum Auswählen des Typs einer ASP.NET Core-Webanwendung mit ausgewählter API-Option.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

**Abbildung 4–37**. Auswählen von ASP.NET Core 3.1 und des Projekttyps „Web-API“

Beachten Sie, dass Docker-Unterstützung jetzt nicht aktiviert ist, um zu zeigen, dass dies nach der Projekterstellung erfolgen kann.

Wenn Sie über eine frühere Version von .NET Core verfügen, können Sie Version 3.1 hier herunterladen und installieren: <https://dotnet.microsoft.com/download>.

Um zu zeigen, dass Sie das Projekt jederzeit „dockerisieren“ können, fügen Sie jetzt Docker-Unterstützung hinzu. Klicken Sie also mit der rechten Maustaste im Projektmappen-Explorer auf den Projektknoten, und wählen Sie im Kontextmenü **Hinzufügen** > **Docker-Unterstützung** aus.

![Kontextmenüoption zum Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt: Klicken Sie mit der rechten Maustaste (im Projekt) auf „Hinzufügen > Docker-Unterstützung“.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

**Abbildung 4–38**. Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt

Um das Hinzufügen von Docker-Unterstützung abzuschließen, können Sie Windows oder Linux auswählen. Wählen Sie in diesem Fall **Linux** aus.

![Optionsdialogfeld für die Auswahl des Betriebssystems für Dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

**Abbildung 4–39**. Auswählen von Linux-Containern.

Mit diesen einfachen Schritten haben Sie festgelegt, dass Ihre ASP.NET Core 3.1-Anwendung in einem Linux-Container ausgeführt wird.

In ähnlicher Weise können Sie auch ein sehr einfaches **WebApp**-Projekt (Abbildung 4-40) hinzufügen, um den Web-API-Endpunkt zu nutzen, auch wenn die Details hier nicht behandelt werden.

Danach fügen Sie Orchestratorunterstützung für Ihr **WebApi**-Projekt hinzu, wie im Folgenden in Abbildung 4-40 dargestellt.

![Hinzufügen von Orchestratorunterstützung zum WebApi-Projekt](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

**Abbildung 4–40**. Hinzufügen von Orchestratorunterstützung zum *WebApi*-Projekt.

Wenn Sie die Option `Docker Compose` auswählen, die für lokale Entwicklung gut geeignet ist, fügt Visual Studio das docker-compose-Projekt mit den docker-compose-Dateien hinzu, wie in Abbildung 4-41 gezeigt.

![Docker-compose wurde der Projektmappe hinzugefügt](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

**Abbildung 4–41**. Hinzufügen von Orchestratorunterstützung zum *WebApi*-Projekt.

Die ersten hinzugefügten Dateien ähneln den folgenden Dateien:

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

Damit Sie die App mit Docker Compose ausführen können, müssen Sie nur einige Anpassungen an `docker-compose.override.yml` vornehmen.

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

Jetzt können Sie Ihre Anwendung mit der Taste **F5** oder mit der Schaltfläche **Wiedergabe** oder der Tastenkombination **STRG+F5** ausführen und das docker-compose-Projekt auswählen, wie in Abbildung 4-42 gezeigt.

![Ausführen des docker-compose-Projekts mit Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

**Abbildung 4–42**. Hinzufügen von Orchestratorunterstützung zum *WebApi*-Projekt.

Wenn Sie die Anwendung „docker-vompose“ wie beschrieben ausführen, erhalten Sie folgendes Ergebnis:

1. Die gemäß der docker-compose-Datei erstellten Images und Container.
2. Öffnen des Browsers in der Adresse, die im Dialogfeld „Eigenschaften“ für das `docker-compose`-Projekt konfiguriert ist.
3. Öffnen des Fensters **Container** (in Visual Studio 2019, Version 16.4 oder höher).
4. Debuggerunterstützung für alle Projekte in der Projektmappe, wie in den folgenden Abbildungen gezeigt.

Geöffneter Browser:

![Browseransicht mit ausgeführter Web-App](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

**Abbildung 4–43**. Browserfenster, in dem eine Anwendung für mehrere Container ausgeführt wird.

Fenster „Container“:

![Visual Studio-Fenster „Container“](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

**Abbildung 4–44**. Visual Studio-Fenster „Container“

Über das Fenster **Container** können Sie ausgeführte Container, Umgebungsvariablen, Protokolle und Portzuordnungen anzeigen, verfügbare Images durchsuchen, das Dateisystem untersuchen, einen Debugger anfügen oder ein Terminalfenster in der Containerumgebung öffnen.

Wie Sie sehen können, ist die Integration von Visual Studio 2019 und Docker völlig auf die Produktivität des Entwicklers ausgelegt.

Natürlich können Sie die Images auch mit dem Befehl `docker images` auflisten. Sie sollten die Images `webapi` und `webapp` mit den `dev`-Tags sehen, die von der automatischen Bereitstellung Ihres Projekts mit Visual Studio 2019 erstellt wurden.

```console
docker images
```

![Konsolenausgabe des docker images-Befehls, eine Liste mit diesem Inhalt: Repository, Tag, Image-ID, Erstellungsdatum und Größe.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

**Abbildung 4–45**. Ansicht von Docker-Images

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a>Registrieren der Projektmappe in einer Azure Container Registry (ACR)

Sie können die Images in [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) hochladen, aber Sie können auch Docker Hub oder eine andere Registrierung verwenden, sodass die Images aus dieser Registrierung im AKS-Cluster bereitgestellt werden können.

### <a name="create-an-acr-instance"></a>Erstellen einer ACR-Instanz

Führen Sie den folgenden Befehl mit **az cli** aus:

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

### <a name="create-the-image-in-release-mode"></a>Erstellen des Images im Releasemodus

Sie erstellen jetzt das Image im **Releasemodus** (für die Produktion bereit), indem Sie zu **Release** wechseln, wie in Abbildung 4–46 dargestellt, und die Anwendung ausführen wie zuvor.

![Symbolleistenoption in Visual Studio zum Erstellen im Releasemodus.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

**Abbildung 4–46**. Auswählen des Releasemodus

Wenn Sie den Befehl `docker images` ausführen, sehen Sie, dass beide Images erstellt werden, ein Image für den `debug`- (**Entwicklung**) und ein weiteres für den `release`-Modus (**neuestes Image**).

### <a name="create-a-new-tag-for-the-image"></a>Erstellen eines neuen Tags für das Image

Jedes Containerimage muss mit dem `loginServer`-Namen der Registrierung gekennzeichnet werden. Dieses Tag wird beim Übertragen von Containerimages per Push in eine Imageregistrierung für das Routing verwendet.

Sie können den Namen des `loginServer` im Azure-Portal anzeigen, indem Sie die Informationen aus der Azure Container Registry übernehmen.

![Browseransicht des Namens in der Azure Container Registry rechts oben.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

**Abbildung 4–47**. Ansicht des Namens der Registry

Alternativ können Sie den folgenden Befehl ausführen:

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des Befehls oben.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

**Abbildung 4–48**. Abrufen des Namens der Registrierung mit **az cli**

In beiden Fällen erhalten Sie den Namen. In unserem Beispiel `exploredocker.azurecr.io`.

Jetzt können Sie das Image mit einem Tag kennzeichnen, indem Sie für das aktuellste Image (das Releaseimage) diesen Befehl ausführen:

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

Nach dem Ausführen des `docker tag`-Befehls können Sie die Images mit dem Befehl `docker images` auflisten, dann sollten Sie das Image mit dem neuen Tag sehen.

![Konsolenausgabe des docker images-Befehls.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

**Abbildung 4–49**. Ansicht von mit Tags gekennzeichneten Images

### <a name="push-the-image-into-the-azure-acr"></a>Pushen des Images in die Azure ACR

Melden Sie sich bei der Azure Container Registry an.

```console
az acr login --name exploredocker
```

Übertragen Sie das Image mit dem folgenden Befehl per Push in die Azure ACR:

```console
docker push <login-server-name>/<image-name>:v1
```

Dieser Befehl benötigt etwas Zeit zum Hochladen von Images, gibt Ihnen aber Feedback zum Verlauf. In der folgenden Abbildung sehen Sie, dass die Ausgabe eines Images abgeschlossen wurde und ein weiteres Image in Bearbeitung ist.

![Konsolenausgabe des docker push-Befehls.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

**Abbildung 4-50**. Konsolenausgabe des push-Befehls.

Um Ihre App mit mehreren Containern in Ihrem AKS-Cluster bereitzustellen, benötigen Sie einige `.yaml`-Manifestdateien, deren Eigenschaften größtenteils aus den `docker-compose.yml`- und `docker-compose.override.yml`-Dateien stammen.

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> Die vorherigen `.yml`-Dateien aktivieren nur die `HTTP`-Ports mithilfe des Parameters `ASPNETCORE_URLS`, um Probleme mit dem fehlenden Zertifikat in der Beispiel-App zu vermeiden.

> [!TIP]
> Informationen zum Erstellen des AKS-Clusters für dieses Beispiel finden Sie in Abschnitt [**Bereitstellen für Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) in diesem Handbuch.

Jetzt sind Sie fast für die Bereitstellung mit **kubectl** bereit. Zunächst müssen Sie jedoch die Anmeldeinformationen aus dem AKS-Cluster mit diesem Befehl abrufen:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Konsolenausgabe des Befehls oben: „explore-docker-aks“ als aktueller Kontext in „C:\Users\Miguel.kube\config“ gemergt](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

**Abbildung 4-51**. Abrufen von Anmeldeinformationen aus AKS in die kubectl-Umgebung.

Sie müssen dem AKS-Cluster außerdem das Pullen von Images aus ACR mithilfe dieses Befehls erlauben:

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

Die Ausführung des vorherigen Befehls kann einige Minuten dauern. Verwenden Sie dann den Befehl `kubectl apply`, um die Bereitstellungen zu starten, und verwenden Sie anschließend `kubectl get all` get list, um die Clusterobjekte aufzulisten.

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Konsolenausgabe der Befehle oben: Bereitstellungen angewendet. Dienste erstellt.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

**Abbildung 4-52**. Bereitstellung in Kubernetes

Sie müssen eine Weile warten, bis der Load Balancer die externe IP-Adresse abruft und mit `kubectl get services` prüft. Anschließend sollte die Anwendung unter dieser Adresse verfügbar sein, wie in der folgenden Abbildung gezeigt:

![Browseransicht der in AKS bereitgestellten Anwendung](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

**Abbildung 4.53**. Bereitstellung in Kubernetes

Wenn die Bereitstellung abgeschlossen ist, können Sie mit einem lokalen Proxy über einen SSH-Tunnel auf die [Kubernetes-Webbenutzeroberfläche](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) zugreifen.

Zunächst müssen Sie eine ClusterRoleBinding mit dem folgenden Befehl erstellen:

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

Verwenden Sie dann diesen Befehl, um den Proxy zu starten:

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

Ein Browserfenster sollte unter `http://127.0.0.1:8001` mit einer Ansicht geöffnet werden, die der folgenden ähnelt:

![Browseransicht des Kubernetes-Dashboards mit Bereitstellungen, Pods, Replikatsätzen und Diensten.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

**Abbildung 4-54**. Anzeigen von Kubernetes-Clusterinformationen

Nun verfügen Sie über Ihre ASP.NET Core Anwendung, die in Linux-Containern ausgeführt und in einem AKS-Cluster in Azure bereitgestellt wird.

> [!NOTE]
> Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.

> [!div class="step-by-step"]
> [Zurück](set-up-windows-containers-with-powershell.md)
> [Weiter](../docker-devops-workflow/index.md)
