---
title: Erstellen von ASP.NET Core 2.1-Anwendungen wie Linux-Container in AKS/Kubernetes-Cluster bereitgestellt
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: c6d778d345466b1b852d06bc01ce40ccfdebf964
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676654"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="d0758-103">Erstellen von ASP.NET Core 2.1-Anwendungen, die als Linux-Container bereitgestellt werden, in einem AKS/Kubernetes-orchestrator</span><span class="sxs-lookup"><span data-stu-id="d0758-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="d0758-104">Azure Kubernetes Service (AKS) ist von Azure verwalteten Kubernetes-Orchestrierungen-Dienste, die containerbereitstellung und Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="d0758-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="d0758-105">AKS-Hauptfunktionen sind:</span><span class="sxs-lookup"><span data-stu-id="d0758-105">AKS main features are:</span></span>

- <span data-ttu-id="d0758-106">Ein Azure-gehostete Steuerungsebene</span><span class="sxs-lookup"><span data-stu-id="d0758-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="d0758-107">Automatische Updates</span><span class="sxs-lookup"><span data-stu-id="d0758-107">Automated upgrades</span></span>
- <span data-ttu-id="d0758-108">Selbstkorrektur</span><span class="sxs-lookup"><span data-stu-id="d0758-108">Self-healing</span></span>
- <span data-ttu-id="d0758-109">Benutzer konfigurierbaren Skalierung</span><span class="sxs-lookup"><span data-stu-id="d0758-109">User configurable scaling</span></span>
- <span data-ttu-id="d0758-110">Ein einfacher Benutzererlebnis für Entwickler und clusterbetreiber.</span><span class="sxs-lookup"><span data-stu-id="d0758-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="d0758-111">Die folgenden Beispiele durchsuchen, die Erstellung einer ASP.NET Core 2.1-Anwendung, die unter Linux ausgeführt wird und auf einen AKS-Cluster in Azure bereitgestellt werden, während der Entwicklung erfolgt mithilfe von Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d0758-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="d0758-112">Erstellen das ASP.NET Core 2.1-Projekt mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d0758-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="d0758-113">ASP.NET Core ist eine allgemeine Entwicklungsplattform von Microsoft und der .NET-Community auf GitHub verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="d0758-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="d0758-114">Dabei handelt es sich plattformübergreifende Unterstützung von Windows, MacOS und Linux, kann in Geräte-, Cloud- und eingebetteten/IoT-Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0758-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="d0758-115">Dieses Beispiel verwendet ein einfaches Projekt, das zusätzliche Kenntnisse zum Erstellen der Beispieldatenbank erforderlich, in einer Visual Studio Web-API-Vorlage basiert.</span><span class="sxs-lookup"><span data-stu-id="d0758-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="d0758-116">Sie müssen nur zum Erstellen des Projekts mithilfe einer standard-Vorlage, die alle zum Ausführen von eines kleinen Projekts mit einer REST-API, die mit ASP.NET Core 2.1-Technologie-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="d0758-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![Fügen Sie Fenster "Neues Projekt hinzu" in Visual Studio, die Auswahl von ASP.NET Core-Webanwendung.](media/create-aspnet-core-application.png)

<span data-ttu-id="d0758-118">**Abbildung 4 bis 36**.</span><span class="sxs-lookup"><span data-stu-id="d0758-118">**Figure 4-36**.</span></span> <span data-ttu-id="d0758-119">Erstellen von ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d0758-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="d0758-120">Wählen Sie zum Erstellen des Beispielprojekts in Visual Studio **Datei** > **neu** > **Projekt**, wählen die **Web**Projekttypen im linken Bereich, gefolgt von **ASP.NET Core-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="d0758-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="d0758-121">Visual Studio enthält Vorlagen für Webprojekte.</span><span class="sxs-lookup"><span data-stu-id="d0758-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="d0758-122">Wählen Sie in unserem Beispiel **API** zum Erstellen einer ASP.NET Web-API-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d0758-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="d0758-123">Stellen Sie sicher, dass Sie ASP.NET Core 2.1 als Framework ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="d0758-123">Verify that you've selected ASP.NET Core 2.1 as the framework.</span></span> <span data-ttu-id="d0758-124">.NET Core 2.1 wird ist in der letzten Version von Visual Studio 2017 enthalten und automatisch installiert und konfiguriert Sie bei der Installation von Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d0758-124">.NET Core 2.1 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Visual Studio-Dialogfeld zum Auswählen von einer ASP.NET Core-Webanwendung mit API-Option ausgewählt ist.](media/create-web-api-application.png)

