---
title: Erstellen von ASP.NET Core-Anwendungen, die als Linux-Container in AKS-/Kubernetes-Clustern bereitgestellt werden
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.date: 01/06/2021
ms.openlocfilehash: 7a8f8272ab2faabd0398aeeb2039b6f034b4dedb
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970627"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="f2622-103">Erstellen von als Linux-Container in einem AKS-/Kubernetes-Orchestrator bereitgestellten ASP.NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f2622-103">Build ASP.NET Core applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="f2622-104">Azure Kubernetes Services (AKS) ist der verwaltete Kubernetes-Orchestrierungsdienst von Azure, der die Bereitstellung und Verwaltung von Containern vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="f2622-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="f2622-105">Dies sind die wichtigsten Features von AKS:</span><span class="sxs-lookup"><span data-stu-id="f2622-105">AKS main features are:</span></span>

- <span data-ttu-id="f2622-106">Eine auf Azure gehostete Steuerungsebene</span><span class="sxs-lookup"><span data-stu-id="f2622-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="f2622-107">Automatisierte Upgrades</span><span class="sxs-lookup"><span data-stu-id="f2622-107">Automated upgrades</span></span>
- <span data-ttu-id="f2622-108">Selbstreparatur</span><span class="sxs-lookup"><span data-stu-id="f2622-108">Self-healing</span></span>
- <span data-ttu-id="f2622-109">Durch den Benutzer konfigurierbare Skalierung</span><span class="sxs-lookup"><span data-stu-id="f2622-109">User-configurable scaling</span></span>
- <span data-ttu-id="f2622-110">Einfacheres Benutzererlebnis sowohl für Entwickler als auch für Clusterbetreiber.</span><span class="sxs-lookup"><span data-stu-id="f2622-110">Simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="f2622-111">In den folgenden Beispielen wird die Erstellung einer ASP.NET Core 5.0-Anwendung untersucht, die unter Linux ausgeführt und auf einem AKS-Cluster in Azure bereitgestellt wird, während die Entwicklung in Version 16.8 von Visual Studio 2019 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f2622-111">The following examples explore the creation of an ASP.NET Core 5.0 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2019 version 16.8.</span></span>

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a><span data-ttu-id="f2622-112">Erstellen des ASP.NET Core 2019-Projekts mithilfe von Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f2622-112">Creating the ASP.NET Core Project using Visual Studio 2019</span></span>

<span data-ttu-id="f2622-113">ASP.NET Core ist eine universelle Entwicklungsplattform, die von Microsoft und der .NET-Community auf GitHub gepflegt wird.</span><span class="sxs-lookup"><span data-stu-id="f2622-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="f2622-114">Sie ist plattformübergreifend, d.h. sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in Einbettungs- und IoT-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2622-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="f2622-115">In diesem Beispiel werden einige einfache Projekte verwendet, die auf Visual Studio-Vorlagen basieren, sodass Sie zum Erstellen des Beispiels nicht viel zusätzliches Wissen benötigen.</span><span class="sxs-lookup"><span data-stu-id="f2622-115">This example uses a couple of simple projects based on Visual Studio templates, so you don't need much additional knowledge to create the sample.</span></span> <span data-ttu-id="f2622-116">Sie müssen das Projekt nur mit einer Standardvorlage erstellen, die alle Elemente enthält, um ein kleines Projekt mit einer REST-API und einer Web-App mit Razor Pages unter Verwendung von ASP.NET Core 5.0-Technologie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f2622-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API and a Web App with Razor pages, using ASP.NET Core 5.0 technology.</span></span>

