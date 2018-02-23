---
title: Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml
description: ".NET Microservicesarchitektur für .NET-Containeranwendungen | Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4fed5c7ba5c2048d103f22bd2b463c143013280
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="716b8-104">Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="716b8-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="716b8-105">In diesem Leitfaden wurde die Datei [docker-compose.yml](https://docs.docker.com/compose/compose-file/) in Abschnitt [Schritt 4: Definieren Ihrer Dienste beim Erstellen einer Docker-Anwendung mit mehreren Containern in docker-compose.yml](#step4_define_svcs_in_docker_compose_yml) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="716b8-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="716b8-106">Es gibt jedoch weitere Möglichkeiten, die docker-compose-Dateien zu verwenden, ausführlicherer betrachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="716b8-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="716b8-107">Beispielsweise können Sie explizit beschreiben, wie Sie Ihre Anwendung mit mehreren Containern in der docker-compose.yml-Datei bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="716b8-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="716b8-108">Optional können Sie auch beschreiben, wie Sie Ihre benutzerdefinierten Docker-Images erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="716b8-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="716b8-109">(Benutzerdefinierte Docker-Images können ebenso mit der Docker-CLI erstellt werden.)</span><span class="sxs-lookup"><span data-stu-id="716b8-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="716b8-110">Im Grunde genommen definieren Sie jeden der Container, den Sie bereitstellen möchten, und dazu noch bestimmte Eigenschaften für jede Containerbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="716b8-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="716b8-111">Sobald Sie über eine Datei mit der Beschreibung der Bereitstellung von mehreren Containern verfügen, können Sie die gesamte Projektmappe in einer einzelnen Aktion, die von dem CLI-Befehl [docker-compose up](https://docs.docker.com/compose/overview/) orchestriert wird, bereitstellen, oder Sie können diese transparent von Visual Studio bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="716b8-112">Andernfalls müssen Sie die Docker-CLI verwenden, um die Container nacheinander in mehreren Schritten bereitzustellen, indem Sie den Befehl „docker run“ über die Befehlszeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="716b8-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="716b8-113">Daher muss jeder in der Datei „docker-compose.yml“ definierte Dienst genau ein Image oder einen Build definieren.</span><span class="sxs-lookup"><span data-stu-id="716b8-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="716b8-114">Andere Schlüssel sind optional und analog zu ihren Gegenstücken von „docker run“ aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="716b8-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="716b8-115">Der folgende YAML-Code ist die Definition einer möglichen globalen aber einzelnen docker-compose.yml-Datei für das eShopOnContainers-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="716b8-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="716b8-116">Dies ist nicht die tatsächliche docker-compose-Datei von eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="716b8-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="716b8-117">Stattdessen handelt es sich um eine vereinfachte und konsolidierte Version in einer einzelnen Datei, die zum Arbeiten mit docker-compose-Datei nicht die beste Lösung ist. Dies wird im Verlauf des Artikels erläutert.</span><span class="sxs-lookup"><span data-stu-id="716b8-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

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

<span data-ttu-id="716b8-118">Der Stammschlüssel in dieser Datei ist „services“.</span><span class="sxs-lookup"><span data-stu-id="716b8-118">The root key in this file is services.</span></span> <span data-ttu-id="716b8-119">Unter diesem Schlüssel definieren Sie die Dienste, die Sie bereitstellen und ausführen möchten, wenn Sie den Befehl „docker-compose up“ ausführen, oder wenn Sie von Visual Studio aus mithilfe dieser docker-compose.yml-Datei bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="716b8-120">In diesem Fall sind wie in der folgenden Liste beschrieben mehrere Dienste für die docker-compose.yml-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="716b8-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="716b8-121">webmvc-Container, einschließlich der ASP.NET Core-MVC-Anwendung, die die Microservices der serverseitigen Programmiersprache C\# verwendet</span><span class="sxs-lookup"><span data-stu-id="716b8-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="716b8-122">catalog.api-Container, einschließlich dem Katalogmicroservice für die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="716b8-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="716b8-123">ordering.api-Container, einschließlich dem Microservice für Bestellungen für die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="716b8-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="716b8-124">sql.data-Container unter SQL Server für Linux, einschließlich der Microservicesdatenbanken</span><span class="sxs-lookup"><span data-stu-id="716b8-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="716b8-125">basket.api-Container mit dem Microservice von ASP.NET Core-Web-API für Basket</span><span class="sxs-lookup"><span data-stu-id="716b8-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="716b8-126">basket.data-Container unter dem REDIS-Cachedienst mit der basket-Datenbank als REDIS-Cache</span><span class="sxs-lookup"><span data-stu-id="716b8-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="716b8-127">Ein einfacher Container für die Webdienst-API</span><span class="sxs-lookup"><span data-stu-id="716b8-127">A simple Web Service API container</span></span>