<span data-ttu-id="d0758-126">**Abbildung 4-37**.</span><span class="sxs-lookup"><span data-stu-id="d0758-126">**Figure 4-37**.</span></span> <span data-ttu-id="d0758-127">Auswählen von ASP.NET CORE 2.1 und Web-API-Projekttyp</span><span class="sxs-lookup"><span data-stu-id="d0758-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="d0758-128">Wenn Sie eine frühere Version von .NET Core verfügen, können Sie diese herunterladen und installieren Sie Version 2.1 von <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="d0758-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="d0758-129">Sie können Docker-Unterstützung hinzufügen, wenn Sie das Projekt zu erstellen oder danach also Sie können "Verpacken" Sie Ihr Projekt zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="d0758-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="d0758-130">Klicken Sie zum Hinzufügen der Docker-Unterstützung nach der projekterstellung mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und wählen Sie **hinzufügen** > **Docker-Unterstützung** im Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="d0758-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Die Kontextmenüoption Docker-Unterstützung zu einem vorhandenen Projekt hinzufügen: Klicken Sie mit der rechten Maustaste (auf das Projekt) > Hinzufügen > Docker-Unterstützung.](media/add-docker-support-to-project.png)

<span data-ttu-id="d0758-132">**Abbildung 4-38**.</span><span class="sxs-lookup"><span data-stu-id="d0758-132">**Figure 4-38**.</span></span> <span data-ttu-id="d0758-133">Docker-Unterstützung zu vorhandenen Projekt hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d0758-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="d0758-134">Zum Hinzufügen von Docker-Unterstützung abgeschlossen haben, können Sie Windows oder Linux.</span><span class="sxs-lookup"><span data-stu-id="d0758-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="d0758-135">Wählen Sie in diesem Fall **Linux**, da AKS Windows-Container (als Ende 2018) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d0758-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Dialogfeld Zielbetriebssystem für die dockerfile-Datei auswählen.](media/select-linux-docker-support.png)

<span data-ttu-id="d0758-137">**Abbildung 4-39**.</span><span class="sxs-lookup"><span data-stu-id="d0758-137">**Figure 4-39**.</span></span> <span data-ttu-id="d0758-138">Auswählen von Linux-Container.</span><span class="sxs-lookup"><span data-stu-id="d0758-138">Selecting Linux containers.</span></span>

<span data-ttu-id="d0758-139">Mit diesen einfachen Schritten haben Sie Ihre ASP.NET Core 2.1-Anwendung, die auf einem Linux-Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d0758-139">With these simple steps, you have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="d0758-140">Wie Sie sehen können, ist die Integration zwischen Visual Studio 2017 und Docker auf die die Produktivität der Entwickler vollständig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="d0758-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="d0758-141">Jetzt können Sie Ihre Anwendung mit Ausführen der **F5** Taste oder durch die Verwendung der **spielen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d0758-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="d0758-142">Nach dem Ausführen des Projekts, können Sie Auflisten der Images mithilfe der `docker images` Befehl.</span><span class="sxs-lookup"><span data-stu-id="d0758-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="d0758-143">Daraufhin sollte die `mssampleapplication` Images, die von der automatischen Bereitstellung unseres Projekts mit Visual Studio 2017 erstellt.</span><span class="sxs-lookup"><span data-stu-id="d0758-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Konsolenausgabe aus dem Befehl "Docker Images" zeigt eine Liste mit: Repository, Tag, Bild-ID, Created (Datum) und Größe.](media/docker-images-command.png)

<span data-ttu-id="d0758-145">**Abbildung 4 – 40**.</span><span class="sxs-lookup"><span data-stu-id="d0758-145">**Figure 4-40**.</span></span> <span data-ttu-id="d0758-146">Anzeigen der Docker-images</span><span class="sxs-lookup"><span data-stu-id="d0758-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="d0758-147">Registrieren Sie die Lösung in Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="d0758-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="d0758-148">Hochladen des Images an eine beliebige Docker-Registrierung, wie z. B. [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) oder Docker-Hub, damit die Bilder in die Registrierung mit dem AKS-Cluster bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="d0758-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="d0758-149">In diesem Fall haben wir das Image in Azure Container Registry hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="d0758-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="d0758-150">Erstellen Sie das Image im Releasemodus</span><span class="sxs-lookup"><span data-stu-id="d0758-150">Create the image in Release mode</span></span>

