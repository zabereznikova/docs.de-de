---
title: Erstellen von ASP.NET Core 2.1-Anwendungen wie Linux-Container in AKS/Kubernetes-Cluster bereitgestellt
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: c6d778d345466b1b852d06bc01ce40ccfdebf964
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052758"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Erstellen von ASP.NET Core 2.1-Anwendungen, die als Linux-Container bereitgestellt werden, in einem AKS/Kubernetes-orchestrator

Azure Kubernetes Service (AKS) ist von Azure verwalteten Kubernetes-Orchestrierungen-Dienste, die containerbereitstellung und Verwaltung zu vereinfachen.

AKS-Hauptfunktionen sind:

- Ein Azure-gehostete Steuerungsebene
- Automatische Updates
- Selbstkorrektur
- Benutzer konfigurierbaren Skalierung
- Ein einfacher Benutzererlebnis für Entwickler und clusterbetreiber.

Die folgenden Beispiele durchsuchen, die Erstellung einer ASP.NET Core 2.1-Anwendung, die unter Linux ausgeführt wird und auf einen AKS-Cluster in Azure bereitgestellt werden, während der Entwicklung erfolgt mithilfe von Visual Studio 2017.

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a>Erstellen das ASP.NET Core 2.1-Projekt mit Visual Studio 2017

ASP.NET Core ist eine allgemeine Entwicklungsplattform von Microsoft und der .NET-Community auf GitHub verwaltet wird. Dabei handelt es sich plattformübergreifende Unterstützung von Windows, MacOS und Linux, kann in Geräte-, Cloud- und eingebetteten/IoT-Szenarien verwendet werden.

Dieses Beispiel verwendet ein einfaches Projekt, das zusätzliche Kenntnisse zum Erstellen der Beispieldatenbank erforderlich, in einer Visual Studio Web-API-Vorlage basiert. Sie müssen nur zum Erstellen des Projekts mithilfe einer standard-Vorlage, die alle zum Ausführen von eines kleinen Projekts mit einer REST-API, die mit ASP.NET Core 2.1-Technologie-Elemente enthält.

![Fügen Sie Fenster "Neues Projekt hinzu" in Visual Studio, die Auswahl von ASP.NET Core-Webanwendung.](media/create-aspnet-core-application.png)

**Abbildung 4 bis 36**. Erstellen von ASP.NET Core-Anwendung

Wählen Sie zum Erstellen des Beispielprojekts in Visual Studio **Datei** > **neu** > **Projekt**, wählen die **Web**Projekttypen im linken Bereich, gefolgt von **ASP.NET Core-Webanwendung**.

Visual Studio enthält Vorlagen für Webprojekte. Wählen Sie in unserem Beispiel **API** zum Erstellen einer ASP.NET Web-API-Anwendung.

Stellen Sie sicher, dass Sie ASP.NET Core 2.1 als Framework ausgewählt haben. .NET Core 2.1 wird ist in der letzten Version von Visual Studio 2017 enthalten und automatisch installiert und konfiguriert Sie bei der Installation von Visual Studio 2017.

![Visual Studio-Dialogfeld zum Auswählen von einer ASP.NET Core-Webanwendung mit API-Option ausgewählt ist.](media/create-web-api-application.png)

**Abbildung 4-37**. Auswählen von ASP.NET CORE 2.1 und Web-API-Projekttyp

Wenn Sie eine frühere Version von .NET Core verfügen, können Sie diese herunterladen und installieren Sie Version 2.1 von <https://www.microsoft.com/net/download/core#/sdk>.

Sie können Docker-Unterstützung hinzufügen, wenn Sie das Projekt zu erstellen oder danach also Sie können "Verpacken" Sie Ihr Projekt zu einem beliebigen Zeitpunkt. Klicken Sie zum Hinzufügen der Docker-Unterstützung nach der projekterstellung mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und wählen Sie **hinzufügen** > **Docker-Unterstützung** im Kontextmenü.

![Die Kontextmenüoption Docker-Unterstützung zu einem vorhandenen Projekt hinzufügen: Klicken Sie mit der rechten Maustaste (auf das Projekt) > Hinzufügen > Docker-Unterstützung.](media/add-docker-support-to-project.png)

**Abbildung 4-38**. Docker-Unterstützung zu vorhandenen Projekt hinzufügen

Zum Hinzufügen von Docker-Unterstützung abgeschlossen haben, können Sie Windows oder Linux. Wählen Sie in diesem Fall **Linux**, da AKS Windows-Container (als Ende 2018) nicht unterstützt.

![Dialogfeld Zielbetriebssystem für die dockerfile-Datei auswählen.](media/select-linux-docker-support.png)

**Abbildung 4-39**. Auswählen von Linux-Container.

Mit diesen einfachen Schritten haben Sie Ihre ASP.NET Core 2.1-Anwendung, die auf einem Linux-Container ausgeführt wird.

Wie Sie sehen können, ist die Integration zwischen Visual Studio 2017 und Docker auf die die Produktivität der Entwickler vollständig ausgerichtet.

Jetzt können Sie Ihre Anwendung mit Ausführen der **F5** Taste oder durch die Verwendung der **spielen** Schaltfläche.

Nach dem Ausführen des Projekts, können Sie Auflisten der Images mithilfe der `docker images` Befehl. Daraufhin sollte die `mssampleapplication` Images, die von der automatischen Bereitstellung unseres Projekts mit Visual Studio 2017 erstellt.

```console
docker images
```

![Konsolenausgabe aus dem Befehl "Docker Images" zeigt eine Liste mit: Repository, Tag, Bild-ID, Created (Datum) und Größe.](media/docker-images-command.png)

**Abbildung 4 – 40**. Anzeigen der Docker-images

