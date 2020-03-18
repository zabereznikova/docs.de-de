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
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="cca24-103">Erstellen von ASP.NET Core 2.2-Anwendungen, die als Linux-Container in einem AKS-/Kubernetes-Orchestrator bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="cca24-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="cca24-104">Azure Kubernetes Services (AKS) ist der verwaltete Kubernetes-Orchestrierungsdienst von Azure, der die Bereitstellung und Verwaltung von Containern vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="cca24-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="cca24-105">Dies sind die wichtigsten Features von AKS:</span><span class="sxs-lookup"><span data-stu-id="cca24-105">AKS main features are:</span></span>

- <span data-ttu-id="cca24-106">Eine auf Azure gehostete Steuerungsebene</span><span class="sxs-lookup"><span data-stu-id="cca24-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="cca24-107">Automatisierte Upgrades</span><span class="sxs-lookup"><span data-stu-id="cca24-107">Automated upgrades</span></span>
- <span data-ttu-id="cca24-108">Selbstreparatur</span><span class="sxs-lookup"><span data-stu-id="cca24-108">Self-healing</span></span>
- <span data-ttu-id="cca24-109">Vom Benutzer zu konfigurierende Skalierung</span><span class="sxs-lookup"><span data-stu-id="cca24-109">User configurable scaling</span></span>
- <span data-ttu-id="cca24-110">Eine einfacheres Benutzererlebnis sowohl für Entwickler als auch für Clusterbetreiber.</span><span class="sxs-lookup"><span data-stu-id="cca24-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="cca24-111">Die folgenden Beispiele untersuchen die Erstellung einer ASP.NET Core 2.2-Anwendung, die unter Linux ausgeführt und auf einem AKS-Cluster in Azure bereitgestellt wird, während die Entwicklung in Visual Studio 2017 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="cca24-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="cca24-112">Erstellen des ASP.NET Core 2.2-Projekts mithilfe von Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cca24-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="cca24-113">ASP.NET Core ist eine universelle Entwicklungsplattform, die von Microsoft und der .NET-Community auf GitHub gepflegt wird.</span><span class="sxs-lookup"><span data-stu-id="cca24-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="cca24-114">Sie ist plattformübergreifend, d.h. sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in Einbettungs- und IoT-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cca24-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="cca24-115">Dieses Beispiel verwendet ein einfaches Projekt, das auf einer Visual Studio Web-API-Vorlage basiert, sodass Sie zum Erstellen des Beispiels keine weiteren Kenntnisse benötigen.</span><span class="sxs-lookup"><span data-stu-id="cca24-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="cca24-116">Sie müssen lediglich das Projekt mithilfe einer Standardvorlage erstellen, die alle Elemente zum Ausführen eines kleinen Projekts mit einer REST-API beinhaltet und ASP.NET Core 2.2-Technologie verwendet.</span><span class="sxs-lookup"><span data-stu-id="cca24-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Fenster zum Hinzufügen eines neuen Projekts in Visual Studio mit ausgewählter ASP.NET Core-Webanwendung.](media/create-aspnet-core-application.png)

<span data-ttu-id="cca24-118">**Abbildung 4–36**.</span><span class="sxs-lookup"><span data-stu-id="cca24-118">**Figure 4-36**.</span></span> <span data-ttu-id="cca24-119">Erstellen einer ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="cca24-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="cca24-120">Wählen Sie zum Erstellen des Beispielprojekts in Visual Studio **Datei** > **Neu** > **Projekt** aus, und wählen Sie dann im linken Bereich die **Web**-Projekttypen aus, gefolgt von **ASP.NET Core-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="cca24-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="cca24-121">Visual Studio listet Vorlagen für Webprojekte auf.</span><span class="sxs-lookup"><span data-stu-id="cca24-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="cca24-122">Wählen Sie für unser Beispiel **API** aus, um eine ASP.NET Web-API-Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cca24-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="cca24-123">Vergewissern Sie sich, dass Sie ASP.NET Core 2.2 als Framework ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="cca24-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="cca24-124">.NET Core 2.2 ist in der letzten Version von Visual Studio 2017 enthalten und wird automatisch für Sie installiert und konfiguriert, wenn Sie Visual Studio 2017 installieren.</span><span class="sxs-lookup"><span data-stu-id="cca24-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Visual Studio-Dialogfeld zum Auswählen des Typs einer ASP.NET Core-Webanwendung mit ausgewählter API-Option.](media/create-web-api-application.png)