<span data-ttu-id="716b8-128">Der Containermicroservice „catalog.api“ hat mit Fokus auf einen einzelnen Container eine klare Definition:</span><span class="sxs-lookup"><span data-stu-id="716b8-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

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

<span data-ttu-id="716b8-129">Dieser Containerdienst verfügt über die folgende grundlegende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="716b8-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="716b8-130">Er basiert auf dem benutzerdefinierten „eshop/catalog.api“-Image.</span><span class="sxs-lookup"><span data-stu-id="716b8-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="716b8-131">Der Einfachheit halber gibt es keine „build: key“-Einstellung in der Datei.</span><span class="sxs-lookup"><span data-stu-id="716b8-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="716b8-132">Das bedeutet, dass das Image zuvor erstellt worden (mit „docker build“) oder aus einer beliebigen Docker-Registrierung heruntergeladen sein muss (mit dem docker pull-Befehl).</span><span class="sxs-lookup"><span data-stu-id="716b8-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="716b8-133">Er definiert die Umgebungsvariable mit der Bezeichnung „ConnectionString“ mit der Verbindungszeichenfolge, die von Entity Framework für den Zugriff auf die SQL Server-Instanz, die das Katalogdatenmodell enthält, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="716b8-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="716b8-134">In diesem Fall enthält der gleicher SQL Server-Container mehrere Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="716b8-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="716b8-135">Aus diesem Grund benötigen Sie weniger Arbeitsspeicher in Ihrem Entwicklungscomputer für Docker.</span><span class="sxs-lookup"><span data-stu-id="716b8-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="716b8-136">Allerdings können Sie auch einen SQL Server-Container für jede Microservicedatenbank bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="716b8-137">Der SQL Server-Name lautet „sql.data“. Dies ist derselbe Name, der für den Container verwendet wird, der die SQL Server-Instanz für Linux ausführt.</span><span class="sxs-lookup"><span data-stu-id="716b8-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="716b8-138">Das ist wirklich praktisch, denn die Möglichkeit, diese Namensauflösung (intern für den Docker-Host) zu verwenden, löst die Netzwerkadresse auf. Sie müssen die interne IP-Adresse für die Container also nicht kennen, auf die Sie von anderen Container aus zugreifen.</span><span class="sxs-lookup"><span data-stu-id="716b8-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="716b8-139">Da die Verbindungszeichenfolge von einer Umgebungsvariable definiert ist, können Sie die Variable über einen anderen Mechanismus und zu einer anderen Zeit festlegen.</span><span class="sxs-lookup"><span data-stu-id="716b8-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="716b8-140">Sie können beispielsweise eine andere Verbindungszeichenfolge festlegen, wenn Sie eine Bereitstellung zur Produktion in den finalen Hosts durchführen, oder von Ihren CI/CD-Pipelines in VSTS bzw. von Ihrem bevorzugten DevOps-System aus.</span><span class="sxs-lookup"><span data-stu-id="716b8-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="716b8-141">Er stellt Port 80 für den internen Zugriff auf den catalog.api-Dienst im Docker-Host zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="716b8-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="716b8-142">Der Host ist derzeit eine Linux-VM, da er auf einem Docker-Image für Linux basiert. Sie können den Container jedoch auch so konfigurieren, dass er stattdessen auf einem Windows-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="716b8-143">Er leitet den zur Verfügung gestellten Port 80 auf dem Container zu Port 5101 auf dem Docker-Hostcomputer (der Linux-VM) weiter.</span><span class="sxs-lookup"><span data-stu-id="716b8-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="716b8-144">Er verknüpft den Webdienst mit dem sql.data-Dienst (der SQL Server-Instanz für die Linux-Datenbank, die in einem Container ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="716b8-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="716b8-145">Bei Angabe dieser Abhängigkeit wird der catalog.api-Container nicht gestartet, bis der sql.data-Container gestartet wird. Dies ist wichtig, da catalog.api erfordert, dass zunächst die SQL Server-Datenbank verfügbar ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="716b8-146">Diese Art der Containerabhängigkeit reicht jedoch in vielen Fällen nicht aus, da Docker nur auf Containerebene prüft.</span><span class="sxs-lookup"><span data-stu-id="716b8-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="716b8-147">Manchmal ist der Dienst (in diesem Fall SQL Server) womöglich noch immer nicht verfügbar, deshalb ist es ratsam, die Wiederholungsversuchslogik mit exponentiellem Backoff in Ihren Clientmicroservices zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="716b8-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="716b8-148">Auf diese Weise ist die Anwendung noch immer widerstandsfähig, wenn ein Abhängigkeitscontainer für kurze Zeit nicht bereit ist.</span><span class="sxs-lookup"><span data-stu-id="716b8-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="716b8-149">Er ist so konfiguriert, dass er Zugriff auf externe Server zulässt: Die Einstellung „extra\_hosts“ ermöglicht Ihnen, auf externe Server oder Computer außerhalb des Docker-Hosts zuzugreifen (das heißt, außerhalb der standardmäßigen Linux-VM, die einen Docker-Entwicklungshost darstellt), z.B. auf eine lokalen SQL Server-Instanz auf Ihrem Entwicklungs-PC.</span><span class="sxs-lookup"><span data-stu-id="716b8-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="716b8-150">Es sind auch andere, leistungsstärkere docker-compose.yml-Einstellungen verfügbar, die in den folgenden Abschnitten erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="716b8-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="716b8-151">Verwenden von docker-compose-Dateien für mehrere Umgebungen</span><span class="sxs-lookup"><span data-stu-id="716b8-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="716b8-152">Die docker-compose.yml-Dateien sind Definitionsdateien und können von mehreren Infrastrukturen verwendet werden, die dieses Format verwenden können.</span><span class="sxs-lookup"><span data-stu-id="716b8-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="716b8-153">Das einfachste Tool ist der „docker-compose“-Befehl. Andere Tools wie Orchestratoren, z.B Docker Swarm, können diese Datei ebenso verwenden.</span><span class="sxs-lookup"><span data-stu-id="716b8-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="716b8-154">Aus diesem Grund können Sie durch die Verwendung des „docker-compose“-Befehls auf die folgenden Hauptszenarios abzielen.</span><span class="sxs-lookup"><span data-stu-id="716b8-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="716b8-155">Entwicklungsumgebungen</span><span class="sxs-lookup"><span data-stu-id="716b8-155">Development environments</span></span>