## <a name="register-the-solution-in-the-azure-container-registry"></a>Registrieren Sie die Lösung in Azure Container Registry

Hochladen des Images an eine beliebige Docker-Registrierung, wie z. B. [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) oder Docker-Hub, damit die Bilder in die Registrierung mit dem AKS-Cluster bereitgestellt werden können. In diesem Fall haben wir das Image in Azure Container Registry hochgeladen.

### <a name="create-the-image-in-release-mode"></a>Erstellen Sie das Image im Releasemodus

Wir erstellen nun das Image im **Version** Modus (bereit für die Produktion) durch Ändern von in **Version**, wie in Abbildung 4: 41 und Ausführen der Anwendung, wie vorher gezeigt.

![Symbolleistenoption in Visual Studio im Releasemodus zu erstellen.](media/select-release-mode.png)

**Abbildung 4: 41**. Auswählen der Releasemodus

Bei Ausführung der `docker image` Befehl sehen Sie beide Bilder erstellt, eine für `debug` und die andere für `release` Modus.

### <a name="create-a-new-tag-for-the-image"></a>Erstellen eines neuen Transponders für das Image

Jedes containerimage muss mit gekennzeichnet werden die `loginServer` -Namen der Registrierung. Dieses Tag wird für die Übertragung von containerimages in eine imageregistrierung routing verwendet.

Sie können anzeigen, die `loginServer` Name im Azure-Portal, nehmen die Informationen aus der Azure-Containerregistrierung

![Browseransicht der den Namen der Azure-containerregistrierung, auf der rechten oberen Ecke.](media/loginServer-name.png)

**Abbildung 4-42**. Überblick über den Namen der Registrierung

Oder durch den folgenden Befehl ausführen:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des obigen Befehls.](media/az-cli-loginServer-name.png)

**Abbildung 4-43**. Rufen Sie den Namen der Registrierung mithilfe von PowerShell

In beiden Fällen müssen Sie den Namen abrufen. In unserem Beispiel `mssampleacr.azurecr.io`.

Jetzt können Sie das Image, zu kennzeichnen dauert das neueste Image (dem Release-Image), mit dem Befehl:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Nach dem Ausführen der `docker tag` Befehl, Listen Sie die Images mit der `docker images` -Befehl, und Sie sollte das Image mit dem neuen Tag angezeigt.

![Konsolenausgabe aus dem Befehl "Docker Images".](media/tagged-docker-images-list.png)

**Abbildung 4: 44**. Anzeigen der markierten images

### <a name="push-the-image-into-the-azure-acr"></a>Pushen Sie das Image in Azure ACR

Pushen Sie das Image in Azure ACR, mit dem folgenden Befehl ein:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Mit diesem Befehl dauert eine Weile Hochladens von Bildern, jedoch erhalten Sie Feedback im Prozess.

![Konsolenausgabe aus dem Docker-Push-Befehl: Zeigt eine zeichenbasierte Statusleiste für jede Ebene.](media/uploading-image-to-acr.png)

**Abbildung 4-45**. Hochladen des Images in ACR

Unten das Ergebnis sehen Sie, dass Sie nach Abschluss des Prozesses erhalten sollten:

![Konsolenausgabe aus dem Docker-Push-Befehl, und fertig sind, zeigt alle Ebenen oder Knoten.](media/uploading-docker-images-complete.png)

**Abbildung 4: 46**. Anzeigen von Knoten

Der nächste Schritt ist, Ihren Container in Ihrem ACS-Kubernetes-Cluster bereitzustellen. Dafür benötigen Sie eine Datei (**.yml dateibereitstellung**), die Folgendes enthält:

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
        - mane: mssample-services-app
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
> Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

Jetzt Sie fast bereit, das Bereitstellen über **"kubectl"**, aber Sie müssen zuerst die Anmeldeinformationen für den AKS-Cluster mit dem folgenden Befehl abrufen:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Konsolenausgabe des obigen Befehls: Zusammengeführte "MSSampleK8Cluster als den aktuellen Kontext im /root/.kube/config](media/getting-aks-credentials.png)

**Abbildung 4: 47**. Abrufen von Anmeldeinformationen

Verwenden Sie dann die `kubectl create` Befehl aus, um die Bereitstellung zu starten.

```console
kubectl create -f mssample-deploy.yml
```

![Konsolenausgabe des obigen Befehls: Bereitstellung "Mssamplesbook" erstellt. Dienst "Mssample-Kub-app" erstellt.](media/kubectl-create-command.png)

**Abbildung 4 – 48**. Bereitstellen in Kubernetes

Wenn die Bereitstellung abgeschlossen ist, können Sie die Kubernetes-Konsole mit einem lokalen Proxy zugreifen, die Sie mit diesem Befehl chronologisch zugreifen können:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

Und den Zugriff auf die Url `http://127.0.0.1:8001`.

![Der Browseransicht der Kubernetes-Dashboard angezeigt werden, Bereitstellungen, Pods, Dienste und -Replikatsätze.](media/kubernetes-cluster-information.png)

**Abbildung 4-49**. Anzeigen von Informationen für Kubernetes-cluster

Sie haben jetzt Ihre Anwendung in Azure mit einem Linux-Container und einem AKS-Kubernetes-Cluster bereitgestellt. Sie können Ihre app navigieren, um die öffentliche IP-Adresse des Diensts, die Sie im Azure-Portal abrufen können zugreifen.

> [!NOTE]
> Sie erfahren, wie zum Erstellen des AKS-Clusters für dieses Beispiel im Abschnitt [ **bereitstellen auf Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) zu diesem Handbuch.

>[!div class="step-by-step"]
>[Zurück](set-up-windows-containers-with-powershell.md)
>[Weiter](../docker-devops-workflow/index.md)
