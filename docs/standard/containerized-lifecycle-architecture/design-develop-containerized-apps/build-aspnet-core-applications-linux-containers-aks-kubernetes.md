---
title: Erstellen von ASP.NET Core 2.1-Anwendungen wie Linux-Container in AKS/Kubernetes-Cluster bereitgestellt
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221488"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a><span data-ttu-id="aff66-103">Erstellen von ASP.NET Core 2.1-Anwendungen wie Linux-Container in AKS/Kubernetes-Orchestrators bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="aff66-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="aff66-104">Azure Kubernetes Service (AKS) ist von Azure verwalteten Kubernetes-Orchestrierungen-Dienste, die containerbereitstellung und Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="aff66-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="aff66-105">AKS-Hauptfunktionen sind:</span><span class="sxs-lookup"><span data-stu-id="aff66-105">AKS main features are:</span></span>

- <span data-ttu-id="aff66-106">Ein Azure-gehostete Steuerungsebene</span><span class="sxs-lookup"><span data-stu-id="aff66-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="aff66-107">Automatische Updates</span><span class="sxs-lookup"><span data-stu-id="aff66-107">Automated upgrades</span></span>
- <span data-ttu-id="aff66-108">Selbstkorrektur</span><span class="sxs-lookup"><span data-stu-id="aff66-108">Self-healing</span></span>
- <span data-ttu-id="aff66-109">Benutzer konfigurierbaren Skalierung</span><span class="sxs-lookup"><span data-stu-id="aff66-109">User configurable scaling</span></span>
- <span data-ttu-id="aff66-110">Ein einfacher Benutzererlebnis für Entwickler und clusterbetreiber.</span><span class="sxs-lookup"><span data-stu-id="aff66-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="aff66-111">Die folgenden Beispiele durchsuchen, die Erstellung einer ASP.NET Core 2.1-Anwendung, die unter Linux ausgeführt wird und auf einen AKS-Cluster in Azure bereitgestellt werden, während der Entwicklung erfolgt mithilfe von Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="aff66-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="aff66-112">Erstellen das ASP.NET Core 2.1-Projekt mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="aff66-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="aff66-113">ASP.NET Core ist eine allgemeine Entwicklungsplattform von Microsoft und der .NET-Community auf GitHub verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="aff66-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="aff66-114">Sie ist plattformübergreifend, d.h., sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in Einbettungs- und IoT-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aff66-114">It is cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="aff66-115">Dieses Beispiel verwendet ein einfaches Projekt, das basiert auf Grundlage einer Visual Studio Web-API-Vorlage, zusätzliche Kenntnisse zum Erstellen der Beispieldatenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aff66-115">This example uses a simple project that's based based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="aff66-116">Sie müssen nur zum Erstellen des Projekts mithilfe einer standard-Vorlage, die alle zum Ausführen von eines kleinen Projekts mit einer REST-API, die mit ASP.NET Core 2.1-Technologie-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="aff66-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![Fügen Sie Fenster "Neues Projekt hinzu" in Visual Studio, die Auswahl von ASP.NET Core-Webanwendung.](media/create-aspnet-core-application.png)

<span data-ttu-id="aff66-118">**Abbildung 4 bis 36**.</span><span class="sxs-lookup"><span data-stu-id="aff66-118">**Figure 4-36**.</span></span> <span data-ttu-id="aff66-119">Erstellen von ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="aff66-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="aff66-120">Um das Beispielprojekt zu erstellen, müssen Sie auswählen **Datei** > **neu** > **Projekt** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aff66-120">To create the sample project, you have to select **File** > **New** > **Project** on Visual Studio.</span></span> <span data-ttu-id="aff66-121">Und Sie eine Liste der Vorlagen für mehrere Typen von Projekten, sehen auf die Suche nach haben **Web** > **.NET Core** im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="aff66-121">Then you'll see a list of templates for several types of projects, where you have to look for **Web** > **.NET Core** on the left panel.</span></span> <span data-ttu-id="aff66-122">Wählen Sie in diesem Beispiel **ASP.NET Core-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="aff66-122">For this example select **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="aff66-123">Im nächsten Dialogfeld stellen Sie sicher, dass Sie .NET Core und ASP.NET Core 2.1 als das Zielframework in der oberen Pulldowns, wie in Abbildung 4-37, ausgewählt haben, und Sie dann die Option "API" zum Erstellen einer ASP.NET Core-Web-API-Anwendung wählen.</span><span class="sxs-lookup"><span data-stu-id="aff66-123">In the next dialog ensure that you have selected .NET Core and ASP.NET Core 2.1 as the target framework in the top pulldowns, as shown in figure 4-37, and then select the API option, to create an ASP.NET Core Web API application.</span></span>