![Fenster zum Hinzufügen eines neuen Projekts in Visual Studio mit ausgewählter ASP.NET Core-Webanwendung.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

<span data-ttu-id="f2622-118">**Abbildung 4–35**.</span><span class="sxs-lookup"><span data-stu-id="f2622-118">**Figure 4-35**.</span></span> <span data-ttu-id="f2622-119">Erstellen einer ASP.NET Core-Webanwendung in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f2622-119">Creating an ASP.NET Core Web Application in Visual Studio 2019.</span></span>

<span data-ttu-id="f2622-120">Um das Beispielprojekt in Visual Studio zu erstellen, wählen Sie **Datei** > **Neu** > **Projekt** aus, wählen Sie den Projekttyp **Web** und dann die Vorlage **ASP.NET Core-Webanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="f2622-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project type and then the **ASP.NET Core Web Application** template.</span></span> <span data-ttu-id="f2622-121">Sie können auch nach der Vorlage suchen, wenn Sie sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="f2622-121">You can also search for the template if you need it.</span></span>

<span data-ttu-id="f2622-122">Geben Sie dann den Namen und den Speicherort der Anwendung wie in der nächsten Abbildung gezeigt ein.</span><span class="sxs-lookup"><span data-stu-id="f2622-122">Then enter the application name and location as shown in the next image.</span></span>

![Geben Sie den Projektnamen und den Speicherort ein.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

<span data-ttu-id="f2622-124">**Abbildung 4–36**.</span><span class="sxs-lookup"><span data-stu-id="f2622-124">**Figure 4-36**.</span></span> <span data-ttu-id="f2622-125">Geben Sie den Projektnamen und den Speicherort in Visual Studio 2019 ein.</span><span class="sxs-lookup"><span data-stu-id="f2622-125">Enter the project name and location in Visual Studio 2019.</span></span>

<span data-ttu-id="f2622-126">Vergewissern Sie sich, dass Sie ASP.NET Core 5.0 als Framework ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f2622-126">Verify that you've selected ASP.NET Core 5.0 as the framework.</span></span> <span data-ttu-id="f2622-127">.NET 5.0 ist im neuesten Release von Visual Studio 2019 enthalten und wird automatisch für Sie installiert und konfiguriert, wenn Sie Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="f2622-127">.NET 5.0 is included in the latest release of Visual Studio 2019 and is automatically installed and configured for you when you install Visual Studio.</span></span>

![Visual Studio-Dialogfeld zum Auswählen des Typs einer ASP.NET Core-Webanwendung mit ausgewählter API-Option.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

<span data-ttu-id="f2622-129">**Abbildung 4–37**.</span><span class="sxs-lookup"><span data-stu-id="f2622-129">**Figure 4-37**.</span></span> <span data-ttu-id="f2622-130">Auswählen von ASP.NET Core 5.0 und des Projekttyps „Web-API“</span><span class="sxs-lookup"><span data-stu-id="f2622-130">Selecting ASP.NET CORE 5.0 and Web API project type</span></span>

<span data-ttu-id="f2622-131">Beachten Sie, dass Docker-Unterstützung jetzt nicht aktiviert ist, um zu zeigen, dass dies nach der Projekterstellung erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="f2622-131">Notice Docker support is not enabled now, just to show it can be done after project creation.</span></span>

<span data-ttu-id="f2622-132">Wenn Sie über eine frühere Version von .NET Core verfügen, können Sie Version 3.1 hier herunterladen und installieren: <https://dotnet.microsoft.com/download>.</span><span class="sxs-lookup"><span data-stu-id="f2622-132">If you have any previous version of .NET Core, you can download and install the 3.1 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="f2622-133">Um zu zeigen, dass Sie das Projekt jederzeit „dockerisieren“ können, fügen Sie jetzt Docker-Unterstützung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2622-133">To show you can "Dockerize" your project at any time, you'll add Docker support now.</span></span> <span data-ttu-id="f2622-134">Klicken Sie also mit der rechten Maustaste im Projektmappen-Explorer auf den Projektknoten, und wählen Sie im Kontextmenü **Hinzufügen** > **Docker-Unterstützung** aus.</span><span class="sxs-lookup"><span data-stu-id="f2622-134">So right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Kontextmenüoption zum Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt: Klicken Sie mit der rechten Maustaste (im Projekt) auf „Hinzufügen > Docker-Unterstützung“.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

<span data-ttu-id="f2622-136">**Abbildung 4–38**.</span><span class="sxs-lookup"><span data-stu-id="f2622-136">**Figure 4-38**.</span></span> <span data-ttu-id="f2622-137">Hinzufügen von Docker-Unterstützung zu einem vorhandenen Projekt</span><span class="sxs-lookup"><span data-stu-id="f2622-137">Adding Docker support to an existing project</span></span>

<span data-ttu-id="f2622-138">Um das Hinzufügen von Docker-Unterstützung abzuschließen, können Sie Windows oder Linux auswählen.</span><span class="sxs-lookup"><span data-stu-id="f2622-138">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="f2622-139">Wählen Sie in diesem Fall **Linux** aus.</span><span class="sxs-lookup"><span data-stu-id="f2622-139">In this case, select **Linux**.</span></span>

![Optionsdialogfeld für die Auswahl des Betriebssystems für Dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

<span data-ttu-id="f2622-141">**Abbildung 4–39**.</span><span class="sxs-lookup"><span data-stu-id="f2622-141">**Figure 4-39**.</span></span> <span data-ttu-id="f2622-142">Auswählen von Linux-Containern.</span><span class="sxs-lookup"><span data-stu-id="f2622-142">Selecting Linux containers.</span></span>

<span data-ttu-id="f2622-143">Durch diese einfachen Schritte haben Sie festgelegt, dass Ihre ASP.NET Core 5.0-Anwendung in einem Linux-Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2622-143">With these simple steps, you have your ASP.NET Core 5.0 application running on a Linux container.</span></span>

<span data-ttu-id="f2622-144">In ähnlicher Weise können Sie auch ein sehr einfaches **WebApp**-Projekt (Abbildung 4-40) hinzufügen, um den Web-API-Endpunkt zu nutzen, auch wenn die Details hier nicht behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f2622-144">In a similar way, you can also add a very simple **WebApp** project (Figure 4-40) to consume the web API endpoint, although the details are not discussed here.</span></span>

<span data-ttu-id="f2622-145">Danach fügen Sie Orchestratorunterstützung für Ihr **WebApi**-Projekt hinzu, wie im Folgenden in Abbildung 4-40 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f2622-145">After that, you add orchestrator support for your **WebApi** project as shown next, in image 4-40.</span></span>

![Hinzufügen von Orchestratorunterstützung zum WebApi-Projekt](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

<span data-ttu-id="f2622-147">**Abbildung 4–40**.</span><span class="sxs-lookup"><span data-stu-id="f2622-147">**Figure 4-40**.</span></span> <span data-ttu-id="f2622-148">Hinzufügen von Orchestratorunterstützung zum *WebApi*-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f2622-148">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="f2622-149">Wenn Sie die Option `Docker Compose` auswählen, die für lokale Entwicklung gut geeignet ist, fügt Visual Studio das docker-compose-Projekt mit den docker-compose-Dateien hinzu, wie in Abbildung 4-41 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2622-149">When you choose the `Docker Compose` option, which is fine for local development, Visual Studio adds the docker-compose project, with the docker-compose files as shown in image 4-41.</span></span>

![Docker-compose wurde der Projektmappe hinzugefügt](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

<span data-ttu-id="f2622-151">**Abbildung 4–41**.</span><span class="sxs-lookup"><span data-stu-id="f2622-151">**Figure 4-41**.</span></span> <span data-ttu-id="f2622-152">Hinzufügen von Orchestratorunterstützung zum *WebApi*-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f2622-152">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="f2622-153">Die ersten hinzugefügten Dateien ähneln den folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="f2622-153">The initial files added are similar to these ones:</span></span>

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

<span data-ttu-id="f2622-154">Damit Sie die App mit Docker Compose ausführen können, müssen Sie nur einige Anpassungen an `docker-compose.override.yml` vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f2622-154">To have you app running with Docker Compose you just have to make a few tweaks to `docker-compose.override.yml`</span></span>

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

<span data-ttu-id="f2622-155">Jetzt können Sie Ihre Anwendung mit der Taste **F5** oder mit der Schaltfläche **Wiedergabe** oder der Tastenkombination **STRG+F5** ausführen und das docker-compose-Projekt auswählen (Abbildung 4-42).</span><span class="sxs-lookup"><span data-stu-id="f2622-155">Now you can run your application with the **F5** key, or by using the **Play** button, or the **Ctrl+F5** key, selecting the docker-compose project, as shown in image 4-42.</span></span>

![Ausführen des docker-compose-Projekts mit Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

<span data-ttu-id="f2622-157">**Abbildung 4–42**.</span><span class="sxs-lookup"><span data-stu-id="f2622-157">**Figure 4-42**.</span></span> <span data-ttu-id="f2622-158">Hinzufügen von Orchestratorunterstützung zum *WebApi*-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f2622-158">Adding orchestrator support to *WebApi* project.</span></span>

<span data-ttu-id="f2622-159">Wenn Sie die Anwendung „docker-vompose“ wie beschrieben ausführen, erhalten Sie folgendes Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="f2622-159">When running the docker-compose application as explained, you get:</span></span>

1. <span data-ttu-id="f2622-160">Die gemäß der docker-compose-Datei erstellten Images und Container.</span><span class="sxs-lookup"><span data-stu-id="f2622-160">The images built and containers created as per the docker-compose file.</span></span>
2. <span data-ttu-id="f2622-161">Öffnen des Browsers in der Adresse, die im Dialogfeld „Eigenschaften“ für das `docker-compose`-Projekt konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f2622-161">The browser open in the address configured in the "Properties" dialog for the `docker-compose` project.</span></span>
3. <span data-ttu-id="f2622-162">Öffnen des Fensters **Container** (in Visual Studio 2019, Version 16.4 oder höher).</span><span class="sxs-lookup"><span data-stu-id="f2622-162">The **Container** window open (in Visual Studio 2019 version 16.4 and later).</span></span>
4. <span data-ttu-id="f2622-163">Debuggerunterstützung für alle Projekte in der Projektmappe, wie in den folgenden Abbildungen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2622-163">Debugger support for all projects in the solution, as shown in the following images.</span></span>

<span data-ttu-id="f2622-164">Geöffneter Browser:</span><span class="sxs-lookup"><span data-stu-id="f2622-164">Browser opened:</span></span>

![Browseransicht mit ausgeführter Web-App](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

<span data-ttu-id="f2622-166">**Abbildung 4–43**.</span><span class="sxs-lookup"><span data-stu-id="f2622-166">**Figure 4-43**.</span></span> <span data-ttu-id="f2622-167">Browserfenster, in dem eine Anwendung für mehrere Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2622-167">Browser window with an application running on multiple containers.</span></span>

<span data-ttu-id="f2622-168">Fenster „Container“:</span><span class="sxs-lookup"><span data-stu-id="f2622-168">Containers window:</span></span>

![Visual Studio-Fenster „Container“](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

<span data-ttu-id="f2622-170">**Abbildung 4–44**.</span><span class="sxs-lookup"><span data-stu-id="f2622-170">**Figure 4-44**.</span></span> <span data-ttu-id="f2622-171">Visual Studio-Fenster „Container“</span><span class="sxs-lookup"><span data-stu-id="f2622-171">Visual Studio "Containers" window</span></span>

<span data-ttu-id="f2622-172">Über das Fenster **Container** können Sie ausgeführte Container, Umgebungsvariablen, Protokolle und Portzuordnungen anzeigen, verfügbare Images durchsuchen, das Dateisystem untersuchen, einen Debugger anfügen oder ein Terminalfenster in der Containerumgebung öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2622-172">The **Containers** window lets you view running containers, browse available images, view environment variables, logs, and port mappings, inspect the filesystem, attach a debugger, or open a terminal window inside the container environment.</span></span>

<span data-ttu-id="f2622-173">Wie Sie sehen können, ist die Integration von Visual Studio 2019 und Docker völlig auf die Produktivität des Entwicklers ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="f2622-173">As you can see, the integration between Visual Studio 2019 and Docker is completely oriented to the developer's productivity.</span></span>

<span data-ttu-id="f2622-174">Natürlich können Sie die Images auch mit dem Befehl `docker images` auflisten.</span><span class="sxs-lookup"><span data-stu-id="f2622-174">Of course, you can also list the images using the `docker images` command.</span></span> <span data-ttu-id="f2622-175">Sie sollten die Images `webapi` und `webapp` mit den `dev`-Tags sehen, die von der automatischen Bereitstellung Ihres Projekts mit Visual Studio 2019 erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f2622-175">You should see the `webapi` and `webapp` images with the `dev` tags created by the automatic deployment of our project with Visual Studio 2019.</span></span>

```console
docker images
```

![Konsolenausgabe des docker images-Befehls, eine Liste mit diesem Inhalt: Repository, Tag, Image-ID, Erstellungsdatum und Größe.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

<span data-ttu-id="f2622-177">**Abbildung 4–45**.</span><span class="sxs-lookup"><span data-stu-id="f2622-177">**Figure 4-45**.</span></span> <span data-ttu-id="f2622-178">Ansicht von Docker-Images</span><span class="sxs-lookup"><span data-stu-id="f2622-178">View of Docker images</span></span>

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a><span data-ttu-id="f2622-179">Registrieren der Projektmappe in einer Azure Container Registry (ACR)</span><span class="sxs-lookup"><span data-stu-id="f2622-179">Register the Solution in an Azure Container Registry (ACR)</span></span>

<span data-ttu-id="f2622-180">Sie können die Images in [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) hochladen, aber Sie können auch Docker Hub oder eine andere Registrierung verwenden, sodass die Images aus dieser Registrierung im AKS-Cluster bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f2622-180">You can upload the images to the [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), but you could also use Docker Hub or any other registry, so the images can be deployed to the AKS cluster from that registry.</span></span>

### <a name="create-an-acr-instance"></a><span data-ttu-id="f2622-181">Erstellen einer ACR-Instanz</span><span class="sxs-lookup"><span data-stu-id="f2622-181">Create an ACR instance</span></span>

<span data-ttu-id="f2622-182">Führen Sie den folgenden Befehl mit **az cli** aus:</span><span class="sxs-lookup"><span data-stu-id="f2622-182">Run the following command from the **az cli**:</span></span>

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> <span data-ttu-id="f2622-183">Der Containerregistrierungsname (z. B. `exploredocker`) muss innerhalb von Azure eindeutig sein und zwischen 5 und 50 alphanumerische Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f2622-183">The container registry name (e.g `exploredocker`) must be unique within Azure, and contain 5-50 alphanumeric characters.</span></span> <span data-ttu-id="f2622-184">Weitere Informationen finden Sie unter [Erstellen einer Containerregistrierung](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry).</span><span class="sxs-lookup"><span data-stu-id="f2622-184">For more details, refer [Create a container registry](/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="f2622-185">Erstellen des Images im Releasemodus</span><span class="sxs-lookup"><span data-stu-id="f2622-185">Create the image in Release mode</span></span>

<span data-ttu-id="f2622-186">Sie erstellen jetzt das Image im **Releasemodus** (für die Produktion bereit), indem Sie zu **Release** wechseln, wie in Abbildung 4–46 dargestellt, und die Anwendung ausführen wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="f2622-186">You'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-46, and running the application as you did before.</span></span>

![Symbolleistenoption in Visual Studio zum Erstellen im Releasemodus.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

<span data-ttu-id="f2622-188">**Abbildung 4–46**.</span><span class="sxs-lookup"><span data-stu-id="f2622-188">**Figure 4-46**.</span></span> <span data-ttu-id="f2622-189">Auswählen des Releasemodus</span><span class="sxs-lookup"><span data-stu-id="f2622-189">Selecting Release Mode</span></span>

<span data-ttu-id="f2622-190">Wenn Sie den Befehl `docker images` ausführen, sehen Sie, dass beide Images erstellt werden, ein Image für den `debug`- (**Entwicklung**) und ein weiteres für den `release`-Modus (**neuestes Image**).</span><span class="sxs-lookup"><span data-stu-id="f2622-190">If you execute the `docker images` command, you'll see both images created, one for `debug` (**dev**) and the other for `release` (**latest**) mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="f2622-191">Erstellen eines neuen Tags für das Image</span><span class="sxs-lookup"><span data-stu-id="f2622-191">Create a new Tag for the Image</span></span>

<span data-ttu-id="f2622-192">Jedes Containerimage muss mit dem `loginServer`-Namen der Registrierung gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f2622-192">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="f2622-193">Dieses Tag wird beim Übertragen von Containerimages per Push in eine Imageregistrierung für das Routing verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2622-193">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="f2622-194">Sie können den Namen des `loginServer` im Azure-Portal anzeigen, indem Sie die Informationen aus der Azure Container Registry übernehmen.</span><span class="sxs-lookup"><span data-stu-id="f2622-194">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Browseransicht des Namens in der Azure Container Registry rechts oben.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

<span data-ttu-id="f2622-196">**Abbildung 4–47**.</span><span class="sxs-lookup"><span data-stu-id="f2622-196">**Figure 4-47**.</span></span> <span data-ttu-id="f2622-197">Ansicht des Namens der Registry</span><span class="sxs-lookup"><span data-stu-id="f2622-197">View of the name of the Registry</span></span>

<span data-ttu-id="f2622-198">Alternativ können Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="f2622-198">Or by running the following command:</span></span>

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Konsolenausgabe des Befehls oben.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

<span data-ttu-id="f2622-200">**Abbildung 4–48**.</span><span class="sxs-lookup"><span data-stu-id="f2622-200">**Figure 4-48**.</span></span> <span data-ttu-id="f2622-201">Abrufen des Namens der Registrierung mit **az cli**</span><span class="sxs-lookup"><span data-stu-id="f2622-201">Get the name of the registry using **az cli**</span></span>

<span data-ttu-id="f2622-202">In beiden Fällen erhalten Sie den Namen.</span><span class="sxs-lookup"><span data-stu-id="f2622-202">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="f2622-203">In unserem Beispiel `exploredocker.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="f2622-203">In our example, `exploredocker.azurecr.io`.</span></span>

<span data-ttu-id="f2622-204">Jetzt können Sie das Image mit einem Tag kennzeichnen, indem Sie für das aktuellste Image (das Releaseimage) diesen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="f2622-204">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

<span data-ttu-id="f2622-205">Nach dem Ausführen des `docker tag`-Befehls können Sie die Images mit dem Befehl `docker images` auflisten, dann sollten Sie das Image mit dem neuen Tag sehen.</span><span class="sxs-lookup"><span data-stu-id="f2622-205">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Konsolenausgabe des docker images-Befehls.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

<span data-ttu-id="f2622-207">**Abbildung 4–49**.</span><span class="sxs-lookup"><span data-stu-id="f2622-207">**Figure 4-49**.</span></span> <span data-ttu-id="f2622-208">Ansicht von mit Tags gekennzeichneten Images</span><span class="sxs-lookup"><span data-stu-id="f2622-208">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="f2622-209">Pushen des Images in die Azure ACR</span><span class="sxs-lookup"><span data-stu-id="f2622-209">Push the image into the Azure ACR</span></span>

<span data-ttu-id="f2622-210">Melden Sie sich bei der Azure Container Registry an.</span><span class="sxs-lookup"><span data-stu-id="f2622-210">Log in to the Azure Container Registry</span></span>

```console
az acr login --name exploredocker
```

<span data-ttu-id="f2622-211">Übertragen Sie das Image mit dem folgenden Befehl per Push in die Azure ACR:</span><span class="sxs-lookup"><span data-stu-id="f2622-211">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push <login-server-name>/<image-name>:v1
```

<span data-ttu-id="f2622-212">Dieser Befehl benötigt etwas Zeit zum Hochladen von Images, gibt Ihnen aber Feedback zum Verlauf.</span><span class="sxs-lookup"><span data-stu-id="f2622-212">This command takes a while uploading the images but gives you feedback in the process.</span></span> <span data-ttu-id="f2622-213">Auf der folgenden Abbildung sehen Sie, dass die Ausgabe eines Images abgeschlossen wurde und ein weiteres Image in Bearbeitung ist.</span><span class="sxs-lookup"><span data-stu-id="f2622-213">In the following image, you can see the output from one image completed and another in progress.</span></span>

![Konsolenausgabe des docker push-Befehls.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

<span data-ttu-id="f2622-215">**Abbildung 4-50**.</span><span class="sxs-lookup"><span data-stu-id="f2622-215">**Figure 4-50**.</span></span> <span data-ttu-id="f2622-216">Konsolenausgabe des push-Befehls.</span><span class="sxs-lookup"><span data-stu-id="f2622-216">Console output from the push command.</span></span>

<span data-ttu-id="f2622-217">Um Ihre App mit mehreren Containern in Ihrem AKS-Cluster bereitzustellen, benötigen Sie einige `.yaml`-Manifestdateien, deren Eigenschaften größtenteils aus den `docker-compose.yml`- und `docker-compose.override.yml`-Dateien stammen.</span><span class="sxs-lookup"><span data-stu-id="f2622-217">To deploy your multi-container app into your AKS cluster you need some manifest `.yaml` files that have, most of the properties taken from the `docker-compose.yml` and `docker-compose.override.yml` files.</span></span>

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
> <span data-ttu-id="f2622-218">Die vorherigen `.yml`-Dateien aktivieren nur die `HTTP`-Ports mithilfe des Parameters `ASPNETCORE_URLS`, um Probleme mit dem fehlenden Zertifikat in der Beispiel-App zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f2622-218">The previous `.yml` files only enable the `HTTP` ports, using the `ASPNETCORE_URLS` parameter, to avoid issues with the missing certificate in the sample app.</span></span>

> [!TIP]
> <span data-ttu-id="f2622-219">Informationen zum Erstellen des AKS-Clusters für dieses Beispiel finden Sie in Abschnitt [**Bereitstellen für Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) in diesem Handbuch.</span><span class="sxs-lookup"><span data-stu-id="f2622-219">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

<span data-ttu-id="f2622-220">Jetzt sind Sie fast für die Bereitstellung mit **kubectl** bereit. Zunächst müssen Sie jedoch die Anmeldeinformationen aus dem AKS-Cluster mit diesem Befehl abrufen:</span><span class="sxs-lookup"><span data-stu-id="f2622-220">Now you're almost ready to deploy using **kubectl**, but first you must get the credentials from the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Konsolenausgabe des Befehls oben: „explore-docker-aks“ als aktueller Kontext in „C:\Users\Miguel.kube\config“ gemergt](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

<span data-ttu-id="f2622-222">**Abbildung 4-51**.</span><span class="sxs-lookup"><span data-stu-id="f2622-222">**Figure 4-51**.</span></span> <span data-ttu-id="f2622-223">Abrufen von Anmeldeinformationen aus AKS in die kubectl-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f2622-223">Getting credentials from AKS into the kubectl environment.</span></span>

<span data-ttu-id="f2622-224">Sie müssen dem AKS-Cluster außerdem das Pullen von Images aus ACR mithilfe dieses Befehls erlauben:</span><span class="sxs-lookup"><span data-stu-id="f2622-224">You also have to allow the AKS cluster to pull images from the ACR, using this command:</span></span>

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

<span data-ttu-id="f2622-225">Die Ausführung des vorherigen Befehls kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="f2622-225">The previous command might take a couple of minutes to complete.</span></span> <span data-ttu-id="f2622-226">Verwenden Sie dann den Befehl `kubectl apply`, um die Bereitstellungen zu starten, und verwenden Sie anschließend `kubectl get all` get list, um die Clusterobjekte aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="f2622-226">Then, use the `kubectl apply` command to launch the deployments, and then `kubectl get all` get list the cluster objects.</span></span>

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Konsolenausgabe der Befehle oben: Bereitstellungen angewendet.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

<span data-ttu-id="f2622-229">**Abbildung 4-52**.</span><span class="sxs-lookup"><span data-stu-id="f2622-229">**Figure 4-52**.</span></span> <span data-ttu-id="f2622-230">Bereitstellung in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f2622-230">Deployment to Kubernetes</span></span>

<span data-ttu-id="f2622-231">Sie müssen eine Weile warten, bis der Load Balancer die externe IP-Adresse abruft und mit `kubectl get services` prüft. Anschließend sollte die Anwendung unter dieser Adresse verfügbar sein, wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2622-231">You'll have to wait a while until the load balancer gets the external IP, checking with `kubectl get services`, and then the application should be available at that address, as shown in the next image:</span></span>

![Browseransicht der in AKS bereitgestellten Anwendung](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

<span data-ttu-id="f2622-233">**Abbildung 4.53**.</span><span class="sxs-lookup"><span data-stu-id="f2622-233">**Figure 4-53**.</span></span> <span data-ttu-id="f2622-234">Bereitstellung in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f2622-234">Deployment to Kubernetes</span></span>

<span data-ttu-id="f2622-235">Wenn die Bereitstellung abgeschlossen ist, können Sie mit einem lokalen Proxy über einen SSH-Tunnel auf die [Kubernetes-Webbenutzeroberfläche](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f2622-235">When the deployment completes, you can access the [Kubernetes Web UI](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) with a local proxy, using an ssh tunnel.</span></span>

<span data-ttu-id="f2622-236">Zunächst müssen Sie eine ClusterRoleBinding mit dem folgenden Befehl erstellen:</span><span class="sxs-lookup"><span data-stu-id="f2622-236">First you must create a ClusterRoleBinding with the following command:</span></span>

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

<span data-ttu-id="f2622-237">Verwenden Sie dann diesen Befehl, um den Proxy zu starten:</span><span class="sxs-lookup"><span data-stu-id="f2622-237">And then this command to start the proxy:</span></span>

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

<span data-ttu-id="f2622-238">Ein Browserfenster sollte unter `http://127.0.0.1:8001` mit einer Ansicht geöffnet werden, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="f2622-238">A browser window should open at `http://127.0.0.1:8001` with a view similar to this one:</span></span>

![Browseransicht des Kubernetes-Dashboards mit Bereitstellungen, Pods, Replikatsätzen und Diensten.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

<span data-ttu-id="f2622-240">**Abbildung 4-54**.</span><span class="sxs-lookup"><span data-stu-id="f2622-240">**Figure 4-54**.</span></span> <span data-ttu-id="f2622-241">Anzeigen von Kubernetes-Clusterinformationen</span><span class="sxs-lookup"><span data-stu-id="f2622-241">View Kubernetes cluster information</span></span>

<span data-ttu-id="f2622-242">Nun verfügen Sie über Ihre ASP.NET Core Anwendung, die in Linux-Containern ausgeführt und in einem AKS-Cluster in Azure bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f2622-242">Now you have your ASP.NET Core application, running in Linux containers, and deployed to an AKS cluster on Azure.</span></span>

> [!NOTE]
> <span data-ttu-id="f2622-243">Weitere Informationen zur Bereitstellung mit Kubernetes finden Sie unter <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.</span><span class="sxs-lookup"><span data-stu-id="f2622-243">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="f2622-244">[Zurück](set-up-windows-containers-with-powershell.md)
> [Weiter](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="f2622-244">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