<span data-ttu-id="cca24-126">**Abbildung 4–37**.</span><span class="sxs-lookup"><span data-stu-id="cca24-126">**Figure 4-37**.</span></span> <span data-ttu-id="cca24-127">Auswählen des Projekttyps ASP.NET CORE 2.2 und Web-API</span><span class="sxs-lookup"><span data-stu-id="cca24-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="cca24-128">Wenn Sie über eine frühere Version von .NET Core verfügen, können Sie die Version 2.2 hier herunterladen und installieren: <https://dotnet.microsoft.com/download>.</span><span class="sxs-lookup"><span data-stu-id="cca24-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="cca24-129">Sie können Docker-Unterstützung beim Erstellen des Projekts oder später hinzufügen – Sie können Ihr Projekt also jederzeit „Dockern“.</span><span class="sxs-lookup"><span data-stu-id="cca24-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="cca24-130">Um Docker-Unterstützung nach der Projekterstellung hinzuzufügen, klicken Sie mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und wählen Sie im Kontextmenü **Hinzufügen** > **Docker-Unterstützung** aus.</span><span class="sxs-lookup"><span data-stu-id="cca24-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Kontextmenüoption zum Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt: Mit der rechten Maustaste (auf dem Projekt) klicken > Hinzufügen > Docker-Unterstützung.](media/add-docker-support-to-project.png)

<span data-ttu-id="cca24-132">**Abbildung 4–38**.</span><span class="sxs-lookup"><span data-stu-id="cca24-132">**Figure 4-38**.</span></span> <span data-ttu-id="cca24-133">Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt</span><span class="sxs-lookup"><span data-stu-id="cca24-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="cca24-134">Um das Hinzufügen von Docker-Unterstützung abzuschließen, können Sie Windows oder Linux auswählen.</span><span class="sxs-lookup"><span data-stu-id="cca24-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="cca24-135">Wählen Sie in diesem Fall **Linux** aus, da AKS keine Windows-Container unterstützt (Stand Ende 2018).</span><span class="sxs-lookup"><span data-stu-id="cca24-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Optionsdialogfeld für die Auswahl des Betriebssystems für Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="cca24-137">**Abbildung 4–39**.</span><span class="sxs-lookup"><span data-stu-id="cca24-137">**Figure 4-39**.</span></span> <span data-ttu-id="cca24-138">Auswählen von Linux-Containern.</span><span class="sxs-lookup"><span data-stu-id="cca24-138">Selecting Linux containers.</span></span>

<span data-ttu-id="cca24-139">Mit diesen einfachen Schritten haben Sie festgelegt, dass Ihre ASP.NET Core 2.2-Anwendung in einem Linux-Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cca24-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="cca24-140">Wie Sie sehen können, ist die Integration von Visual Studio 2017 und Docker völlig auf die Produktivität des Entwicklers ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="cca24-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="cca24-141">Jetzt können Sie Ihre Anwendung mit der Taste **F5** oder der Schaltfläche **Wiedergabe** ausführen.</span><span class="sxs-lookup"><span data-stu-id="cca24-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="cca24-142">Nach dem Ausführen des Projekts können Sie die Images mithilfe des Befehls `docker images` auflisten.</span><span class="sxs-lookup"><span data-stu-id="cca24-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="cca24-143">Sie sollten das Image `mssampleapplication` sehen, das von der automatischen Bereitstellung Ihres Projekts mit Visual Studio 2017 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cca24-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Konsolenausgabe des docker images-Befehls, eine Liste mit diesem Inhalt: Repository, Tag, Image-ID, Erstellungsdatum und Größe.](media/docker-images-command.png)

<span data-ttu-id="cca24-145">**Abbildung 4–40**.</span><span class="sxs-lookup"><span data-stu-id="cca24-145">**Figure 4-40**.</span></span> <span data-ttu-id="cca24-146">Ansicht von Docker-Images</span><span class="sxs-lookup"><span data-stu-id="cca24-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="cca24-147">Registrieren der Projektmappe in der Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="cca24-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="cca24-148">Laden Sie das Image in eine beliebige Docker-Registrierung hoch, wie etwa [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) oder Docker Hub, damit die Images aus dieser Registrierung auf dem AKS-Cluster bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="cca24-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="cca24-149">In diesem Fall laden wir das Image in die Azure Container Registry hoch.</span><span class="sxs-lookup"><span data-stu-id="cca24-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="cca24-150">Erstellen des Images im Releasemodus</span><span class="sxs-lookup"><span data-stu-id="cca24-150">Create the image in Release mode</span></span>