<span data-ttu-id="aff66-124">Die .NET Core 2.1 ist im Visual Studio 2017 Version 15.7.0 enthalten oder höher und wird automatisch installiert und konfiguriert für die Sie bei der Auswahl der **plattformübergreifende Entwicklung mit .NET Core** Workload während der Installation.</span><span class="sxs-lookup"><span data-stu-id="aff66-124">The .NET Core 2.1 is included in Visual Studio 2017 version 15.7.0 or higher and is automatically installed and configured for you when you select the **.NET Core cross-platform development** workload during installation.</span></span>

![Visual Studio-Dialogfeld zum Auswählen von einer ASP.NET Core-Webanwendung mit API-Option ausgewählt ist.](media/create-web-api-application.png)

<span data-ttu-id="aff66-126">**Abbildung 4-37**.</span><span class="sxs-lookup"><span data-stu-id="aff66-126">**Figure 4-37**.</span></span> <span data-ttu-id="aff66-127">Auswählen von ASP.NET CORE 2.1 und Web-API-Projekttyp</span><span class="sxs-lookup"><span data-stu-id="aff66-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="aff66-128">Wenn Sie eine frühere Version von .NET Core verfügen, können Sie diese herunterladen und installieren Sie Version 2.1 von <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="aff66-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="aff66-129">Sie können Docker-Unterstützung hinzufügen, wenn das Projekt erstellen, im vorherigen Schritt, oder höher, bei Bedarf nach dem Starten des Projekts.</span><span class="sxs-lookup"><span data-stu-id="aff66-129">You can add Docker support when creating the project in the previous step, or later, if the need arises after starting the project.</span></span> <span data-ttu-id="aff66-130">Zum Hinzufügen der Docker-Unterstützung nach der projekterstellung mit der Maustaste, auf die Projektdatei in die **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **Docker-Unterstützung** auf Klicken Sie im Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="aff66-130">To add the Docker support after the project creation, right-click on the project file in the **Solution Explorer** and select **Add** > **Docker support** on the context menu.</span></span>

![Die Kontextmenüoption Docker-Unterstützung zu einem vorhandenen Projekt hinzufügen: Klicken Sie mit der rechten Maustaste (auf das Projekt) > Hinzufügen > Docker-Unterstützung.](media/add-docker-support-to-project.png)

<span data-ttu-id="aff66-132">**Abbildung 4-38**.</span><span class="sxs-lookup"><span data-stu-id="aff66-132">**Figure 4-38**.</span></span> <span data-ttu-id="aff66-133">Docker-Unterstützung zu vorhandenen Projekt hinzufügen</span><span class="sxs-lookup"><span data-stu-id="aff66-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="aff66-134">Zum Hinzufügen von Docker-Unterstützung abschließen zu können, müssen Sie die Auswahl von Windows oder Linux.</span><span class="sxs-lookup"><span data-stu-id="aff66-134">To complete adding Docker support, you have the choice of Windows or Linux.</span></span> <span data-ttu-id="aff66-135">Wählen Sie in diesem Fall **Linux**, da AKS Windows-Container (als Ende 2018) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aff66-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Dialogfeld Zielbetriebssystem für die dockerfile-Datei auswählen.](media/select-linux-docker-support.png)