<span data-ttu-id="d0758-151">Wir erstellen nun das Image im **Version** Modus (bereit für die Produktion) durch Ändern von in **Version**, wie in Abbildung 4: 41 und Ausführen der Anwendung, wie vorher gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0758-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Symbolleistenoption in Visual Studio im Releasemodus zu erstellen.](media/select-release-mode.png)

<span data-ttu-id="d0758-153">**Abbildung 4: 41**.</span><span class="sxs-lookup"><span data-stu-id="d0758-153">**Figure 4-41**.</span></span> <span data-ttu-id="d0758-154">Auswählen der Releasemodus</span><span class="sxs-lookup"><span data-stu-id="d0758-154">Selecting Release Mode</span></span>

<span data-ttu-id="d0758-155">Bei Ausführung der `docker image` Befehl sehen Sie beide Bilder erstellt, eine für `debug` und die andere für `release` Modus.</span><span class="sxs-lookup"><span data-stu-id="d0758-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="d0758-156">Erstellen eines neuen Transponders für das Image</span><span class="sxs-lookup"><span data-stu-id="d0758-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="d0758-157">Jedes containerimage muss mit gekennzeichnet werden die `loginServer` -Namen der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="d0758-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="d0758-158">Dieses Tag wird für die Übertragung von containerimages in eine imageregistrierung routing verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0758-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="d0758-159">Sie können anzeigen, die `loginServer` Name im Azure-Portal, nehmen die Informationen aus der Azure-Containerregistrierung</span><span class="sxs-lookup"><span data-stu-id="d0758-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Browseransicht der den Namen der Azure-containerregistrierung, auf der rechten oberen Ecke.](media/loginServer-name.png)

<span data-ttu-id="d0758-161">**Abbildung 4-42**.</span><span class="sxs-lookup"><span data-stu-id="d0758-161">**Figure 4-42**.</span></span> <span data-ttu-id="d0758-162">Überblick über den Namen der Registrierung</span><span class="sxs-lookup"><span data-stu-id="d0758-162">View of the name of the Registry</span></span>

<span data-ttu-id="d0758-163">Oder durch den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="d0758-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des obigen Befehls.](media/az-cli-loginServer-name.png)

<span data-ttu-id="d0758-165">**Abbildung 4-43**.</span><span class="sxs-lookup"><span data-stu-id="d0758-165">**Figure 4-43**.</span></span> <span data-ttu-id="d0758-166">Rufen Sie den Namen der Registrierung mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0758-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="d0758-167">In beiden Fällen müssen Sie den Namen abrufen.</span><span class="sxs-lookup"><span data-stu-id="d0758-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="d0758-168">In unserem Beispiel `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="d0758-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="d0758-169">Jetzt können Sie das Image, zu kennzeichnen dauert das neueste Image (dem Release-Image), mit dem Befehl:</span><span class="sxs-lookup"><span data-stu-id="d0758-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="d0758-170">Nach dem Ausführen der `docker tag` Befehl, Listen Sie die Images mit der `docker images` -Befehl, und Sie sollte das Image mit dem neuen Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0758-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Konsolenausgabe aus dem Befehl "Docker Images".](media/tagged-docker-images-list.png)

<span data-ttu-id="d0758-172">**Abbildung 4: 44**.</span><span class="sxs-lookup"><span data-stu-id="d0758-172">**Figure 4-44**.</span></span> <span data-ttu-id="d0758-173">Anzeigen der markierten images</span><span class="sxs-lookup"><span data-stu-id="d0758-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="d0758-174">Pushen Sie das Image in Azure ACR</span><span class="sxs-lookup"><span data-stu-id="d0758-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="d0758-175">Pushen Sie das Image in Azure ACR, mit dem folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="d0758-175">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="d0758-176">Mit diesem Befehl dauert eine Weile Hochladens von Bildern, jedoch erhalten Sie Feedback im Prozess.</span><span class="sxs-lookup"><span data-stu-id="d0758-176">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Konsolenausgabe aus dem Docker-Push-Befehl: Zeigt eine zeichenbasierte Statusleiste für jede Ebene.](media/uploading-image-to-acr.png)