<span data-ttu-id="cca24-151">Wir erstellen jetzt das Image im **Releasemodus** (für die Produktion bereit), indem wir zu **Release** wechseln, wie in Abbildung 4–41 dargestellt, und die Anwendung ausführen wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="cca24-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Symbolleistenoption in Visual Studio zum Erstellen im Releasemodus.](media/select-release-mode.png)

<span data-ttu-id="cca24-153">**Abbildung 4–41**.</span><span class="sxs-lookup"><span data-stu-id="cca24-153">**Figure 4-41**.</span></span> <span data-ttu-id="cca24-154">Auswählen des Releasemodus</span><span class="sxs-lookup"><span data-stu-id="cca24-154">Selecting Release Mode</span></span>

<span data-ttu-id="cca24-155">Wenn Sie den Befehl `docker image` ausführen, sehen Sie, dass beide Images erstellt werden, eins für den `debug`- und das andere für den `release`-Modus.</span><span class="sxs-lookup"><span data-stu-id="cca24-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="cca24-156">Erstellen eines neuen Tags für das Image</span><span class="sxs-lookup"><span data-stu-id="cca24-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="cca24-157">Jedes Containerimage muss mit dem `loginServer`-Namen der Registrierung gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="cca24-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="cca24-158">Dieses Tag wird beim Übertragen von Containerimages per Push in eine Imageregistrierung für das Routing verwendet.</span><span class="sxs-lookup"><span data-stu-id="cca24-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="cca24-159">Sie können den Namen des `loginServer` im Azure-Portal anzeigen, indem Sie die Informationen aus der Azure Container Registry übernehmen.</span><span class="sxs-lookup"><span data-stu-id="cca24-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Browseransicht des Namens in der Azure Container Registry rechts oben.](media/loginServer-name.png)

<span data-ttu-id="cca24-161">**Abbildung 4–42**.</span><span class="sxs-lookup"><span data-stu-id="cca24-161">**Figure 4-42**.</span></span> <span data-ttu-id="cca24-162">Ansicht des Namens der Registry</span><span class="sxs-lookup"><span data-stu-id="cca24-162">View of the name of the Registry</span></span>

<span data-ttu-id="cca24-163">Alternativ können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="cca24-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des Befehls oben.](media/az-cli-loginServer-name.png)