<span data-ttu-id="aff66-137">**Abbildung 4-39**.</span><span class="sxs-lookup"><span data-stu-id="aff66-137">**Figure 4-39**.</span></span> <span data-ttu-id="aff66-138">Auswählen von Linux-Container.</span><span class="sxs-lookup"><span data-stu-id="aff66-138">Selecting Linux containers.</span></span>

<span data-ttu-id="aff66-139">Mit diesen einfachen Schritten müssen Sie Ihre ASP.NET Core 2.1-Anwendung, die auf einem Linux-Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aff66-139">With these simple steps, you will have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="aff66-140">Wie Sie sehen können, ist die Integration zwischen Visual Studio 2017 und Docker auf die die Produktivität der Entwickler vollständig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="aff66-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="aff66-141">Nachdem Sie drücken können **F5** erstellen und Ausführen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="aff66-141">Now you can press **F5** to build and run your application.</span></span>

<span data-ttu-id="aff66-142">Nach dem Ausführen des Projekts, können Sie Auflisten der Images mithilfe der `docker images` Befehl.</span><span class="sxs-lookup"><span data-stu-id="aff66-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="aff66-143">Daraufhin sollte die `mssampleapplication` Image mit für das automatische Bereitstellen unseres Projekts mit Visual Studio 2017 erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="aff66-143">You should see the `mssampleapplication` image created with the automatic deploy of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Konsolenausgabe aus dem Befehl "Docker Images" zeigt eine Liste mit: Repository, Tag, Bild-ID, Created (Datum) und Größe.](media/docker-images-command.png)

<span data-ttu-id="aff66-145">**Abbildung 4 – 40**.</span><span class="sxs-lookup"><span data-stu-id="aff66-145">**Figure 4-40**.</span></span> <span data-ttu-id="aff66-146">Anzeigen der Docker-images</span><span class="sxs-lookup"><span data-stu-id="aff66-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="aff66-147">Registrieren Sie die Lösung in Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="aff66-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="aff66-148">Hochladen des Images an eine beliebige Docker-Registrierung, wie z. B. [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) oder Docker-Hub, damit die Bilder in die Registrierung mit dem AKS-Cluster bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="aff66-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="aff66-149">In diesem Fall haben wir das Image in Azure Container Registry hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="aff66-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="aff66-150">Erstellen Sie das Image im Releasemodus</span><span class="sxs-lookup"><span data-stu-id="aff66-150">Create the image in Release mode</span></span>

<span data-ttu-id="aff66-151">Erstellen Sie das Image in **Version** Modus (bereit für die Produktion) in Version ändern, wie hier gezeigt, und drücken Sie F5, um die Anwendung erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="aff66-151">Create the image in **Release** Mode (ready for production) changing to Release as shown here and press F5 to run the application again.</span></span>

![Symbolleistenoption in Visual Studio im Releasemodus zu erstellen.](media/select-release-mode.png)

<span data-ttu-id="aff66-153">**Abbildung 4: 41**.</span><span class="sxs-lookup"><span data-stu-id="aff66-153">**Figure 4-41**.</span></span> <span data-ttu-id="aff66-154">Auswählen der Releasemodus</span><span class="sxs-lookup"><span data-stu-id="aff66-154">Selecting Release Mode</span></span>

<span data-ttu-id="aff66-155">Bei Ausführung der `docker image` Befehl sehen Sie beide Bilder erstellt.</span><span class="sxs-lookup"><span data-stu-id="aff66-155">If you execute the `docker image` command, you'll see both images created.</span></span> <span data-ttu-id="aff66-156">Eine für `debug` und die andere für `release` Modus.</span><span class="sxs-lookup"><span data-stu-id="aff66-156">One for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="aff66-157">Erstellen eines neuen Transponders für das Image</span><span class="sxs-lookup"><span data-stu-id="aff66-157">Create a new Tag for the Image</span></span>