<span data-ttu-id="d0758-178">**Abbildung 4-45**.</span><span class="sxs-lookup"><span data-stu-id="d0758-178">**Figure 4-45**.</span></span> <span data-ttu-id="d0758-179">Hochladen des Images in ACR</span><span class="sxs-lookup"><span data-stu-id="d0758-179">Uploading the image to the ACR</span></span>

<span data-ttu-id="d0758-180">Unten das Ergebnis sehen Sie, dass Sie nach Abschluss des Prozesses erhalten sollten:</span><span class="sxs-lookup"><span data-stu-id="d0758-180">You can see below the result you should get when the process completes:</span></span>

![Konsolenausgabe aus dem Docker-Push-Befehl, und fertig sind, zeigt alle Ebenen oder Knoten.](media/uploading-docker-images-complete.png)

<span data-ttu-id="d0758-182">**Abbildung 4: 46**.</span><span class="sxs-lookup"><span data-stu-id="d0758-182">**Figure 4-46**.</span></span> <span data-ttu-id="d0758-183">Anzeigen von Knoten</span><span class="sxs-lookup"><span data-stu-id="d0758-183">View of nodes</span></span>

<span data-ttu-id="d0758-184">Der nächste Schritt ist, Ihren Container in Ihrem ACS-Kubernetes-Cluster bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d0758-184">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="d0758-185">Dafür benötigen Sie eine Datei (**.yml dateibereitstellung**), die Folgendes enthält:</span><span class="sxs-lookup"><span data-stu-id="d0758-185">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
> <span data-ttu-id="d0758-186">Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="d0758-186">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="d0758-187">Jetzt Sie fast bereit, das Bereitstellen über **"kubectl"**, aber Sie müssen zuerst die Anmeldeinformationen für den AKS-Cluster mit dem folgenden Befehl abrufen:</span><span class="sxs-lookup"><span data-stu-id="d0758-187">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Konsolenausgabe des obigen Befehls: Zusammengeführte "MSSampleK8Cluster als den aktuellen Kontext im /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="d0758-189">**Abbildung 4: 47**.</span><span class="sxs-lookup"><span data-stu-id="d0758-189">**Figure 4-47**.</span></span> <span data-ttu-id="d0758-190">Abrufen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="d0758-190">getting credentials</span></span>

<span data-ttu-id="d0758-191">Verwenden Sie dann die `kubectl create` Befehl aus, um die Bereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="d0758-191">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Konsolenausgabe des obigen Befehls: Bereitstellung "Mssamplesbook" erstellt.](media/kubectl-create-command.png)

<span data-ttu-id="d0758-194">**Abbildung 4 – 48**.</span><span class="sxs-lookup"><span data-stu-id="d0758-194">**Figure 4-48**.</span></span> <span data-ttu-id="d0758-195">Bereitstellen in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="d0758-195">Deploy to Kubernetes</span></span>

<span data-ttu-id="d0758-196">Wenn die Bereitstellung abgeschlossen ist, können Sie die Kubernetes-Konsole mit einem lokalen Proxy zugreifen, die Sie mit diesem Befehl chronologisch zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="d0758-196">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="d0758-197">Und den Zugriff auf die Url `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="d0758-197">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Der Browseransicht der Kubernetes-Dashboard angezeigt werden, Bereitstellungen, Pods, Dienste und -Replikatsätze.](media/kubernetes-cluster-information.png)

<span data-ttu-id="d0758-199">**Abbildung 4-49**.</span><span class="sxs-lookup"><span data-stu-id="d0758-199">**Figure 4-49**.</span></span> <span data-ttu-id="d0758-200">Anzeigen von Informationen für Kubernetes-cluster</span><span class="sxs-lookup"><span data-stu-id="d0758-200">View Kubernetes cluster information</span></span>

<span data-ttu-id="d0758-201">Sie haben jetzt Ihre Anwendung in Azure mit einem Linux-Container und einem AKS-Kubernetes-Cluster bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d0758-201">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="d0758-202">Sie können Ihre app navigieren, um die öffentliche IP-Adresse des Diensts, die Sie im Azure-Portal abrufen können zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d0758-202">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="d0758-203">Sie erfahren, wie zum Erstellen des AKS-Clusters für dieses Beispiel im Abschnitt [ **bereitstellen auf Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) zu diesem Handbuch.</span><span class="sxs-lookup"><span data-stu-id="d0758-203">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d0758-204">[Zurück](set-up-windows-containers-with-powershell.md)
>[Weiter](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="d0758-204">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