<span data-ttu-id="cca24-165">**Abbildung 4–43**.</span><span class="sxs-lookup"><span data-stu-id="cca24-165">**Figure 4-43**.</span></span> <span data-ttu-id="cca24-166">Rufen Sie den Namen der Registrierung mithilfe von PowerShell ab</span><span class="sxs-lookup"><span data-stu-id="cca24-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="cca24-167">In beiden Fällen erhalten Sie den Namen.</span><span class="sxs-lookup"><span data-stu-id="cca24-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="cca24-168">In unserem Beispiel `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="cca24-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="cca24-169">Jetzt können Sie das Image mit einem Tag kennzeichnen, indem Sie für das aktuellste Image (das Releaseimage) diesen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="cca24-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="cca24-170">Nach dem Ausführen des `docker tag`-Befehls können Sie die Images mit dem Befehl `docker images` auflisten, dann sollten Sie das Image mit dem neuen Tag sehen.</span><span class="sxs-lookup"><span data-stu-id="cca24-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Konsolenausgabe des docker images-Befehls.](media/tagged-docker-images-list.png)

<span data-ttu-id="cca24-172">**Abbildung 4–44**.</span><span class="sxs-lookup"><span data-stu-id="cca24-172">**Figure 4-44**.</span></span> <span data-ttu-id="cca24-173">Ansicht von mit Tags gekennzeichneten Images</span><span class="sxs-lookup"><span data-stu-id="cca24-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="cca24-174">Pushen des Images in die Azure ACR</span><span class="sxs-lookup"><span data-stu-id="cca24-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="cca24-175">Melden Sie sich bei der Azure Container Registry an.</span><span class="sxs-lookup"><span data-stu-id="cca24-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="cca24-176">Übertragen Sie das Image mit dem folgenden Befehl per Push in die Azure ACR:</span><span class="sxs-lookup"><span data-stu-id="cca24-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="cca24-177">Dieser Befehl benötigt etwas Zeit zum Hochladen von Images, gibt Ihnen aber Feedback zum Verlauf.</span><span class="sxs-lookup"><span data-stu-id="cca24-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Konsolenausgabe des docker push-Befehls: Zeigt einen zeichenbasierten Verlaufsbalken für jede Schicht an.](media/uploading-image-to-acr.png)

<span data-ttu-id="cca24-179">**Abbildung 4–45**.</span><span class="sxs-lookup"><span data-stu-id="cca24-179">**Figure 4-45**.</span></span> <span data-ttu-id="cca24-180">Hochladen des Images in die ACR</span><span class="sxs-lookup"><span data-stu-id="cca24-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="cca24-181">Unten sehen Sie das Ergebnis, das Sie nach Abschluss des Prozesses erhalten sollten:</span><span class="sxs-lookup"><span data-stu-id="cca24-181">You can see below the result you should get when the process completes:</span></span>

![Konsolenausgabe des docker push-Befehls nach dem Abschluss mit Anzeige aller Schichten oder Knoten.](media/uploading-docker-images-complete.png)

<span data-ttu-id="cca24-183">**Abbildung 4–46**.</span><span class="sxs-lookup"><span data-stu-id="cca24-183">**Figure 4-46**.</span></span> <span data-ttu-id="cca24-184">Ansicht von Knoten</span><span class="sxs-lookup"><span data-stu-id="cca24-184">View of nodes</span></span>

<span data-ttu-id="cca24-185">Der nächste Schritt besteht im Bereitstellen Ihres Containers in Ihrem AKS Kubernetes-Cluster.</span><span class="sxs-lookup"><span data-stu-id="cca24-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="cca24-186">Dazu benötigen Sie eine Datei (**YML-Bereitstellungsdatei**), die folgende Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="cca24-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
> <span data-ttu-id="cca24-187">Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.</span><span class="sxs-lookup"><span data-stu-id="cca24-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="cca24-188">Jetzt sind Sie fast zur Bereitstellung mit **Kubectl** bereit, zunächst müssen Sie jedoch die Anmeldeinformationen für den AKS-Cluster mit diesem Befehl abrufen:</span><span class="sxs-lookup"><span data-stu-id="cca24-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Konsolenausgabe des Befehls oben: Merge von „MSSampleK8Cluster“ als aktueller Kontext in „/root/.kube/config“](media/getting-aks-credentials.png)

<span data-ttu-id="cca24-190">**Abbildung 4–47**.</span><span class="sxs-lookup"><span data-stu-id="cca24-190">**Figure 4-47**.</span></span> <span data-ttu-id="cca24-191">Abrufen von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="cca24-191">getting credentials</span></span>

<span data-ttu-id="cca24-192">Verwenden Sie anschließend den `kubectl create`-Befehl, um die Bereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="cca24-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Konsolenausgabe des Befehls oben: „deployment ‚mssamplesbook‘ created.](media/kubectl-create-command.png)

<span data-ttu-id="cca24-195">**Abbildung 4–48**.</span><span class="sxs-lookup"><span data-stu-id="cca24-195">**Figure 4-48**.</span></span> <span data-ttu-id="cca24-196">Bereitstellen in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="cca24-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="cca24-197">Wenn die Bereitstellung abgeschlossen ist, können Sie mit einem lokalen Proxy, auf den Sie zeitweilig mit diesem Befehl zugreifen können, auf die Kubernetes-Konsole zugreifen:</span><span class="sxs-lookup"><span data-stu-id="cca24-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="cca24-198">Und greifen Sie auf die URL `http://127.0.0.1:8001` zu.</span><span class="sxs-lookup"><span data-stu-id="cca24-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Browseransicht des Kubernetes-Dashboards mit Bereitstellungen, Pods, Replikatsätzen und Diensten.](media/kubernetes-cluster-information.png)

<span data-ttu-id="cca24-200">**Abbildung 4–49**.</span><span class="sxs-lookup"><span data-stu-id="cca24-200">**Figure 4-49**.</span></span> <span data-ttu-id="cca24-201">Anzeigen von Kubernetes-Clusterinformationen</span><span class="sxs-lookup"><span data-stu-id="cca24-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="cca24-202">Sie haben jetzt Ihre Anwendung auf Azure bereitgestellt und dazu einen Linux-Container und einen AKS Kubernetes-Cluster verwendet.</span><span class="sxs-lookup"><span data-stu-id="cca24-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="cca24-203">Sie können auf Ihre App zugreifen, indem Sie zur öffentlichen IP-Adresse Ihres Diensts navigieren, die Sie im Azure-Portal abrufen können.</span><span class="sxs-lookup"><span data-stu-id="cca24-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="cca24-204">Informationen zum Erstellen des AKS-Clusters für dieses Beispiel finden Sie in Abschnitt [**Bereitstellen für Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) in diesem Handbuch.</span><span class="sxs-lookup"><span data-stu-id="cca24-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cca24-205">[Zurück](set-up-windows-containers-with-powershell.md)
>[Weiter](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="cca24-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