<span data-ttu-id="716b8-156">Wenn Sie Anwendungen entwickeln, ist es wichtig, dass Sie eine Anwendung in einer isolierten Entwicklungsumgebung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="716b8-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="716b8-157">Sie können den CLI-Befehl „docker-compose“ verwenden, um diese Umgebung zu erstellen, oder Visual Studio im Hintergrund ausführen, was „docker-compose“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="716b8-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="716b8-158">Die docker-compose.yml-Datei ermöglicht Ihnen, alle Dienstabhängigkeiten Ihrer Anwendung (andere Dienste, Caches, Datenbanken, Warteschlangen usw.) zu konfigurieren und zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="716b8-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="716b8-159">Mithilfe des CLI-Befehls „docker-compose“ können Sie einen oder mehrere Container für jede Abhängigkeit mit einem einzelnen Befehl (docker-compose up) erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="716b8-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="716b8-160">Die docker-compose.yml-Dateien sind Konfigurationsdateien, die von der Docker-Engine interpretiert werden, sie dienen aber auch als praktische Dokumentationsdateien über den Aufbau Ihrer Anwendung mit mehreren Container.</span><span class="sxs-lookup"><span data-stu-id="716b8-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="716b8-161">Testumgebungen</span><span class="sxs-lookup"><span data-stu-id="716b8-161">Testing environments</span></span>

<span data-ttu-id="716b8-162">Ein wichtiger Teil des Prozesses jeder fortlaufenden Bereitstellung (Continuous Deployment, CD) oder fortlaufenden Integration (Continuous Integration, CI) sind die Komponententests und Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="716b8-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="716b8-163">Diese automatisierten Tests erfordern eine isolierte Umgebung, damit sie nicht von den Benutzern oder anderen Änderungen in den Daten der Anwendung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="716b8-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="716b8-164">Mit Docker Compose können Sie diese isolierte Umgebung sehr einfach mithilfe von ein paar Befehlen aus Ihrer Eingabeaufforderung oder Skripts, die nachfolgend aufgeführt sind, erstellen und zerstören:</span><span class="sxs-lookup"><span data-stu-id="716b8-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="716b8-165">Produktionsbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="716b8-165">Production deployments</span></span>

