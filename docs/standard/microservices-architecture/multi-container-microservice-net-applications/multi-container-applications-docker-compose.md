---
title: Definieren Ihre Anwendung mit mehreren Container mit Docker compose.yml
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Definieren Ihre Anwendung mit mehreren Container mit Docker compose.yml"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="234f3-104">Definieren Ihre Anwendung mit mehreren Container mit Docker compose.yml</span><span class="sxs-lookup"><span data-stu-id="234f3-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="234f3-105">In diesem Handbuch sind die [Docker compose.yml](https://docs.docker.com/compose/compose-file/) Datei wurde im Abschnitt eingeführt [Schritt 4. Definieren Sie Ihre Dienste in Docker-compose.yml, beim Erstellen einer Docker-Anwendung mit mehreren Container](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="234f3-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="234f3-106">Es gibt jedoch zusätzliche Möglichkeiten, die Docker-compose-Dateien zu verwenden, die noch ausführlicher untersuchen werden.</span><span class="sxs-lookup"><span data-stu-id="234f3-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="234f3-107">Beispielsweise können Sie explizit beschreiben, wie Sie Ihre Anwendung mehrere Container in der Docker-compose.yml-Datei bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="234f3-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="234f3-108">Optional können Sie auch beschreiben, wie Sie möchten Ihre benutzerdefinierten Docker-Images zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="234f3-109">(Custom Docker-Images können auch mit der Docker-Befehlszeilenschnittstelle erstellt werden).</span><span class="sxs-lookup"><span data-stu-id="234f3-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="234f3-110">Im Grunde genommen, definieren Sie jeweils die Container, die Sie bereitstellen möchten, sowie bestimmte Merkmale für jede Bereitstellung Container.</span><span class="sxs-lookup"><span data-stu-id="234f3-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="234f3-111">Nachdem Sie eine Bereitstellung mit mehreren Container-Beschreibungsdatei haben, können Sie die gesamte Projektmappe in einer einzigen Aktion von orchestriert Bereitstellen der [Docker Verfassen Sie](https://docs.docker.com/compose/overview/) CLI-Befehl, oder Sie können die Bereitstellung er transparent in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="234f3-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="234f3-112">Andernfalls müssen Sie den Docker-Befehlszeilenschnittstelle zu verwenden, um die Container-durch-Container in mehreren Schritten, die mithilfe von "Docker run" Befehl über die Befehlszeile bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="234f3-113">Daher muss jeder Dienst in Docker-compose.yml definiert genau ein Bild angeben oder erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="234f3-114">Andere Schlüssel sind optional und werden analog zu ihren "Docker run" Befehlszeile-Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="234f3-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="234f3-115">Die folgende YAML Code ist die Definition einer möglichen globalen aber einzelne Docker-compose.yml-Datei für das eShopOnContainers-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="234f3-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="234f3-116">Dies ist nicht der tatsächliche Docker-compose Datei eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="234f3-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="234f3-117">Stattdessen ist er eine vereinfachte und konsolidierten Version in einer einzelnen Datei, die nicht die beste Möglichkeit zum Arbeiten mit Docker-bilden Dateien, wie weiter unten erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="234f3-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

<span data-ttu-id="234f3-118">In dieser Datei der Stammschlüssel ist Services.</span><span class="sxs-lookup"><span data-stu-id="234f3-118">The root key in this file is services.</span></span> <span data-ttu-id="234f3-119">Unter diesen Schlüssel, die Sie definieren die Dienste, die Sie bereitstellen möchten und führen Sie beim Ausführen der Docker-Befehl oder wenn Sie in Visual Studio bereitstellen mithilfe dieser Datei Docker compose.yml zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="234f3-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="234f3-120">In diesem Fall hat die Docker-compose.yml-Datei mehrere Dienste, die definiert, wie in der folgenden Liste beschrieben.</span><span class="sxs-lookup"><span data-stu-id="234f3-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="234f3-121">Webmvc Container, einschließlich der Nutzung der Microservices von serverseitigen C ASP.NET Core MVC-Anwendung\#</span><span class="sxs-lookup"><span data-stu-id="234f3-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="234f3-122">Catalog.API Container, einschließlich der Microservice Katalog ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="234f3-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="234f3-123">Ordering.API Container, einschließlich der Web-API für ASP.NET Core Sortierung microservice</span><span class="sxs-lookup"><span data-stu-id="234f3-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="234f3-124">SQL.Data Container, die mit SQL Server für Linux, halten die Microservices-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="234f3-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="234f3-125">Basket.API Container mit dem Warenkorb ASP.NET Core-Web-API-microservice</span><span class="sxs-lookup"><span data-stu-id="234f3-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="234f3-126">Basket.Data Container mit den REDIS-Cache-Dienst muss die Warenkorb-Datenbank als eine REDIS-cache</span><span class="sxs-lookup"><span data-stu-id="234f3-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="234f3-127">Ein einfacher Webdienst-API-container</span><span class="sxs-lookup"><span data-stu-id="234f3-127">A simple Web Service API container</span></span>

<span data-ttu-id="234f3-128">Schwerpunkt auf einem einzelnen Container, hat die catalog.api Container-Microservice eine unkomplizierte Definition:</span><span class="sxs-lookup"><span data-stu-id="234f3-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

<span data-ttu-id="234f3-129">Dieser Dienst Datenvolumes hat die folgenden grundlegenden Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="234f3-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="234f3-130">Es basiert auf dem Abbild eines benutzerdefinierten eshop/catalog.api.</span><span class="sxs-lookup"><span data-stu-id="234f3-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="234f3-131">Der Einfachheit halber, es ist keine Build: key-Einstellung in der Datei.</span><span class="sxs-lookup"><span data-stu-id="234f3-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="234f3-132">Dies bedeutet, dass das Bild muss zuvor (mit Docker Build) erstellt wurden, oder (mit dem Befehl "Docker Pull") aus der Registrierung Docker heruntergeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="234f3-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="234f3-133">Es definiert eine Umgebungsvariable mit dem Namen "ConnectionString" mit der Verbindungszeichenfolge von Entity Framework verwendet werden, Zugriff auf die SQL Server-Instanz, die das Datenmodell für den Katalog enthält.</span><span class="sxs-lookup"><span data-stu-id="234f3-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="234f3-134">In diesem Fall wird die gleiche SQL Server-Container mehrere Datenbanken enthalten.</span><span class="sxs-lookup"><span data-stu-id="234f3-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="234f3-135">Aus diesem Grund benötigen Sie weniger Arbeitsspeicher in Ihrem Entwicklungscomputer für Docker ein.</span><span class="sxs-lookup"><span data-stu-id="234f3-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="234f3-136">Allerdings können Sie auch eine SQL Server-Container für jede Datenbank Microservice bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="234f3-137">Der SQL Server-Name ist sql.data, also den gleichen Namen verwendet, die für den Container, der die SQL Server-Instanz für Linux ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="234f3-138">Dies ist zweckmäßig, Diese namensauflösung (intern auf den Docker-Host) verwenden können wird die Netzwerkadresse aufgelöst werden, damit Sie nicht die interne IP-Adresse für den Container zu kennen, die in anderen Containern auf Sie zugreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="234f3-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="234f3-139">Da die Verbindungszeichenfolge durch eine Umgebungsvariable definiert ist, können Sie diese Variable mithilfe eines anderen Mechanismus und zu einem anderen Zeitpunkt festlegen.</span><span class="sxs-lookup"><span data-stu-id="234f3-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="234f3-140">Sie konnten z. B. eine andere Verbindungszeichenfolge festlegen, bei der Bereitstellung bis hin zur Produktion in die endgültige Hosts oder indem Sie es aus der CI-CD-Pipelines in VSTS oder Ihrem bevorzugten DevOps-System.</span><span class="sxs-lookup"><span data-stu-id="234f3-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="234f3-141">Er stellt die Port 80 für den internen Zugriff an den Dienst catalog.api der Docker-Host bereit.</span><span class="sxs-lookup"><span data-stu-id="234f3-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="234f3-142">Der Host ist derzeit eine Linux-VM, da auf einem Docker-Images für Linux basiert, jedoch konnte, konfigurieren Sie den Container auf einem Windows-Abbild stattdessen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="234f3-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="234f3-143">Er leitet die verfügbar gemachten Port 80 für den Container an Port 5101 auf dem Docker-Hostcomputer (Linux-VM).</span><span class="sxs-lookup"><span data-stu-id="234f3-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="234f3-144">Den Webdienst verweist auf der sql.data-Dienst (SQL Server-Instanz für Linux-Datenbank, die in einem Container).</span><span class="sxs-lookup"><span data-stu-id="234f3-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="234f3-145">Bei Angabe dieser Abhängigkeit beginnt catalog.api Container erst, wenn der Container sql.data bereits begonnen wurde; Dies ist wichtig, da catalog.api SQL Server-Datenbank benötigt einrichten und ausgeführten zuerst.</span><span class="sxs-lookup"><span data-stu-id="234f3-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="234f3-146">Jedoch reicht diese Art der Abhängigkeit der Container nicht in vielen Fällen daran, dass nur auf Containerebene Docker überprüft.</span><span class="sxs-lookup"><span data-stu-id="234f3-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="234f3-147">In einigen Fällen der Dienst (in dieser SQL Server mit Groß-/Kleinschreibung) nicht bereit ist, möglicherweise weiterhin daher ist es ratsam, Wiederholungslogik mit exponenzieller Wartezeit in Ihrem Client Microservices implementieren.</span><span class="sxs-lookup"><span data-stu-id="234f3-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="234f3-148">Auf diese Weise ist ein Container für die Abhängigkeit nicht bereit für kurze Zeit, die Anwendung stabil bleiben.</span><span class="sxs-lookup"><span data-stu-id="234f3-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="234f3-149">Für den Zugriff mit externen Servern konfiguriert ist: die zusätzlichen\_Hosts festlegen können Sie den Zugriff auf externe Server oder Computer außerhalb der Docker-Host (d. h. außerhalb der Standardwert eine Entwicklung Docker ist Linux-VM gehostet), wie z. B. eine lokale SQL Server-Instanz auf Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="234f3-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="234f3-150">Es gibt auch andere, erweiterten Docker compose.yml-Einstellungen, die wir in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="234f3-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="234f3-151">Mit Docker-verfassen Dateien auf mehrere Umgebung</span><span class="sxs-lookup"><span data-stu-id="234f3-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="234f3-152">Die Docker-compose.yml Dateien bestehen aus Berichtsdefinitionsdateien und können durch mehrere Infrastrukturen, die diesem Format verstehen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="234f3-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="234f3-153">Das einfachste Tool wird der Docker-Befehl zu erstellen, jedoch andere tools, wie diese Datei auch die Orchestrators (z. B. Docker Containerhostclustern) vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="234f3-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="234f3-154">Aus diesem Grund mithilfe der Docker-verfassen Befehl können Sie die folgenden Hauptszenarien abzielen.</span><span class="sxs-lookup"><span data-stu-id="234f3-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="234f3-155">Entwicklungsumgebungen</span><span class="sxs-lookup"><span data-stu-id="234f3-155">Development environments</span></span>

<span data-ttu-id="234f3-156">Wenn Sie Anwendungen entwickeln, ist es wichtig, um eine Anwendung in einer isolierten Entwicklungsumgebung ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="234f3-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="234f3-157">Sie können die CLI-Befehl zum Erstellen der Umgebung oder verwenden Visual Studio die Verwendungsmöglichkeiten Docker-grundlegend verfassen Docker zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="234f3-158">Der Docker-compose.yml-Datei können Sie zum Konfigurieren und alle Ihre Anwendung dienstabhängigkeiten (andere Dienste, Cache, Datenbanken, Warteschlangen usw.) zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="234f3-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="234f3-159">Mithilfe der CLI-Befehl Docker zu erstellen, können Sie erstellen und starten Sie einen oder mehrere Container für jede Abhängigkeit mit einem einzigen Befehl (Docker-verfassen oben).</span><span class="sxs-lookup"><span data-stu-id="234f3-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="234f3-160">Docker-compose.yml Dateien sind Konfigurationsdateien, die durch Docker-Modul interpretiert zu werden, aber auch als einfache Dokumentationsdateien über die Zusammensetzung der Anwendung mit mehreren Container dienen.</span><span class="sxs-lookup"><span data-stu-id="234f3-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="234f3-161">Testumgebungen</span><span class="sxs-lookup"><span data-stu-id="234f3-161">Testing environments</span></span>

<span data-ttu-id="234f3-162">Ein wichtiger Teil eines dauerhaften Bereitstellung (CD) oder fortlaufende Integration (CI) Prozess werden die Komponententests und Integrationstests erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="234f3-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="234f3-163">Diese automatisierten Tests erfordern eine isolierte Umgebung, damit sie nicht durch die Benutzer oder jede andere Änderung in die Anwendung Daten eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="234f3-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="234f3-164">Sie können mit Docker Compose erstellen und zerstören, isolierten Umgebung sehr einfach in wenigen Befehle von der Eingabeaufforderung oder Skripts, z. B. die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="234f3-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="234f3-165">Produktionsbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="234f3-165">Production deployments</span></span>

<span data-ttu-id="234f3-166">Sie können auch verfassen zur Bereitstellung auf einem remote-Docker-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="234f3-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="234f3-167">Ein typischer Fall für eine einzelne Instanz des Docker-Host bereitgestellt ist (z. B. einer Produktions-VM oder einem Server bereitgestellt, mit [Docker-Computer](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="234f3-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="234f3-168">Aber unter Umständen liegen auch eine gesamte [Docker Containerhostclustern](https://docs.docker.com/swarm/overview/) -cluster, da Cluster auch mit der Docker-compose.yml-Dateien kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="234f3-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="234f3-169">Wenn Sie andere Orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes usw.) verwenden, müssen Sie Setup und Metadaten Konfigurationseinstellungen wie diejenigen in Docker-compose.yml, aber in der von den anderen Orchestrator erforderlichen Format hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="234f3-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="234f3-170">In jedem Fall Docker-verfassen gängiges Format Tool und die Metadaten für Entwicklungs-, Test- und Produktionszwecke Workflows ist, auch wenn die Produktions-Workflow auf die Orchestrator stark variieren können Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="234f3-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="234f3-171">Verwenden mehrerer Docker-bilden Dateien, um mehrere Umgebungen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="234f3-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="234f3-172">Wenn Sie unterschiedliche Umgebungen verwenden zu können, sollten Sie verwenden Sie mehrere Dateien zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="234f3-173">Dies können Sie mehrere Konfigurationsvarianten abhängig von der Umgebung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="234f3-174">Überschreiben die Basis Docker-compose-Datei</span><span class="sxs-lookup"><span data-stu-id="234f3-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="234f3-175">Sie können eine einzelne Docker-compose.yml-Datei wie in den vereinfachten Beispielen, die in vorherigen Abschnitten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="234f3-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="234f3-176">Allerdings wird, nicht für die meisten Anwendungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="234f3-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="234f3-177">Standardmäßig liest verfassen, zwei Dateien, ein Docker-compose.yml und eine optionale Docker-compose.override.yml-Datei.</span><span class="sxs-lookup"><span data-stu-id="234f3-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="234f3-178">Wie in Abbildung 8 bis 11 dargestellt, wenn Sie Visual Studio verwenden, und Aktivieren der Unterstützung für Docker, Visual Studio auch erstellt diese Dateien und einige zusätzliche Dateien, die zum Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="234f3-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates those files plus some additional files used for debugging.</span></span>

![](./media/image12.png)

<span data-ttu-id="234f3-179">**Abbildung 8 bis 11**.</span><span class="sxs-lookup"><span data-stu-id="234f3-179">**Figure 8-11**.</span></span> <span data-ttu-id="234f3-180">Dateien in Visual Studio 2017 Docker zu erstellen</span><span class="sxs-lookup"><span data-stu-id="234f3-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="234f3-181">Sie können die Docker-compose-Dateien mit einem beliebigen Editor, z. B. Visual Studio Code oder Sublime, bearbeiten und Ausführen der Anwendung mit der Docker verfassen Befehl oben.</span><span class="sxs-lookup"><span data-stu-id="234f3-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="234f3-182">Gemäß der Konvention werden die Docker-compose.yml-Datei enthält, der Basiskonfiguration und andere Einstellungen für statischen.</span><span class="sxs-lookup"><span data-stu-id="234f3-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="234f3-183">Das bedeutet, dass es sich bei die Dienstkonfiguration abhängig von der bereitstellungsumgebung Ihrer Zielgruppe, nicht ändern sollten.</span><span class="sxs-lookup"><span data-stu-id="234f3-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="234f3-184">Die Docker-compose.override.yml-Datei, enthält wie der Name andeutet, Konfigurationseinstellungen, die von der Basisklasse der Konfigurationselemente, z. B. Konfiguration außer Kraft setzen, von die die bereitstellungsumgebung abhängt.</span><span class="sxs-lookup"><span data-stu-id="234f3-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="234f3-185">Sie können auch mehrere Außerkraftsetzung-Dateien mit unterschiedlichen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="234f3-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="234f3-186">Die Außerkraftsetzung-Dateien enthalten in der Regel zusätzlichen Informationen, die von der Anwendung jedoch bestimmte in einer Umgebung oder auf eine Bereitstellung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="234f3-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="234f3-187">Umgebungen mit mehreren abzielt</span><span class="sxs-lookup"><span data-stu-id="234f3-187">Targeting multiple environments</span></span>

<span data-ttu-id="234f3-188">Ein typischer Anwendungsfall ist beim Definieren von mehreren bilden Dateien, damit Sie mehrere Umgebungen, z. B. Produktion abzielen können, staging, CI oder Entwicklungsmethode.</span><span class="sxs-lookup"><span data-stu-id="234f3-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="234f3-189">Um diese Unterschiede zu unterstützen, können Sie Ihre Konfiguration verfassen in mehrere Dateien aufteilen, wie in Abbildung 8 – 12 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="234f3-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="234f3-190">**Abbildung 8 – 12**.</span><span class="sxs-lookup"><span data-stu-id="234f3-190">**Figure 8-12**.</span></span> <span data-ttu-id="234f3-191">Mehrere Docker-bilden Dateien, die Werte in der Basisklasse Docker-compose.yml Datei überschreiben</span><span class="sxs-lookup"><span data-stu-id="234f3-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="234f3-192">Beginnen Sie mit der Basis Docker-compose.yml-Datei.</span><span class="sxs-lookup"><span data-stu-id="234f3-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="234f3-193">Diese Basis-Datei muss die Basistabelle oder statische Konfigurationseinstellungen enthält, die abhängig von der Umgebung nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="234f3-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="234f3-194">Die eShopOnContainers hat beispielsweise die folgende Docker-compose.yml-Datei als die Basisdatei.</span><span class="sxs-lookup"><span data-stu-id="234f3-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

<span data-ttu-id="234f3-195">Die Werte in der Datei Basis Docker-compose.yml sollten aufgrund bereitstellungsumgebungen anderes Ziel nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="234f3-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="234f3-196">Wenn Sie auf die Dienstdefinition Webmvc zu konzentrieren, für die Instanz, sehen Sie wie diese Informationen nahezu identisch, unabhängig davon, welche Umgebung ist, den Sie als Ziel sein können.</span><span class="sxs-lookup"><span data-stu-id="234f3-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="234f3-197">Sie haben die folgende Informationen:</span><span class="sxs-lookup"><span data-stu-id="234f3-197">You have the following information:</span></span>

-   <span data-ttu-id="234f3-198">Der Dienstname: Webmvc.</span><span class="sxs-lookup"><span data-stu-id="234f3-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="234f3-199">Benutzerdefiniertes Image des Containers: Shopping/Webmvc.</span><span class="sxs-lookup"><span data-stu-id="234f3-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="234f3-200">Der Befehl zum Erstellen der benutzerdefinierten Docker-Images, der angibt, welche dockerfile-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="234f3-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="234f3-201">Abhängigkeiten von anderen Diensten, damit dieser Container nicht gestartet wird, bis der andere Abhängigkeit Container gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="234f3-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="234f3-202">Es können zusätzliche Konfigurationsschritte, aber der wichtige Punkt ist, dass in der Datei Basis Docker-compose.yml Sie nur die Informationen festlegen möchten, die über Umgebungen hinweg gemeinsam ist.</span><span class="sxs-lookup"><span data-stu-id="234f3-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="234f3-203">Klicken Sie dann sollten Sie in der Docker-compose.override.yml oder ähnliche Dateien für die Produktion oder Staging, Konfiguration platzieren, die für jede Umgebung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="234f3-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="234f3-204">In der Regel wird der Docker-compose.override.yml für Ihre Entwicklungsumgebung, wie im folgenden Beispiel aus eShopOnContainers verwendet:</span><span class="sxs-lookup"><span data-stu-id="234f3-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="234f3-205">In diesem Beispiel wird die Entwicklungskonfiguration Außerkraftsetzung macht einige Ports auf dem Host, definiert der Umgebungsvariablen mit Umleiten von URLs und Verbindungszeichenfolgen für die Entwicklungsumgebung angibt.</span><span class="sxs-lookup"><span data-stu-id="234f3-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="234f3-206">Diese Einstellungen sind alle nur für die Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="234f3-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="234f3-207">Beim Ausführen von Docker zusammensetzt (oder starten Sie ihn von Visual Studio), der Befehl liest die Außerkraftsetzungen automatisch, als ob sie beide Dateien zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="234f3-207">When you run docker-compose up (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="234f3-208">Angenommen Sie, Sie eine andere Compose-Datei für die produktionsumgebung mit verschiedenen Konfigurationswerte möchten.</span><span class="sxs-lookup"><span data-stu-id="234f3-208">Suppose that you want another Compose file for the production environment, with different configuration values.</span></span> <span data-ttu-id="234f3-209">Sie können eine andere Außerkraftsetzung-Datei wie folgt erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-209">You can create another override file, like the following.</span></span> <span data-ttu-id="234f3-210">(Diese Datei möglicherweise werden in einem anderen Git-Repository gespeichert oder verwaltet und von einem anderen Team gesichert werden.)</span><span class="sxs-lookup"><span data-stu-id="234f3-210">(This file might be stored in a different Git repo or managed and secured by a different team.)</span></span>

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="234f3-211">Gewusst wie: Bereitstellen mit einer bestimmten Außerkraftsetzung-Datei</span><span class="sxs-lookup"><span data-stu-id="234f3-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="234f3-212">Um mehrere Außerkraftsetzung Dateien oder eine Überschreibung-Datei mit einem anderen Namen zu verwenden, können Sie die Option "-f" mit dem Befehl Docker zu erstellen, und geben Sie die Dateien.</span><span class="sxs-lookup"><span data-stu-id="234f3-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="234f3-213">Verfassen Sie Zusammenführungen-Dateien in der Reihenfolge, die sie in der Befehlszeile angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="234f3-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="234f3-214">Im folgende Beispiel wird gezeigt, wie mit Außerkraftsetzung Dateien bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="234f3-215">Verwenden von Umgebungsvariablen in Docker-zusammenstellen Dateien</span><span class="sxs-lookup"><span data-stu-id="234f3-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="234f3-216">Es ist sinnvoll, insbesondere in produktionsumgebungen, in der Lage, beim Abrufen von Konfigurationsinformationen aus der Umgebungsvariablen, sein, wie es in den vorherigen Beispielen gezeigt haben.</span><span class="sxs-lookup"><span data-stu-id="234f3-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="234f3-217">Sie verweisen eine Umgebungsvariablen in Ihren Docker-compose-Dateien, die mit der Syntax \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="234f3-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="234f3-218">Die folgende Zeile aus einer Datei Docker compose.prod.yml zeigt, wie der Wert einer Umgebungsvariablen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="234f3-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="234f3-219">Umgebungsvariablen werden erstellt und initialisiert Sie verschiedene Möglichkeiten, je nach Ihrer hostumgebung (Linux, Windows, Cloud-Cluster usw..).</span><span class="sxs-lookup"><span data-stu-id="234f3-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="234f3-220">Ist jedoch ein geeigneten Ansatz eine .env-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="234f3-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="234f3-221">Deklarieren von Standard-Umgebungsvariablen in der Datei .env Docker-compose Dateien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="234f3-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="234f3-222">Diese Werte für die Umgebungsvariablen sind die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="234f3-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="234f3-223">Sie können jedoch überschrieben werden durch die Werte, die Sie möglicherweise in den einzelnen Ihrer Umgebungen (Host-BS oder Umgebungsvariablen aus Ihrem Cluster) definiert haben.</span><span class="sxs-lookup"><span data-stu-id="234f3-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="234f3-224">Sie fügen diese .env-Datei in den Ordner, in dem der Docker-verfassen Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="234f3-225">Das folgende Beispiel zeigt eine Datei .env wie die [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) Datei für die Anwendung eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="234f3-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="234f3-226">Verfassen von Docker erwartet, dass jede Zeile in einer Datei .env werden im Format &lt;Variable&gt;=&lt;Wert&gt;.</span><span class="sxs-lookup"><span data-stu-id="234f3-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="234f3-227">Beachten Sie, dass die Werte in der Common Language Runtime-Umgebung immer in der Datei .env definierten Werte überschreiben.</span><span class="sxs-lookup"><span data-stu-id="234f3-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="234f3-228">Auf ähnliche Weise überschreiben die Werte, die über die Befehlszeile Argumente übergeben auch die Standardwerte, die in der Datei .env festgelegt.</span><span class="sxs-lookup"><span data-stu-id="234f3-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="234f3-229">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="234f3-229">Additional resources</span></span>

-   <span data-ttu-id="234f3-230">**Übersicht über Docker verfassen**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="234f3-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="234f3-231">**Mehrere verfassen Dateien**
    [*https://docs.docker.com/compose/extends/\#mehrere verfassen Dateien*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="234f3-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="234f3-232">Erstellen von optimiert ASP.NET Core Docker-images</span><span class="sxs-lookup"><span data-stu-id="234f3-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="234f3-233">Wenn Sie Docker und .NET Core auf Quellen im Internet untersuchen, finden Sie dockerfile-Dateien, die die Einfachheit der Erstellung eines Images von Docker durch Kopieren von Quellcode in einen Container zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="234f3-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="234f3-234">In diesen Beispielen wird empfohlen, eine einfache Konfiguration, ein Docker Bild mit der Umgebung, die mit der Anwendung verpackt verfügen können.</span><span class="sxs-lookup"><span data-stu-id="234f3-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="234f3-235">Das folgende Beispiel zeigt einen einfachen dockerfile-Datei in diesem Vein.</span><span class="sxs-lookup"><span data-stu-id="234f3-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="234f3-236">Eine dockerfile-Datei wie folgt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="234f3-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="234f3-237">Sie können jedoch im Wesentlichen der Bilder, insbesondere der Produktions-Bilder optimieren.</span><span class="sxs-lookup"><span data-stu-id="234f3-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="234f3-238">In den Container und Microservices Modell beginnen Sie ständig Container.</span><span class="sxs-lookup"><span data-stu-id="234f3-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="234f3-239">Die gewohnte Weise von mithilfe von Containern wird keinen inaktiven Container neu gestartet, da der Container gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="234f3-240">Orchestrators (z. B. Docker Containerhostclustern, Kubernetes, DCOS oder Azure Service Fabric) erstellen Sie einfach neue Instanzen von Bildern.</span><span class="sxs-lookup"><span data-stu-id="234f3-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="234f3-241">Dies bedeutet, dass Sie optimieren, indem Sie das Vorkompilieren von der Anwendung, wenn sie erstellt wird, damit der Prozess Instanziierung schneller werden müssten.</span><span class="sxs-lookup"><span data-stu-id="234f3-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="234f3-242">Wenn der Container gestartet wird, sollte er für die Ausführung bereit.</span><span class="sxs-lookup"><span data-stu-id="234f3-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="234f3-243">Sie sollte nicht wiederherstellen und Kompilieren zur Laufzeit, mithilfe Dotnet wiederherstellen und Dotnet build-Befehle von der CLI-Dotnet, die die in den zahlreichen Blogbeiträgen zu .NET Core und Docker angezeigt.</span><span class="sxs-lookup"><span data-stu-id="234f3-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="234f3-244">Das Team .NET verfügt über wichtige Schritte, um .NET Core und ASP.NET Core stellen ein Framework Container optimiert ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="234f3-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="234f3-245">Ist nicht nur .NET Core eine einfache Framework mit einer geringen speicherbeanspruchung; vom Team konzentriert sich auf die Leistung beim Start und einige optimierte Docker-Images, z. B. erzeugt der [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Bild unter [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), im Vergleich zu normalen [ Microsoft/Dotnet](https://hub.docker.com/r/microsoft/dotnet/) oder [Microsoft/Nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) Bilder.</span><span class="sxs-lookup"><span data-stu-id="234f3-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="234f3-246">Die [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Grafik automatische Aspnetcore-Einstellung\_Urls für den Port 80 und Cache vor Ngend von Assemblys aus; beide Einstellungen dazu führen, den Start zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="234f3-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="234f3-247">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="234f3-247">Additional resources</span></span>

-   <span data-ttu-id="234f3-248">**Erstellen von optimiert Docker-Images mit ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="234f3-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="234f3-249">Erstellen der Anwendung aus einem Build (CI)-container</span><span class="sxs-lookup"><span data-stu-id="234f3-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="234f3-250">Ein weiterer Vorteil der Docker ist, dass Sie die Anwendung aus einem vorkonfigurierten Container erstellen können, wie in Abbildung 8 bis 13 gezeigt werden, damit Sie nicht benötigen, um einen Buildcomputer oder VM zur Erstellung der Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="234f3-251">Sie können verwenden oder diesen Build-Container testen, indem Sie es auf Ihrem Entwicklungscomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="234f3-252">Doch interessanteres ist, dass Sie den gleichen Build-Container aus der Pipeline CI (Continuous Integration) verwenden können.</span><span class="sxs-lookup"><span data-stu-id="234f3-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="234f3-253">**Abbildung 8 bis 13**.</span><span class="sxs-lookup"><span data-stu-id="234f3-253">**Figure 8-13**.</span></span> <span data-ttu-id="234f3-254">Komponenten, die .NET Bits aus einem Container erstellen</span><span class="sxs-lookup"><span data-stu-id="234f3-254">Components building .NET bits from a container</span></span>

<span data-ttu-id="234f3-255">Geben Sie in diesem Szenario wird die [Microsoft/Aspnetcore-Build](https://hub.docker.com/r/microsoft/aspnetcore-build/) Image, das Sie zum Kompilieren und erstellen Ihre ASP.NET Core apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="234f3-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="234f3-256">Die Ausgabe befindet sich in einem Bild auf der Grundlage der [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Image, das eine optimierte Common Language Runtime-Image, wie bereits erwähnt ist.</span><span class="sxs-lookup"><span data-stu-id="234f3-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="234f3-257">Aspnetcore-buildabbild enthält alles, was Sie benötigen, um das Kompilieren einer ASP.NET Core-Anwendung, einschließlich .NET Core, die ASP.NET SDK, Npm, Bower, Gulp usw..</span><span class="sxs-lookup"><span data-stu-id="234f3-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="234f3-258">Wir benötigen diese Abhängigkeiten zur Buildzeit.</span><span class="sxs-lookup"><span data-stu-id="234f3-258">We need these dependencies at build time.</span></span> <span data-ttu-id="234f3-259">Wir nicht möchten, jedoch mit der Anwendung zur Laufzeit ausführen, da sie das Bild unnötig große machen würden.</span><span class="sxs-lookup"><span data-stu-id="234f3-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="234f3-260">In der Anwendung eShopOnContainers erstellen Sie die Anwendung aus einem Container, indem Sie nur Ausführen folgender Docker-verfassen Befehl.</span><span class="sxs-lookup"><span data-stu-id="234f3-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="234f3-261">Abbildung 8 – 14 zeigt diesen Befehl an der Befehlszeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="234f3-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="234f3-262">**Abbildung 8 – 14.**</span><span class="sxs-lookup"><span data-stu-id="234f3-262">**Figure 8-14.**</span></span> <span data-ttu-id="234f3-263">Erstellen der Anwendung .NET aus einem container</span><span class="sxs-lookup"><span data-stu-id="234f3-263">Building your .NET application from a container</span></span>

<span data-ttu-id="234f3-264">Wie Sie sehen können, ist der Container, der ausgeführt wird, wird der Ci-Build\_1 Container.</span><span class="sxs-lookup"><span data-stu-id="234f3-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="234f3-265">Dies basiert auf der Aspnetcore buildabbild, damit sie kompilieren und die gesamte Anwendung aus innerhalb dieses Containers statt von Ihrem PC erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="234f3-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="234f3-266">D. h. warum in Wirklichkeit es ist erstellen und Kompilieren die Projekte von .NET Core in Linux – da diesen Container auf die Standard-Docker-Linux-Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="234f3-267">Die [Docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) -Konfigurationsdatei für dieses Abbilds (eShopOnContainers Teil) der folgende Code enthält.</span><span class="sxs-lookup"><span data-stu-id="234f3-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="234f3-268">Beachten Sie, dass Sie einen Build-Container mit Beginn der [Microsoft/Aspnetcore-Build](https://hub.docker.com/r/microsoft/aspnetcore-build/) Bild.</span><span class="sxs-lookup"><span data-stu-id="234f3-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* <span data-ttu-id="234f3-269">Beginnend mit **.NET Core 2.0**, `dotnet restore` Befehl führt automatisch bei der `dotnet publish` -Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="234f3-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="234f3-270">Nachdem der Build-Container ausgeführt wird, die .NET SDK-Dotnet-Wiederherstellung ausführen und Dotnet veröffentlichen Befehle für alle Projekte in der Projektmappe, um die .NET Bits zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="234f3-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="234f3-271">In diesem Fall da eShopOnContainers auch ein SPA basierend auf TypeScript und Angular für den Clientcode verfügt, muss sie außerdem Überprüfen von JavaScript-Abhängigkeiten mit Npm, aber diese Aktion nicht mit dem .NET Bits verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="234f3-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="234f3-272">Die Dotnet Befehl Builds veröffentlichen und die kompilierte Ausgabe im Ordner des Projekts veröffentlicht die... /obj/Docker/Publish-Ordner, wie in Abbildung 8-15 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="234f3-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="234f3-273">**Abbildung 8-15.**</span><span class="sxs-lookup"><span data-stu-id="234f3-273">**Figure 8-15.**</span></span> <span data-ttu-id="234f3-274">Binärdateien, die von der Dotnet generierten veröffentlichen (Befehl)</span><span class="sxs-lookup"><span data-stu-id="234f3-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="234f3-275">Erstellen der Docker-Images von der CLI</span><span class="sxs-lookup"><span data-stu-id="234f3-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="234f3-276">Nachdem die Anwendungsausgabe auf die zugehörigen Ordner (innerhalb eines Projekts) veröffentlicht wurde, besteht der nächste Schritt der Docker-Images zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="234f3-277">Zu diesem Zweck verwenden den Build Docker-compose und Docker-verfassen Befehle, wie in Abbildung 8 bis 16 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="234f3-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="234f3-278">**Abbildung 8-16.**</span><span class="sxs-lookup"><span data-stu-id="234f3-278">**Figure 8-16.**</span></span> <span data-ttu-id="234f3-279">Docker-Images erstellen und Ausführen von den Containern</span><span class="sxs-lookup"><span data-stu-id="234f3-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="234f3-280">In Abbildung 8 bis 17, sehen Sie, wie die Docker-compose befehlsausführung erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="234f3-281">**Abbildung 8 bis 17**.</span><span class="sxs-lookup"><span data-stu-id="234f3-281">**Figure 8-17**.</span></span> <span data-ttu-id="234f3-282">Beim Erstellen der Docker-Images mit Docker-Buildbefehl verfassen</span><span class="sxs-lookup"><span data-stu-id="234f3-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="234f3-283">Der Unterschied zwischen der Docker-compose erstellen und Docker Verfassen Sie Befehle ist, die Docker-Verfassen Sie Builds und startet die Bilder.</span><span class="sxs-lookup"><span data-stu-id="234f3-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="234f3-284">Wenn Sie Visual Studio verwenden, werden all diese Schritte im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="234f3-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="234f3-285">Visual Studio kompiliert Ihre Anwendung .NET, erstellt das Docker-Images und die Container in der Docker-Host bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="234f3-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="234f3-286">Visual Studio bietet zusätzliche Funktionen, z. B. die Fähigkeit, die Container, die in Docker ausgeführt wird, direkt in Visual Studio debuggen.</span><span class="sxs-lookup"><span data-stu-id="234f3-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="234f3-287">Die gesamte Takeway hier besteht darin, dass kann zum Erstellen der Anwendung die gleiche Weise Ihre Pipeline CI-CD sollten erstellt werden – aus einem Container anstatt von einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="234f3-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="234f3-288">Haben Sie die Bilder, die erstellt wurden, dann müssen Sie nur führen Sie den Docker-Images mit Docker-Befehl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="234f3-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="234f3-289">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="234f3-289">Additional resources</span></span>

-   <span data-ttu-id="234f3-290">**Erstellen von Bits von einem Container: Einrichten der eShopOnContainers-Lösung in einer Windows-CLI-Umgebung (Dotnet CLI, Docker-Befehlszeilenschnittstelle und Visual Studio Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-Up-in-a-Windows-CLI-Environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="234f3-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="234f3-291">[Vorherigen] (Data-driven-Crud-microservice.md) [weiter] (Datenbank-Server-container.md)</span><span class="sxs-lookup"><span data-stu-id="234f3-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