<span data-ttu-id="aff66-158">Jedes containerimage muss mit gekennzeichnet werden die `loginServer` -Namen der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="aff66-158">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="aff66-159">Dieses Tag wird für die Übertragung von containerimages in eine imageregistrierung routing verwendet.</span><span class="sxs-lookup"><span data-stu-id="aff66-159">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="aff66-160">Sie können anzeigen, die `loginServer` Name im Azure-Portal, nehmen die Informationen aus der Azure-Containerregistrierung</span><span class="sxs-lookup"><span data-stu-id="aff66-160">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Browseransicht der den Namen der Azure-containerregistrierung, auf der rechten oberen Ecke.](media/loginServer-name.png)

<span data-ttu-id="aff66-162">**Abbildung 4-42**.</span><span class="sxs-lookup"><span data-stu-id="aff66-162">**Figure 4-42**.</span></span> <span data-ttu-id="aff66-163">Überblick über den Namen der Registrierung</span><span class="sxs-lookup"><span data-stu-id="aff66-163">View of the name of the Registry</span></span>

<span data-ttu-id="aff66-164">Oder durch den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="aff66-164">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des obigen Befehls.](media/az-cli-loginServer-name.png)

<span data-ttu-id="aff66-166">**Abbildung 4-43**.</span><span class="sxs-lookup"><span data-stu-id="aff66-166">**Figure 4-43**.</span></span> <span data-ttu-id="aff66-167">Rufen Sie den Namen der Registrierung mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="aff66-167">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="aff66-168">In beiden Fällen müssen Sie den Namen abrufen.</span><span class="sxs-lookup"><span data-stu-id="aff66-168">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="aff66-169">In unserem Beispiel `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="aff66-169">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="aff66-170">Jetzt können Sie das Bild, markieren, erstellen das neueste Image (Release-Image), mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="aff66-170">Now you can tag the image, taking the latest image (Release image), with the following command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="aff66-171">Nach dem Ausführen der `docker tag` Befehl, Listen Sie die Images mit der `docker images` Befehl.</span><span class="sxs-lookup"><span data-stu-id="aff66-171">After running the `docker tag` command, list the images with the `docker images` command.</span></span> <span data-ttu-id="aff66-172">Das Image mit das neue Tag sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aff66-172">You should see the image with the new tag.</span></span>

![Konsolenausgabe aus dem Befehl "Docker Images".](media/tagged-docker-images-list.png)

<span data-ttu-id="aff66-174">**Abbildung 4: 44**.</span><span class="sxs-lookup"><span data-stu-id="aff66-174">**Figure 4-44**.</span></span> <span data-ttu-id="aff66-175">Anzeigen der markierten images</span><span class="sxs-lookup"><span data-stu-id="aff66-175">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="aff66-176">Pushen Sie das Image in Azure ACR</span><span class="sxs-lookup"><span data-stu-id="aff66-176">Push the image into the Azure ACR</span></span>

<span data-ttu-id="aff66-177">Pushen Sie das Image in Azure ACR, mit dem folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="aff66-177">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="aff66-178">Mit diesem Befehl dauert eine Weile Hochladens von Bildern, jedoch erhalten Sie Feedback im Prozess.</span><span class="sxs-lookup"><span data-stu-id="aff66-178">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Konsolenausgabe aus dem Docker-Push-Befehl: Zeigt eine zeichenbasierte Statusleiste für jede Ebene.](media/uploading-image-to-acr.png)

<span data-ttu-id="aff66-180">**Abbildung 4-45**.</span><span class="sxs-lookup"><span data-stu-id="aff66-180">**Figure 4-45**.</span></span> <span data-ttu-id="aff66-181">Hochladen des Images in ACR</span><span class="sxs-lookup"><span data-stu-id="aff66-181">Uploading the image to the ACR</span></span>

<span data-ttu-id="aff66-182">Unten das Ergebnis sehen Sie, dass Sie nach Abschluss des Prozesses erhalten sollten:</span><span class="sxs-lookup"><span data-stu-id="aff66-182">You can see below the result you should get when the process completes:</span></span>

![Konsolenausgabe aus dem Docker-Push-Befehl, und fertig sind, zeigt alle Ebenen oder Knoten.](media/uploading-docker-images-complete.png)

<span data-ttu-id="aff66-184">**Abbildung 4: 46**.</span><span class="sxs-lookup"><span data-stu-id="aff66-184">**Figure 4-46**.</span></span> <span data-ttu-id="aff66-185">Anzeigen von Knoten</span><span class="sxs-lookup"><span data-stu-id="aff66-185">View of nodes</span></span>

<span data-ttu-id="aff66-186">Der nächste Schritt ist, Ihren Container in Ihrem ACS-Kubernetes-Cluster bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aff66-186">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="aff66-187">Dafür benötigen Sie eine Datei (**.yml dateibereitstellung**), die in diesem Fall enthält:</span><span class="sxs-lookup"><span data-stu-id="aff66-187">For that you need a file (**.yml deploy file**) that, in this case, contains:</span></span>

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
> <span data-ttu-id="aff66-188">Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="aff66-188">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="aff66-189">Jetzt Sie fast bereit, das Bereitstellen über **"kubectl"**, aber Sie müssen zuerst die Anmeldeinformationen für den AKS-Cluster mit dem folgenden Befehl abrufen:</span><span class="sxs-lookup"><span data-stu-id="aff66-189">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Konsolenausgabe des obigen Befehls: Zusammengeführte "MSSampleK8Cluster als den aktuellen Kontext im /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="aff66-191">**Abbildung 4: 47**.</span><span class="sxs-lookup"><span data-stu-id="aff66-191">**Figure 4-47**.</span></span> <span data-ttu-id="aff66-192">Abrufen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="aff66-192">getting credentials</span></span>

<span data-ttu-id="aff66-193">Verwenden Sie dann die `kubectl create` Befehl aus, um die Bereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="aff66-193">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Konsolenausgabe des obigen Befehls: Bereitstellung "Mssamplesbook" erstellt.](media/kubectl-create-command.png)

<span data-ttu-id="aff66-196">**Abbildung 4 – 48**.</span><span class="sxs-lookup"><span data-stu-id="aff66-196">**Figure 4-48**.</span></span> <span data-ttu-id="aff66-197">Bereitstellen in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="aff66-197">Deploy to Kubernetes</span></span>

<span data-ttu-id="aff66-198">Wenn die Bereitstellung abgeschlossen ist, können Sie die Kubernetes-Konsole mit einem lokalen Proxy zugreifen, die Sie mit diesem Befehl chronologisch zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="aff66-198">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="aff66-199">Und den Zugriff auf die Url `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="aff66-199">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Der Browseransicht der Kubernetes-Dashboard angezeigt werden, Bereitstellungen, Pods, Dienste und -Replikatsätze.](media/kubernetes-cluster-information.png)

<span data-ttu-id="aff66-201">**Abbildung 4-49**.</span><span class="sxs-lookup"><span data-stu-id="aff66-201">**Figure 4-49**.</span></span> <span data-ttu-id="aff66-202">Anzeigen von Informationen für Kubernetes-cluster</span><span class="sxs-lookup"><span data-stu-id="aff66-202">View Kubernetes cluster information</span></span>

<span data-ttu-id="aff66-203">Sie haben jetzt Ihre Anwendung in Azure mit einem Linux-Container und einem AKS-Kubernetes-Cluster bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aff66-203">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="aff66-204">Sie können Ihre app navigieren, um die öffentliche IP-Adresse des Diensts, die Sie im Azure-Portal abrufen können zugreifen.</span><span class="sxs-lookup"><span data-stu-id="aff66-204">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="aff66-205">Sie erfahren, wie zum Erstellen des AKS-Clusters für dieses Beispiel im Abschnitt [ **bereitstellen auf Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) zu diesem Handbuch.</span><span class="sxs-lookup"><span data-stu-id="aff66-205">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aff66-206">[Zurück](set-up-windows-containers-with-powershell.md)
>[Weiter](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="aff66-206">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