<span data-ttu-id="716b8-166">Sie können Compose auch zum Bereitstellen auf eine Docker-Remote-Engine verwenden.</span><span class="sxs-lookup"><span data-stu-id="716b8-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="716b8-167">Ein typischer Fall hier ist die Bereitstellung auf eine einzelne Docker-Hostinstanz (z.B. eine Produktions-VM oder ein Server, der mit einem [Docker-Computer](https://docs.docker.com/machine/overview/) bereitgestellt wird).</span><span class="sxs-lookup"><span data-stu-id="716b8-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="716b8-168">Es kann jedoch auch ein ganzer [Docker Swarm](https://docs.docker.com/swarm/overview/)-Cluster sein, da Cluster auch mit den docker-compose.yml-Dateien kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="716b8-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="716b8-169">Wenn Sie einen anderen Orchestrator verwenden (Azure Service Fabric, Mesos DC/OS, Kubernetes usw.), müssen Sie möglicherweise Setup- und Metadatenkonfigurationseinstellungen (wie jene in docker-compose.yml) hinzufügen, jedoch im Format, das vom anderen Orchestrator verlangt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="716b8-170">In jedem Fall ist „docker-compose“ ein nützliches Tool und Metadatenformat für die Entwicklung, das Testen und für Produktionsworkflows, obwohl der Produktionsworkflow je nach verwendetem Orchestrator variieren kann.</span><span class="sxs-lookup"><span data-stu-id="716b8-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="716b8-171">Verwenden mehrerer docker-compose-Dateien zum Verarbeiten mehrerer Umgebungen</span><span class="sxs-lookup"><span data-stu-id="716b8-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="716b8-172">Wenn unterschiedliche Umgebungen angezielt werden sollen, verwenden Sie mehrere Compose-Dateien.</span><span class="sxs-lookup"><span data-stu-id="716b8-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="716b8-173">Dadurch können Sie mehrere Konfigurationsvarianten auf Grundlage der Umgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="716b8-174">Überschreiben der docker-compose-Basisdatei</span><span class="sxs-lookup"><span data-stu-id="716b8-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="716b8-175">Sie können eine einzelne docker-compose-Datei verwenden. Dies wird in den vorherigen Abschnitten in vereinfachten Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="716b8-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="716b8-176">Diese Verfahren sind jedoch für die meisten Anwendungen nicht empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="716b8-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="716b8-177">Standardmäßig liest Compose zwei Dateien: eine docker-compose.yml- und eine optionale docker-compose.override.yml-Datei.</span><span class="sxs-lookup"><span data-stu-id="716b8-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="716b8-178">Wie in Abbildung 8-11 dargestellt ist, erstellt Visual Studio, wenn Sie Visual Studio verwenden und Docker-Support aktivieren, eine zusätzliche docker-compose.ci.build.yml-Datei für Sie, die Sie aus Ihren CI/CD-Pipelines wie VSTS verwenden können.</span><span class="sxs-lookup"><span data-stu-id="716b8-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.ci.build,yml file for you to use from your CI/CD pipelines like in VSTS.</span></span>

![](./media/image12.png)

<span data-ttu-id="716b8-179">**Abbildung 8-11**.</span><span class="sxs-lookup"><span data-stu-id="716b8-179">**Figure 8-11**.</span></span> <span data-ttu-id="716b8-180">docker-compose-Dateien in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="716b8-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="716b8-181">Sie können die docker-compose-Dateien mit jedem beliebigen Editor bearbeiten, z.B. Visual Studio Code oder Sublime, und die Anwendung mit dem Befehl „docker-compose up“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="716b8-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="716b8-182">Gemäß der Konvention enthält die docker-compose.yml-Datei Ihre Basiskonfiguration sowie andere statische Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="716b8-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="716b8-183">Das bedeutet, dass die Dienstkonfiguration nicht in Abhängigkeit von der Entwicklungsumgebung geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="716b8-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="716b8-184">Die docker-compose.override.yml-Datei enthält – wie der Name vermuten lässt – Konfigurationsdateien, die die Basiskonfiguration außer Kraft setzen, also z.B. die Konfiguration, die von der Bereitstellungsumgebung abhängt.</span><span class="sxs-lookup"><span data-stu-id="716b8-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="716b8-185">Sie können auch mehrere Außerkraftsetzungsdateien mit unterschiedlichem Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="716b8-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="716b8-186">Die Außerkraftsetzungsdateien enthalten in der Regel zusätzliche Informationen, die von der Anwendung benötigt werden, die jedoch für eine Umgebung oder eine Bereitstellung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="716b8-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="716b8-187">Anzielen mehrerer Umgebungen</span><span class="sxs-lookup"><span data-stu-id="716b8-187">Targeting multiple environments</span></span>

<span data-ttu-id="716b8-188">Ein typischer Anwendungsfall ist, wenn Sie mehrere Compose-Dateien definieren, damit Sie auf mehrere Umgebungen abzielen können, z.B. auf die Produktion, das Staging, CI oder die Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="716b8-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="716b8-189">Sie können Ihre Compose-Konfiguration wie in Abbildung 8-12 dargestellt in mehrere Dateien aufteilen, um diese Unterschiede zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="716b8-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="716b8-190">**Abbildung 8-12**.</span><span class="sxs-lookup"><span data-stu-id="716b8-190">**Figure 8-12**.</span></span> <span data-ttu-id="716b8-191">Mehrere docker-compose-Dateien, die Werte in der docker-compose.yml-Basisdatei überschreiben</span><span class="sxs-lookup"><span data-stu-id="716b8-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="716b8-192">Sie beginnen mit der docker-compose.yml-Basisdatei.</span><span class="sxs-lookup"><span data-stu-id="716b8-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="716b8-193">Diese Basisdatei muss die Basis- oder statischen Konfigurationseinstellungen enthalten, die sich nicht in Abhängigkeit von der Umgebung ändern.</span><span class="sxs-lookup"><span data-stu-id="716b8-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="716b8-194">Beispielsweise verfügt eShopOnContainers über die folgende docker-compose.yml-Datei als Basisdatei.</span><span class="sxs-lookup"><span data-stu-id="716b8-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="716b8-195">Die Werte in der docker-compose.yml-Basisdatei dürfen sich aufgrund der unterschiedlichen Zielbereitstellungsumgebungen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="716b8-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="716b8-196">Wenn Sie den Fokus z.B. auf die webmvc-Dienstdefinition legen, können Sie sehen, dass diese Information unabhängig von der Zielumgebung mehr oder weniger gleich bleibt.</span><span class="sxs-lookup"><span data-stu-id="716b8-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="716b8-197">Sie verfügen über folgende Informationen:</span><span class="sxs-lookup"><span data-stu-id="716b8-197">You have the following information:</span></span>

-   <span data-ttu-id="716b8-198">Der Dienstname: webmvc.</span><span class="sxs-lookup"><span data-stu-id="716b8-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="716b8-199">Das benutzerdefinierte Image des Containers: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="716b8-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="716b8-200">Der Befehl, mit dem das benutzerdefinierte Docker-Image erstellt wird, und der angibt, welche Docker-Datei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="716b8-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="716b8-201">Abhängigkeiten auf anderen Diensten, damit dieser Container nicht gestartet wird, bevor die anderen Abhängigkeitscontainer nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="716b8-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="716b8-202">Sie verfügen über zusätzliche Konfigurationen. Der wichtigste Punkt ist jedoch, dass Sie in der docker-compose.yml-Basisdatei nur die Informationen festlegen möchten, die in mehreren Umgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="716b8-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="716b8-203">Sie müssen in der docker-compose.override.yml-Datei,oder in ähnlichen Dateien für die Produktion oder das Staging, eine Konfiguration platzieren, die für jede Umgebung spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="716b8-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="716b8-204">Normalerweise wird die docker-compose.override.yml- Datei wie im folgenden Beispiel von eShopOnContainers dargestellt für die Entwicklungsumgebung verwendet:</span><span class="sxs-lookup"><span data-stu-id="716b8-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}      
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}         
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="716b8-205">In diesem Beispiel macht die Konfiguration zur Entwicklungsaußerkraftsetzung dem Host einige Ports verfügbar, definiert Umgebungsvariablen mit Umleitungs-URLs und gibt Verbindungszeichenfolgen für die Entwicklungsumgebung an.</span><span class="sxs-lookup"><span data-stu-id="716b8-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="716b8-206">Diese Einstellungen sind alle nur für die Entwicklungsumgebung gedacht.</span><span class="sxs-lookup"><span data-stu-id="716b8-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="716b8-207">Wenn Sie `docker-compose up` ausführen (oder von Visual Studio aus starten), liest der Befehl die Außerkraftsetzungen automatisch so, als ob er beide Dateien zusammenführen würde.</span><span class="sxs-lookup"><span data-stu-id="716b8-207">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="716b8-208">Angenommen, Sie möchten eine andere Compose-Datei mit unterschiedlichen Konfigurationswerten, Ports oder Verbindungszeichenfolgen für die Produktionsumgebung verwenden.</span><span class="sxs-lookup"><span data-stu-id="716b8-208">Suppose that you want another Compose file for the production environment, with different configuration values, ports or connection strings.</span></span> <span data-ttu-id="716b8-209">Sie können eine weitere Außerkraftsetzungsdatei (z.B. eine Datei namens `docker-compose.prod.yml`) mit verschiedenen Einstellungen und Umgebungsvariablen erstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-209">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span>  <span data-ttu-id="716b8-210">Diese Datei kann in einem anderen Git-Repository oder von einem anderen Team verwaltet und gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="716b8-210">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="716b8-211">Durchführen einer Bereitstellung mit einer bestimmten Außerkraftsetzungsdatei</span><span class="sxs-lookup"><span data-stu-id="716b8-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="716b8-212">Um mehrere Außerkraftsetzungsdateien oder eine Außerkraftsetzungsdatei mit einem anderen Namen zu verwenden, können Sie die Option „-f“ mit dem „docker-compose“-Befehl verwenden und die Dateien angeben.</span><span class="sxs-lookup"><span data-stu-id="716b8-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="716b8-213">Erstellen Sie Mergedateien in der Reihenfolge, in der sie in der Befehlszeile angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="716b8-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="716b8-214">Im folgenden Beispiel sehen Sie, wie eine Bereitstellung mit Außerkraftsetzungsdateien durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="716b8-215">Verwenden von Umgebungsvariablen in docker-compose-Dateien</span><span class="sxs-lookup"><span data-stu-id="716b8-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="716b8-216">Es ist besonders in Produktionsumgebungen nützlich, Konfigurationsinformationen aus Umgebungsvariablen abrufen zu können. Dies wurde in vorherigen Beispielen bereits dargestellt.</span><span class="sxs-lookup"><span data-stu-id="716b8-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="716b8-217">Sie verweisen in Ihren docker-compose-Dateien mithilfe der Syntax \${MY\_VAR} auf eine Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="716b8-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="716b8-218">Die folgende Zeile aus einer docker-compose.prod.yml-Datei zeigt, wie Sie auf den Wert einer Umgebungsvariable verweisen.</span><span class="sxs-lookup"><span data-stu-id="716b8-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="716b8-219">Umgebungsvariablen werden unterschiedlich erstellt und initialisiert. Dies hängt von Ihrer Hostumgebung (Linux, Windows, Cloud-Cluster usw.) ab.</span><span class="sxs-lookup"><span data-stu-id="716b8-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="716b8-220">Eine geeignete Herangehensweise ist die Verwendung einer ENV-Datei.</span><span class="sxs-lookup"><span data-stu-id="716b8-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="716b8-221">Die docker-compose-Dateien unterstützen das Deklarieren von Standardumgebungsvariablen in der ENV-Datei.</span><span class="sxs-lookup"><span data-stu-id="716b8-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="716b8-222">Diese Werte für die Umgebungsvariablen sind die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="716b8-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="716b8-223">Sie können jedoch von den Werten überschrieben werden, die Sie möglicherweise in jeder Umgebung (Hostbetriebssystem oder Umgebungsvariablen aus Ihrem Cluster) definiert haben.</span><span class="sxs-lookup"><span data-stu-id="716b8-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="716b8-224">Sie fügen die ENV-Datei in den Ordner ein, aus dem der docker-compose-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="716b8-225">Das folgende Beispiel zeigt eine ENV-Datei wie die [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env)-Datei für die eShopOnContainers-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="716b8-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="716b8-226">Docker-compose erwartet, dass jede Zeile in einer ENV-Datei im Format &lt;variable&gt;=&lt;wert&gt; ist.</span><span class="sxs-lookup"><span data-stu-id="716b8-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="716b8-227">Beachten Sie, dass die in der Laufzeitumgebung festgelegten Werte immer die innerhalb der ENV-Datei definierten Werte außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="716b8-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="716b8-228">Auf ähnliche Weise setzen Werte, die über die Befehlsargumente der Befehlszeile übergeben werden, die in der ENV-Datei festgelegten Standardwerte außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="716b8-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="716b8-229">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="716b8-229">Additional resources</span></span>

-   <span data-ttu-id="716b8-230">**Übersicht über Docker Compose**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="716b8-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="716b8-231">**Mehrere Compose-Dateien**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="716b8-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="716b8-232">Erstellen von optimierten Docker-Images für ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="716b8-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="716b8-233">Wenn Sie Docker und .NET Core in Internetquellen untersuchen, finden Sie Docker-Dateien, die die Einfachheit der Erstellung eines Docker-Images darstellen, indem die Quelle ganz einfach in einen Container kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="716b8-234">In diesen Beispielen wird empfohlen, dass Sie mithilfe einer einfachen Konfiguration ein Docker-Image besitzen, das die Umgebung zusammen mit Ihrer Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="716b8-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="716b8-235">Zu diesem Zweck wird im folgenden Beispiel eine einfache Docker-Datei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="716b8-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="716b8-236">Eine Dockerfile-Datei wie diese funktioniert.</span><span class="sxs-lookup"><span data-stu-id="716b8-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="716b8-237">Sie können jedoch im Wesentlichen Ihre Images optimieren, besonders bei Ihren Produktionsimages funktioniert das gut.</span><span class="sxs-lookup"><span data-stu-id="716b8-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="716b8-238">Sie starten im Container- und im Microservicesmodell ständig Container.</span><span class="sxs-lookup"><span data-stu-id="716b8-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="716b8-239">Es wird kein inaktiver Container neu gestartet, wenn ein Container ganz normal verwendet wird, da der Container verwerfbar ist.</span><span class="sxs-lookup"><span data-stu-id="716b8-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="716b8-240">Orchestratoren (z.B. Docker Swarm, Kubernetes DCOS oder Azure Service Fabric) erstellen einfach neue Instanzen eines Images.</span><span class="sxs-lookup"><span data-stu-id="716b8-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="716b8-241">Das bedeutet, dass Sie eine Optimierung durch Vorkompilierung der Anwendung vornehmen müssten, wenn diese erstellt wird, damit der Instanziierungsprozess schneller wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="716b8-242">Wenn der Container gestartet wird, sollte er für die Ausführung bereit sein.</span><span class="sxs-lookup"><span data-stu-id="716b8-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="716b8-243">Es sollte keine Wiederherstellung und Kompilierung mithilfe von „dotnet restore“ und „dotnet build“ aus der Dotnet-CLI zur Laufzeit durchgeführt werden, so wie es in vielen Blogbeiträgen über .NET Core und Docker gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="716b8-244">Das .NET-Team hat sich große Mühe gegeben, damit .NET Core und ASP.NET Core ein containeroptimiertes Framework ist.</span><span class="sxs-lookup"><span data-stu-id="716b8-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="716b8-245">.NET Core ist nicht nur ein einfaches Framework mit wenig Arbeitsspeicherverbrauch, sondern das Team hat sich auf die Startleistung konzentriert und im Vergleich zu den herkömmlichen Images [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) oder [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) einige optimierte Docker-Images erstellt, z.B. das [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Image, das auf dem [Docker-Hub](https://hub.docker.com/r/microsoft/aspnetcore/) verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="716b8-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="716b8-246">Das [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Image bietet die automatische Einstellung von aspnetcore\_urls auf Port 80 den Cache von Assemblys, bevor er mit NGEN.exe zu einem nativen Image kompiliert wurde. Diese Einstellungen ermöglichen einen schnelleren Start.</span><span class="sxs-lookup"><span data-stu-id="716b8-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="716b8-247">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="716b8-247">Additional resources</span></span>

-   <span data-ttu-id="716b8-248">**Building Optimized Docker Images with ASP.NET Core**
    (Erstellen von optimierten Docker-Images mit ASP.NET Core) [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="716b8-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="716b8-249">Erstellen der Anwendung aus einem Buildcontainer (CI)</span><span class="sxs-lookup"><span data-stu-id="716b8-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="716b8-250">Ein weiterer Vorteil von Docker ist, dass Sie Ihre Anwendung wie in Abbildung 8-13 dargestellt aus einem vordefinierten Container erstellen können. So müssen Sie keinen Buildcomputer oder virtuellen Computer erstellen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="716b8-251">Sie können diesen Buildcontainer verwenden oder testen, indem Sie ihn in Ihrem Entwicklungscomputer ausführen.</span><span class="sxs-lookup"><span data-stu-id="716b8-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="716b8-252">Noch interessanter ist, dass Sie denselben Buildcontainer aus Ihrer CI-Pipeline (Continuous Integration) verwenden können.</span><span class="sxs-lookup"><span data-stu-id="716b8-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="716b8-253">**Abbildung 8-13**.</span><span class="sxs-lookup"><span data-stu-id="716b8-253">**Figure 8-13**.</span></span> <span data-ttu-id="716b8-254">Docker-Buildcontainer, der Ihre .NET-Binärdateien kompiliert</span><span class="sxs-lookup"><span data-stu-id="716b8-254">Docker build-container compiling your .NET binaries</span></span> 

<span data-ttu-id="716b8-255">Für dieses Szenario stellen wir das [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/)-Image bereit, das Sie zum Kompilieren und Erstellen Ihrer ASP.NET Core-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="716b8-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="716b8-256">Die Ausgabe wird auf einem Image basierend auf dem [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Image platziert, bei dem es sich wie bereits erwähnt um ein optimiertes Laufzeitimage handelt.</span><span class="sxs-lookup"><span data-stu-id="716b8-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="716b8-257">Das aspnetcore-build-Image enthält alles, was Sie zum Kompilieren einer ASP.NET Core-Anwendung benötigen, einschließlich .NET Core, dem ASP.NET SDK, npm, Bower, Gulp usw.</span><span class="sxs-lookup"><span data-stu-id="716b8-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="716b8-258">Wir benötigen diese Abhängigkeiten zur Buildzeit.</span><span class="sxs-lookup"><span data-stu-id="716b8-258">We need these dependencies at build time.</span></span> <span data-ttu-id="716b8-259">Diese sollen jedoch nicht zur Laufzeit in der Anwendung enthalten sein, damit das Image nicht unnötig groß wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="716b8-260">In der eShopOnContainers-Anwendung können Sie die Anwendung aus einem Container erstellen, indem Sie einfach den folgenden docker-compose-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="716b8-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="716b8-261">Abbildung 8-14 zeigt, wie dieser Befehl über die Befehlszeile ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="716b8-262">**Abbildung 8-14.**</span><span class="sxs-lookup"><span data-stu-id="716b8-262">**Figure 8-14.**</span></span> <span data-ttu-id="716b8-263">Erstellen Ihrer .NET-Anwendung aus einem Container</span><span class="sxs-lookup"><span data-stu-id="716b8-263">Building your .NET application from a container</span></span>

<span data-ttu-id="716b8-264">Wie Sie sehen können, ist der Container, der ausgeführt wird, der ci-build\_1-Container.</span><span class="sxs-lookup"><span data-stu-id="716b8-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="716b8-265">Dieser basiert auf dem aspnetcore-build-Image. So kann Ihre gesamte Anwendung von innerhalb dieses Containers anstatt von Ihrem PC kompiliert und erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="716b8-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="716b8-266">Tatsächlich wird das Erstellen und Kompilieren der .NET Core-Projekte in Linux durchgeführt, da dieser Container auf dem Docker Linux-Standardhost ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="716b8-267">Die [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml)-Datei für dieses Image (ein Teil von eShopOnContainers) enthält den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="716b8-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="716b8-268">Sie können sehen, dass ein Buildcontainer mithilfe des [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/)-Images gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* <span data-ttu-id="716b8-269">Ab **.NET Core 2.0** wird der `dotnet restore`-Befehl automatisch ausgeführt, wenn der `dotnet publish`-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="716b8-270">Sobald der Buildcontainer ausgeführt wird, führt er die .NET SDK-Befehle „dotnet restore“ und „dotnet publish“ für die Projekte in der Projektmappe aus, um die .NET-Bits zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="716b8-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="716b8-271">In diesem Fall müssen auch JavaScript-Abhängigkeiten mit npm geprüft werden, da eShopOnContainers auch über eine SPA verfügt, die auf TypeScript und Angular für den Clientcode basiert. Diese Aktion steht jedoch nicht in Verbindung mit den .NET-Bits.</span><span class="sxs-lookup"><span data-stu-id="716b8-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="716b8-272">Der Befehl „dotnet publish“ erstellt und veröffentlicht wie in Abbildung 8-15 dargestellt die kompilierte Ausgabe innerhalb jedes Projektordners im Ordner „../obj/Docker/publish“.</span><span class="sxs-lookup"><span data-stu-id="716b8-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="716b8-273">**Abbildung 8-15.**</span><span class="sxs-lookup"><span data-stu-id="716b8-273">**Figure 8-15.**</span></span> <span data-ttu-id="716b8-274">Binärdateien, die vom Befehl „dotnet publish“ generiert wurden</span><span class="sxs-lookup"><span data-stu-id="716b8-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="716b8-275">Erstellen der Docker-Images aus der CLI</span><span class="sxs-lookup"><span data-stu-id="716b8-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="716b8-276">Sobald die Anwendungsausgabe in den jeweiligen Ordnern (innerhalb jedes Projekts) veröffentlicht wurde, besteht der nächste Schritt darin, die Docker-Images tatsächlich zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="716b8-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="716b8-277">Zu diesem Zweck verwenden Sie die in Abbildung 8-16 gezeigten Befehle „docker-compose build“ und „docker-compose up“.</span><span class="sxs-lookup"><span data-stu-id="716b8-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="716b8-278">**Abbildung 8-16.**</span><span class="sxs-lookup"><span data-stu-id="716b8-278">**Figure 8-16.**</span></span> <span data-ttu-id="716b8-279">Erstellen von Docker-Images und Ausführen des Containers</span><span class="sxs-lookup"><span data-stu-id="716b8-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="716b8-280">In Abbildung 8-17 sehen Sie, wie der „docker-compose build“-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="716b8-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="716b8-281">**Abbildung 8-17**.</span><span class="sxs-lookup"><span data-stu-id="716b8-281">**Figure 8-17**.</span></span> <span data-ttu-id="716b8-282">Erstellen des Docker-Images mit dem „docker-compose build“-Befehl.</span><span class="sxs-lookup"><span data-stu-id="716b8-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="716b8-283">Der Unterschied zwischen den Befehlen „docker-compose build“ und „docker-compose up“ ist, dass „docker-compose up“ die Images jeweils erstellt und startet.</span><span class="sxs-lookup"><span data-stu-id="716b8-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="716b8-284">Wenn Sie Visual Studio verwenden, werden diese Schritte im Hintergrund ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="716b8-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="716b8-285">Visual Studio kompiliert Ihre .NET-Anwendung, erstellt die Docker-Images und stellt die Container im Docker-Host bereit.</span><span class="sxs-lookup"><span data-stu-id="716b8-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="716b8-286">Visual Studio bietet zusätzliche Features, z.B. die Möglichkeit, Ihre Container direkt aus Visual Studio zu debuggen, die in Docker ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="716b8-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="716b8-287">Zusammengefasst besteht der Vorteil daraus, dass Sie Ihre Anwendung genauso erstellen können, wie sie auch von Ihrer CI/CD-Pipeline erstellt werden würde: aus einem Container statt von einem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="716b8-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="716b8-288">Nachdem die Images erstellt wurden, müssen Sie nur noch die Docker-Images mithilfe des „docker-compose up“-Befehls ausführen.</span><span class="sxs-lookup"><span data-stu-id="716b8-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="716b8-289">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="716b8-289">Additional resources</span></span>

-   <span data-ttu-id="716b8-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)** (Erstellen von Bits aus einem Container: Einrichten der eShopOnContainers-Projektmappe in einer Windows-CLI-Umgebung)
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="716b8-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="716b8-291">[Zurück] (data-driven-crud-microservice.md) [Weiter] (database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="716b8-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
