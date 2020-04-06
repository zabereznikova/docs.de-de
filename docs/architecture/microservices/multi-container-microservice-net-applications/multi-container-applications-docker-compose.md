---
title: Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml
description: Festlegen der Zusammensetzung von Microservices für eine Anwendung mit mehreren Containern mit „docker-compose.yml“
ms.date: 01/30/2020
ms.openlocfilehash: 9143801fbbffbdc5b795a232b3333edf71f05c7c
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523648"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="b9ee0-103">Definieren Ihrer Anwendung mit mehreren Containern mit docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="b9ee0-103">Defining your multi-container application with docker-compose.yml</span></span>

<span data-ttu-id="b9ee0-104">In diesem Leitfaden wurde die Datei [docker-compose.yml](https://docs.docker.com/compose/compose-file/) in Abschnitt [Schritt 4: Definieren Ihrer Dienste beim Erstellen einer Docker-Anwendung mit mehreren Containern in docker-compose.yml](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application) eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span></span> <span data-ttu-id="b9ee0-105">Es gibt jedoch weitere Möglichkeiten, die docker-compose-Dateien zu verwenden, ausführlicherer betrachtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="b9ee0-106">Beispielsweise können Sie explizit beschreiben, wie Sie Ihre Anwendung mit mehreren Containern in der docker-compose.yml-Datei bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="b9ee0-107">Optional können Sie auch beschreiben, wie Sie Ihre benutzerdefinierten Docker-Images erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="b9ee0-108">(Benutzerdefinierte Docker-Images können ebenso mit der Docker-CLI erstellt werden.)</span><span class="sxs-lookup"><span data-stu-id="b9ee0-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="b9ee0-109">Im Grunde genommen definieren Sie jeden der Container, den Sie bereitstellen möchten, und dazu noch bestimmte Eigenschaften für jede Containerbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="b9ee0-110">Sobald Sie über eine Datei mit der Beschreibung der Bereitstellung von mehreren Containern verfügen, können Sie die gesamte Projektmappe in einer einzelnen Aktion, die von dem CLI-Befehl [docker-compose up](https://docs.docker.com/compose/overview/) orchestriert wird, bereitstellen, oder Sie können diese transparent von Visual Studio bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="b9ee0-111">Andernfalls müssen Sie die Docker-CLI verwenden, um die Container nacheinander in mehreren Schritten bereitzustellen, indem Sie den Befehl `docker run` über die Befehlszeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the `docker run` command from the command line.</span></span> <span data-ttu-id="b9ee0-112">Daher muss jeder in der Datei „docker-compose.yml“ definierte Dienst genau ein Image oder einen Build definieren.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="b9ee0-113">Andere Schlüssel sind optional und analog zu ihren Gegenstücken von `docker run` aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-113">Other keys are optional, and are analogous to their `docker run` command-line counterparts.</span></span>

<span data-ttu-id="b9ee0-114">Der folgende YAML-Code ist die Definition einer möglichen globalen aber einzelnen docker-compose.yml-Datei für das eShopOnContainers-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="b9ee0-115">Dies ist nicht die tatsächliche docker-compose-Datei von eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="b9ee0-116">Stattdessen handelt es sich um eine vereinfachte und konsolidierte Version in einer einzelnen Datei, die zum Arbeiten mit docker-compose-Datei nicht die beste Lösung ist. Dies wird im Verlauf des Artikels erläutert.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '3.4'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
      - BasketUrl=http://basket-api
    ports:
      - "5100:80"
    depends_on:
      - catalog-api
      - ordering-api
      - basket-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  basket-api:
    image: eshop/basket-api
    environment:
      - ConnectionString=sqldata
    ports:
      - "5103:80"
    depends_on:
      - sqldata

  sqldata:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basketdata:
    image: redis
```

<span data-ttu-id="b9ee0-117">Der Stammschlüssel in dieser Datei ist „services“.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-117">The root key in this file is services.</span></span> <span data-ttu-id="b9ee0-118">Unter diesem Schlüssel definieren Sie die Dienste, die Sie bereitstellen und ausführen möchten, wenn Sie den Befehl `docker-compose up` ausführen oder wenn Sie die Bereitstellung von Visual Studio aus mithilfe dieser docker-compose.yml-Datei durchführen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-118">Under that key, you define the services you want to deploy and run when you execute the `docker-compose up` command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="b9ee0-119">In diesem Fall sind wie in der folgenden Tabelle beschrieben mehrere Dienste für die docker-compose.yml-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following table.</span></span>

| <span data-ttu-id="b9ee0-120">Dienstname</span><span class="sxs-lookup"><span data-stu-id="b9ee0-120">Service name</span></span> | <span data-ttu-id="b9ee0-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9ee0-121">Description</span></span> |
|--------------|-------------|
| <span data-ttu-id="b9ee0-122">webmvc</span><span class="sxs-lookup"><span data-stu-id="b9ee0-122">webmvc</span></span>       | <span data-ttu-id="b9ee0-123">Container, einschließlich der ASP.NET Core-MVC-Anwendung, die die Microservices der serverseitigen Programmiersprache C\# verwendet</span><span class="sxs-lookup"><span data-stu-id="b9ee0-123">Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>|
| <span data-ttu-id="b9ee0-124">catalog-api</span><span class="sxs-lookup"><span data-stu-id="b9ee0-124">catalog-api</span></span>  | <span data-ttu-id="b9ee0-125">Container, einschließlich des Katalogmicroservice für die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="b9ee0-125">Container including the Catalog ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="b9ee0-126">ordering-api</span><span class="sxs-lookup"><span data-stu-id="b9ee0-126">ordering-api</span></span> | <span data-ttu-id="b9ee0-127">Container, einschließlich des Microservice für Bestellungen für die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="b9ee0-127">Container including the Ordering ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="b9ee0-128">sqldata</span><span class="sxs-lookup"><span data-stu-id="b9ee0-128">sqldata</span></span>     | <span data-ttu-id="b9ee0-129">Container unter SQL Server für Linux, einschließlich der Microservicesdatenbanken</span><span class="sxs-lookup"><span data-stu-id="b9ee0-129">Container running SQL Server for Linux, holding the microservices databases</span></span> |
| <span data-ttu-id="b9ee0-130">basket-api</span><span class="sxs-lookup"><span data-stu-id="b9ee0-130">basket-api</span></span>   | <span data-ttu-id="b9ee0-131">Container mit dem Warenkorbmicroservice für die ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="b9ee0-131">Container with the Basket ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="b9ee0-132">basketdata</span><span class="sxs-lookup"><span data-stu-id="b9ee0-132">basketdata</span></span>  | <span data-ttu-id="b9ee0-133">Container, der den REDIS-Cachedienst mit der basket-Datenbank als REDIS-Cache ausführt</span><span class="sxs-lookup"><span data-stu-id="b9ee0-133">Container running the REDIS cache service, with the basket database as a REDIS cache</span></span> |

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="b9ee0-134">Ein einfacher Container für die Webdienst-API</span><span class="sxs-lookup"><span data-stu-id="b9ee0-134">A simple Web Service API container</span></span>

<span data-ttu-id="b9ee0-135">Der Containermicroservice „catalog.api“ hat mit Fokus auf einen einzelnen Container eine klare Definition:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-135">Focusing on a single container, the catalog-api container-microservice has a straightforward definition:</span></span>

```yml
  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata
```

<span data-ttu-id="b9ee0-136">Dieser Containerdienst verfügt über die folgende grundlegende Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-136">This containerized service has the following basic configuration:</span></span>

- <span data-ttu-id="b9ee0-137">Er basiert auf dem benutzerdefinierten Image **eshop/catalog-api**.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-137">It is based on the custom **eshop/catalog-api** image.</span></span> <span data-ttu-id="b9ee0-138">Der Einfachheit halber gibt es keine „build: key“-Einstellung in der Datei.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-138">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="b9ee0-139">Das bedeutet, dass das Image zuvor erstellt worden (mit „docker build“) oder aus einer beliebigen Docker-Registrierung heruntergeladen worden sein muss (mit dem Befehl „docker pull“).</span><span class="sxs-lookup"><span data-stu-id="b9ee0-139">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

- <span data-ttu-id="b9ee0-140">Er definiert die Umgebungsvariable mit der Bezeichnung „ConnectionString“ mit der Verbindungszeichenfolge, die von Entity Framework für den Zugriff auf die SQL Server-Instanz, die das Katalogdatenmodell enthält, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-140">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="b9ee0-141">In diesem Fall enthält der gleicher SQL Server-Container mehrere Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-141">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="b9ee0-142">Aus diesem Grund benötigen Sie weniger Arbeitsspeicher in Ihrem Entwicklungscomputer für Docker.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-142">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="b9ee0-143">Allerdings können Sie auch einen SQL Server-Container für jede Microservicedatenbank bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-143">However, you could also deploy one SQL Server container for each microservice database.</span></span>

- <span data-ttu-id="b9ee0-144">Der SQL Server-Name lautet **sqldata**. Dies ist derselbe Name, der für den Container verwendet wird, der die SQL Server-Instanz für Linux ausführt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-144">The SQL Server name is **sqldata**, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="b9ee0-145">Das ist wirklich praktisch, denn die Möglichkeit, diese Namensauflösung (intern für den Docker-Host) zu verwenden, löst die Netzwerkadresse auf. Sie müssen die interne IP-Adresse für die Container also nicht kennen, auf die Sie von anderen Container aus zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-145">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="b9ee0-146">Da die Verbindungszeichenfolge von einer Umgebungsvariable definiert ist, können Sie die Variable über einen anderen Mechanismus und zu einer anderen Zeit festlegen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-146">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="b9ee0-147">Sie können beispielsweise eine andere Verbindungszeichenfolge festlegen, wenn Sie eine Bereitstellung zur Produktion in den finalen Hosts durchführen, oder von Ihren CI/CD-Pipelines in Azure DevOps Services bzw. von Ihrem bevorzugten DevOps-System aus.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-147">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

- <span data-ttu-id="b9ee0-148">Er stellt Port 80 für den internen Zugriff auf den Dienst **catalog.api** im Docker-Host zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-148">It exposes port 80 for internal access to the **catalog-api** service within the Docker host.</span></span> <span data-ttu-id="b9ee0-149">Der Host ist derzeit eine Linux-VM, da er auf einem Docker-Image für Linux basiert. Sie können den Container jedoch auch so konfigurieren, dass er stattdessen auf einem Windows-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-149">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

- <span data-ttu-id="b9ee0-150">Er leitet den zur Verfügung gestellten Port 80 auf dem Container zu Port 5101 auf dem Docker-Hostcomputer (der Linux-VM) weiter.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-150">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

- <span data-ttu-id="b9ee0-151">Er verknüpft den Webdienst mit dem Dienst **sqldata** (der SQL Server-Instanz für die Linux-Datenbank, die in einem Container ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="b9ee0-151">It links the web service to the **sqldata** service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="b9ee0-152">Bei Angabe dieser Abhängigkeit wird der Container „catalog-api“ nicht gestartet, bis der Container „sqldata“ gestartet wird. Dies ist wichtig, da „catalog-api“ verlangt, dass zunächst die SQL Server-Datenbank verfügbar ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-152">When you specify this dependency, the catalog-api container will not start until the sqldata container has already started; this is important because catalog-api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="b9ee0-153">Diese Art der Containerabhängigkeit reicht jedoch in vielen Fällen nicht aus, da Docker nur auf Containerebene prüft.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-153">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="b9ee0-154">Manchmal ist der Dienst (in diesem Fall SQL Server) womöglich noch immer nicht verfügbar, deshalb ist es ratsam, die Wiederholungsversuchslogik mit exponentiellem Backoff in Ihren Clientmicroservices zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-154">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="b9ee0-155">Auf diese Weise ist die Anwendung noch immer widerstandsfähig, wenn ein Abhängigkeitscontainer für kurze Zeit nicht bereit ist.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-155">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

- <span data-ttu-id="b9ee0-156">Er ist so konfiguriert, dass er Zugriff auf externe Server zulässt: Die Einstellung „extra\_hosts“ ermöglicht es Ihnen, auf externe Server oder Computer außerhalb des Docker-Hosts zuzugreifen (das heißt, außerhalb der standardmäßigen Linux-VM, die einen Docker-Entwicklungshost darstellt), z. B. auf eine lokale SQL Server-Instanz auf Ihrem Entwicklungs-PC.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-156">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM, which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="b9ee0-157">Es sind auch andere, leistungsstärkere `docker-compose.yml`-Einstellungen verfügbar, die in den folgenden Abschnitten erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-157">There are also other, more advanced `docker-compose.yml` settings that we'll discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="b9ee0-158">Verwenden von docker-compose-Dateien für mehrere Umgebungen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-158">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="b9ee0-159">Die `docker-compose.*.yml`-Dateien sind Definitionsdateien und können von mehreren Infrastrukturen verwendet werden, die dieses Format verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-159">The `docker-compose.*.yml` files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="b9ee0-160">Das einfachste Tool ist der Befehl „docker-compose“.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-160">The most straightforward tool is the docker-compose command.</span></span>

<span data-ttu-id="b9ee0-161">Aus diesem Grund können Sie durch die Verwendung des „docker-compose“-Befehls auf die folgenden Hauptszenarios abzielen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-161">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="b9ee0-162">Entwicklungsumgebungen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-162">Development environments</span></span>

<span data-ttu-id="b9ee0-163">Wenn Sie Anwendungen entwickeln, ist es wichtig, dass Sie eine Anwendung in einer isolierten Entwicklungsumgebung ausführen können.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-163">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="b9ee0-164">Sie können diese Umgebung mithilfe des CLI-Befehls „docker-compose“ oder in Visual Studio erstellen. Visual Studio verwendet „docker-compose“ im Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-164">You can use the docker-compose CLI command to create that environment or Visual Studio, which uses docker-compose under the covers.</span></span>

<span data-ttu-id="b9ee0-165">Die docker-compose.yml-Datei ermöglicht Ihnen, alle Dienstabhängigkeiten Ihrer Anwendung (andere Dienste, Caches, Datenbanken, Warteschlangen usw.) zu konfigurieren und zu dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-165">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="b9ee0-166">Mithilfe des CLI-Befehls „docker-compose“ können Sie mindestens einen Container für jede Abhängigkeit mit einem einzelnen Befehl („docker-compose up“) erstellen oder starten.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-166">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="b9ee0-167">Die docker-compose.yml-Dateien sind Konfigurationsdateien, die von der Docker-Engine interpretiert werden, sie dienen aber auch als praktische Dokumentationsdateien über den Aufbau Ihrer Anwendung mit mehreren Container.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-167">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="b9ee0-168">Testumgebungen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-168">Testing environments</span></span>

<span data-ttu-id="b9ee0-169">Ein wichtiger Teil des Prozesses jeder fortlaufenden Bereitstellung (Continuous Deployment, CD) oder fortlaufenden Integration (Continuous Integration, CI) sind die Komponententests und Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-169">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="b9ee0-170">Diese automatisierten Tests erfordern eine isolierte Umgebung, damit sie nicht von den Benutzern oder anderen Änderungen in den Daten der Anwendung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-170">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="b9ee0-171">Mit Docker Compose können Sie diese isolierte Umgebung sehr einfach mit einigen wenigen Befehlen an der Eingabeaufforderung oder in Skripts erstellen und zerstören. Hier einige Beispiele für diese Befehle:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-171">With Docker Compose, you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml down
```

#### <a name="production-deployments"></a><span data-ttu-id="b9ee0-172">Produktionsbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-172">Production deployments</span></span>

<span data-ttu-id="b9ee0-173">Sie können Compose auch zum Bereitstellen auf eine Docker-Remote-Engine verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-173">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="b9ee0-174">Ein typischer Fall hier ist die Bereitstellung auf eine einzelne Docker-Hostinstanz (z.B. eine Produktions-VM oder ein Server, der mit einem [Docker-Computer](https://docs.docker.com/machine/overview/) bereitgestellt wird).</span><span class="sxs-lookup"><span data-stu-id="b9ee0-174">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span>

<span data-ttu-id="b9ee0-175">Wenn Sie einen anderen Orchestrator verwenden (Azure Service Fabric, Kubernetes usw.), müssen Sie möglicherweise Setup- und Metadatenkonfigurationseinstellungen wie jene in „docker-compose.yml“ hinzufügen, jedoch in dem Format, das vom anderen Orchestrator verlangt wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-175">If you are using any other orchestrator (Azure Service Fabric, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="b9ee0-176">In jedem Fall ist „docker-compose“ ein nützliches Tool und Metadatenformat für die Entwicklung, das Testen und für Produktionsworkflows, obwohl der Produktionsworkflow je nach verwendetem Orchestrator variieren kann.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-176">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="b9ee0-177">Verwenden mehrerer docker-compose-Dateien zum Verarbeiten mehrerer Umgebungen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-177">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="b9ee0-178">Wenn unterschiedliche Umgebungen angezielt werden sollen, verwenden Sie mehrere Compose-Dateien.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-178">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="b9ee0-179">Dadurch können Sie mehrere Konfigurationsvarianten auf Grundlage der Umgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-179">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="b9ee0-180">Überschreiben der docker-compose-Basisdatei</span><span class="sxs-lookup"><span data-stu-id="b9ee0-180">Overriding the base docker-compose file</span></span>

<span data-ttu-id="b9ee0-181">Sie können eine einzelne docker-compose-Datei verwenden. Dies wird in den vorherigen Abschnitten in vereinfachten Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-181">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="b9ee0-182">Diese Verfahren sind jedoch für die meisten Anwendungen nicht empfehlenswert.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-182">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="b9ee0-183">Standardmäßig liest Compose zwei Dateien: eine docker-compose.yml- und eine optionale docker-compose.override.yml-Datei.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-183">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="b9ee0-184">Wenn Sie Visual Studio verwenden und die Docker-Unterstützung aktivieren, erstellt Visual Studio wie in Abbildung 6-11 dargestellt eine zusätzliche „docker-compose.vs.debug.g.yml“-Datei zum Debuggen der Anwendung. Sie können sich diese Datei im Ordner obj\\Docker\\ im Projektmappenhauptordner ansehen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-184">As shown in Figure 6-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.vs.debug.g.yml file for debugging the application, you can take a look at this file in folder obj\\Docker\\ in the main solution folder.</span></span>

![Screenshot der Dateien in einem Docker Compose-Projekt.](./media/multi-container-applications-docker-compose/docker-compose-file-visual-studio.png)

<span data-ttu-id="b9ee0-186">**Abbildung 6-11**.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-186">**Figure 6-11**.</span></span> <span data-ttu-id="b9ee0-187">docker-compose-Dateien in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b9ee0-187">docker-compose files in Visual Studio 2019</span></span>

<span data-ttu-id="b9ee0-188">**docker-compose**-Projektdateistruktur:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-188">**docker-compose** project file structure:</span></span>

- <span data-ttu-id="b9ee0-189">*.dockerignore*: wird zum Ignorieren von Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-189">*.dockerignore* - used to ignore files</span></span>
- <span data-ttu-id="b9ee0-190">*docker-compose.yml*: wird zum Verfassen von Microservices verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-190">*docker-compose.yml* - used to compose microservices</span></span>
- <span data-ttu-id="b9ee0-191">*docker-compose.override.yml*: wird zum Konfigurieren der Microservices-Umgebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-191">*docker-compose.override.yml* - used to configure microservices environment</span></span>

<span data-ttu-id="b9ee0-192">Sie können die docker-compose-Dateien mit jedem beliebigen Editor bearbeiten, z.B. mit Visual Studio Code oder Sublime, und die Anwendung mit dem Befehl „docker-compose up“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-192">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="b9ee0-193">Gemäß der Konvention enthält die docker-compose.yml-Datei Ihre Basiskonfiguration sowie andere statische Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-193">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="b9ee0-194">Das bedeutet, dass die Dienstkonfiguration nicht in Abhängigkeit von der Entwicklungsumgebung geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-194">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="b9ee0-195">Die docker-compose.override.yml-Datei enthält – wie der Name vermuten lässt – Konfigurationsdateien, die die Basiskonfiguration außer Kraft setzen, also z.B. die Konfiguration, die von der Bereitstellungsumgebung abhängt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-195">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="b9ee0-196">Sie können auch mehrere Außerkraftsetzungsdateien mit unterschiedlichem Namen besitzen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-196">You can have multiple override files with different names also.</span></span> <span data-ttu-id="b9ee0-197">Die Außerkraftsetzungsdateien enthalten in der Regel zusätzliche Informationen, die von der Anwendung benötigt werden, die jedoch für eine Umgebung oder eine Bereitstellung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-197">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="b9ee0-198">Anzielen mehrerer Umgebungen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-198">Targeting multiple environments</span></span>

<span data-ttu-id="b9ee0-199">Ein typischer Anwendungsfall ist, wenn Sie mehrere Compose-Dateien definieren, damit Sie auf mehrere Umgebungen abzielen können, z.B. auf die Produktion, das Staging, CI oder die Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-199">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="b9ee0-200">Sie können Ihre Compose-Konfiguration wie in Abbildung 6-12 dargestellt in mehrere Dateien aufteilen, um diese Unterschiede zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-200">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 6-12.</span></span>

![Diagramm mit drei Docker Compose-Dateien, die zum Überschreiben der Basisdatei festgelegt sind.](./media/multi-container-applications-docker-compose/multiple-docker-compose-files-override-base.png)

<span data-ttu-id="b9ee0-202">**Abbildung 6-12**.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-202">**Figure 6-12**.</span></span> <span data-ttu-id="b9ee0-203">Mehrere docker-compose-Dateien, die Werte in der docker-compose.yml-Basisdatei überschreiben</span><span class="sxs-lookup"><span data-stu-id="b9ee0-203">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="b9ee0-204">Sie können mehrere docker.compose\*.yml-Dateien kombinieren, wenn verschiedene Umgebungen abgedeckt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-204">You can combine multiple docker-compose\*.yml files to handle different environments.</span></span> <span data-ttu-id="b9ee0-205">Sie beginnen mit der docker-compose.yml-Basisdatei.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-205">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="b9ee0-206">Diese Basisdatei muss die Basis- oder statischen Konfigurationseinstellungen enthalten, die sich nicht in Abhängigkeit von der Umgebung ändern.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-206">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="b9ee0-207">Beispielsweise verfügt eShopOnContainers über die folgende docker-compose.yml-Datei (zur Vereinfachung mit weniger Diensten) als Basisdatei.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-207">For example, the eShopOnContainers has the following docker-compose.yml file (simplified with fewer services) as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket-api:
    image: eshop/basket-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basketdata
      - identity-api
      - rabbitmq

  catalog-api:
    image: eshop/catalog-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sqldata
      - rabbitmq

  marketing-api:
    image: eshop/marketing-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sqldata
      - nosqldata
      - identity-api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
    depends_on:
      - catalog-api
      - ordering-api
      - identity-api
      - basket-api
      - marketing-api

  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest

  nosqldata:
    image: mongo

  basketdata:
    image: redis

  rabbitmq:
    image: rabbitmq:3-management

```

<span data-ttu-id="b9ee0-208">Die Werte in der docker-compose.yml-Basisdatei dürfen sich aufgrund der unterschiedlichen Zielbereitstellungsumgebungen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-208">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="b9ee0-209">Wenn Sie den Fokus z.B. auf die webmvc-Dienstdefinition legen, können Sie sehen, dass diese Information unabhängig von der Zielumgebung mehr oder weniger gleich bleibt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-209">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="b9ee0-210">Sie verfügen über folgende Informationen:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-210">You have the following information:</span></span>

- <span data-ttu-id="b9ee0-211">Der Dienstname: webmvc.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-211">The service name: webmvc.</span></span>

- <span data-ttu-id="b9ee0-212">Das benutzerdefinierte Image des Containers: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-212">The container’s custom image: eshop/webmvc.</span></span>

- <span data-ttu-id="b9ee0-213">Der Befehl, mit dem das benutzerdefinierte Docker-Image erstellt wird, und der angibt, welche Docker-Datei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-213">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

- <span data-ttu-id="b9ee0-214">Abhängigkeiten auf anderen Diensten, damit dieser Container nicht gestartet wird, bevor die anderen Abhängigkeitscontainer nicht gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-214">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="b9ee0-215">Sie verfügen über zusätzliche Konfigurationen. Der wichtigste Punkt ist jedoch, dass Sie in der docker-compose.yml-Basisdatei nur die Informationen festlegen möchten, die in mehreren Umgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-215">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="b9ee0-216">Sie müssen in der docker-compose.override.yml-Datei,oder in ähnlichen Dateien für die Produktion oder das Staging, eine Konfiguration platzieren, die für jede Umgebung spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-216">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="b9ee0-217">Normalerweise wird die docker-compose.override.yml- Datei wie im folgenden Beispiel von eShopOnContainers dargestellt für die Entwicklungsumgebung verwendet:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-217">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services:
# Simplified number of services here:

  basket-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basketdata}
      - identityUrl=http://identity-api
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

  catalog-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
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

  marketing-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - identityUrl=http://identity-api
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
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog-api/hc
      - OrderingUrlHC=http://ordering-api/hc
      - IdentityUrlHC=http://identity-api/hc
      - BasketUrlHC=http://basket-api/hc
      - MarketingUrlHC=http://marketing-api/hc
      - PaymentUrlHC=http://payment-api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
  basketdata:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

<span data-ttu-id="b9ee0-218">In diesem Beispiel macht die Konfiguration zur Entwicklungsaußerkraftsetzung dem Host einige Ports verfügbar, definiert Umgebungsvariablen mit Umleitungs-URLs und gibt Verbindungszeichenfolgen für die Entwicklungsumgebung an.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-218">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="b9ee0-219">Diese Einstellungen sind alle nur für die Entwicklungsumgebung gedacht.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-219">These settings are all just for the development environment.</span></span>

<span data-ttu-id="b9ee0-220">Wenn Sie `docker-compose up` ausführen (oder von Visual Studio aus starten), liest der Befehl die Außerkraftsetzungen automatisch so, als ob er beide Dateien zusammenführen würde.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-220">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="b9ee0-221">Angenommen, Sie möchten eine andere Compose-Datei mit anderen Konfigurationswerten, Ports oder Verbindungszeichenfolgen für die Produktionsumgebung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-221">Suppose that you want another Compose file for the production environment, with different configuration values, ports, or connection strings.</span></span> <span data-ttu-id="b9ee0-222">Sie können eine weitere Außerkraftsetzungsdatei (z.B. eine Datei namens `docker-compose.prod.yml`) mit verschiedenen Einstellungen und Umgebungsvariablen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-222">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span> <span data-ttu-id="b9ee0-223">Diese Datei kann in einem anderen Git-Repository oder von einem anderen Team verwaltet und gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-223">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="b9ee0-224">Durchführen einer Bereitstellung mit einer bestimmten Außerkraftsetzungsdatei</span><span class="sxs-lookup"><span data-stu-id="b9ee0-224">How to deploy with a specific override file</span></span>

<span data-ttu-id="b9ee0-225">Um mehrere Außerkraftsetzungsdateien oder eine Außerkraftsetzungsdatei mit einem anderen Namen zu verwenden, können Sie die Option „-f“ mit dem „docker-compose“-Befehl verwenden und die Dateien angeben.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-225">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="b9ee0-226">Erstellen Sie Mergedateien in der Reihenfolge, in der sie in der Befehlszeile angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-226">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="b9ee0-227">Im folgenden Beispiel sehen Sie, wie eine Bereitstellung mit Außerkraftsetzungsdateien durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-227">The following example shows how to deploy with override files.</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="b9ee0-228">Verwenden von Umgebungsvariablen in docker-compose-Dateien</span><span class="sxs-lookup"><span data-stu-id="b9ee0-228">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="b9ee0-229">Es ist besonders in Produktionsumgebungen nützlich, Konfigurationsinformationen aus Umgebungsvariablen abrufen zu können. Dies wurde in vorherigen Beispielen bereits dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-229">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="b9ee0-230">Sie können in Ihren docker-compose-Dateien mithilfe der Syntax ${MY\_VAR} auf eine Umgebungsvariable verweisen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-230">You can reference an environment variable in your docker-compose files using the syntax ${MY\_VAR}.</span></span> <span data-ttu-id="b9ee0-231">Die folgende Zeile aus einer docker-compose.prod.yml-Datei zeigt, wie Sie auf den Wert einer Umgebungsvariable verweisen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-231">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="b9ee0-232">Umgebungsvariablen werden unterschiedlich erstellt und initialisiert. Dies hängt von Ihrer Hostumgebung (Linux, Windows, Cloud-Cluster usw.) ab.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-232">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="b9ee0-233">Eine geeignete Herangehensweise ist die Verwendung einer ENV-Datei.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-233">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="b9ee0-234">Die docker-compose-Dateien unterstützen das Deklarieren von Standardumgebungsvariablen in der ENV-Datei.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-234">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="b9ee0-235">Diese Werte für die Umgebungsvariablen sind die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-235">These values for the environment variables are the default values.</span></span> <span data-ttu-id="b9ee0-236">Sie können jedoch von den Werten überschrieben werden, die Sie möglicherweise in jeder Umgebung (Hostbetriebssystem oder Umgebungsvariablen aus Ihrem Cluster) definiert haben.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-236">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="b9ee0-237">Sie fügen die ENV-Datei in den Ordner ein, aus dem der docker-compose-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-237">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="b9ee0-238">Das folgende Beispiel zeigt eine ENV-Datei wie die [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env)-Datei für die eShopOnContainers-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-238">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```sh
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="b9ee0-239">Docker-compose erwartet, dass jede Zeile in einer ENV-Datei im Format \<variable\>=\<wert\> ist.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-239">Docker-compose expects each line in an .env file to be in the format \<variable\>=\<value\>.</span></span>

<span data-ttu-id="b9ee0-240">Die in der Laufzeitumgebung festgelegten Werte setzen immer die in der ENV-Datei definierten Werte außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-240">The values set in the run-time environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="b9ee0-241">Auf ähnliche Weise setzen Werte, die über Befehlszeilenargumente übergeben werden, die in der ENV-Datei festgelegten Standardwerte außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-241">In a similar way, values passed via command-line arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b9ee0-242">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-242">Additional resources</span></span>

- <span data-ttu-id="b9ee0-243">**Overview of Docker Compose (Übersicht über Docker Compose)**  </span><span class="sxs-lookup"><span data-stu-id="b9ee0-243">**Overview of Docker Compose** </span></span>\
    <https://docs.docker.com/compose/overview/>

- <span data-ttu-id="b9ee0-244">**Multiple Compose files (Mehrere Compose-Dateien)**  </span><span class="sxs-lookup"><span data-stu-id="b9ee0-244">**Multiple Compose files** </span></span>\
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="b9ee0-245">Erstellen von optimierten Docker-Images für ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b9ee0-245">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="b9ee0-246">Wenn Sie Docker und .NET Core in Internetquellen untersuchen, finden Sie Docker-Dateien, die die Einfachheit der Erstellung eines Docker-Images darstellen, indem die Quelle ganz einfach in einen Container kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-246">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="b9ee0-247">In diesen Beispielen wird empfohlen, dass Sie mithilfe einer einfachen Konfiguration ein Docker-Image besitzen, das die Umgebung zusammen mit Ihrer Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-247">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="b9ee0-248">Zu diesem Zweck wird im folgenden Beispiel eine einfache Docker-Datei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-248">The following example shows a simple Dockerfile in this vein.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/sdk:3.1
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="b9ee0-249">Eine Dockerfile-Datei wie diese funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-249">A Dockerfile like this will work.</span></span> <span data-ttu-id="b9ee0-250">Sie können jedoch im Wesentlichen Ihre Images optimieren, besonders bei Ihren Produktionsimages funktioniert das gut.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-250">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="b9ee0-251">Sie starten im Container- und im Microservicesmodell ständig Container.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-251">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="b9ee0-252">Es wird kein inaktiver Container neu gestartet, wenn ein Container ganz normal verwendet wird, da der Container verwerfbar ist.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-252">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="b9ee0-253">Orchestratoren (z.B. Kubernetes und Azure Service Fabric) erstellen nur neue Instanzen von Images.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-253">Orchestrators (like Kubernetes and Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="b9ee0-254">Das bedeutet, dass Sie eine Optimierung durch Vorkompilierung der Anwendung vornehmen müssten, wenn diese erstellt wird, damit der Instanziierungsprozess schneller wird.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-254">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="b9ee0-255">Wenn der Container gestartet wird, sollte er für die Ausführung bereit sein.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-255">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="b9ee0-256">Wie in vielen Blogbeiträgen über .NET Core und Docker gezeigt wird, sollte keine Wiederherstellung und Kompilierung mithilfe der Befehle `dotnet restore` und `dotnet build` aus der Dotnet-CLI zur Laufzeit durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-256">You should not restore and compile at run time, using `dotnet restore` and `dotnet build` commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="b9ee0-257">Das .NET-Team hat sich große Mühe gegeben, damit .NET Core und ASP.NET Core ein containeroptimiertes Framework ist.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-257">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="b9ee0-258">.NET Core ist nicht nur ein einfaches Framework mit geringem Speicherbedarf, sondern das Team hat sich auch auf optimierte Docker-Images für drei Hauptszenarios konzentriert und diese ab Version 2.1 in der Docker-Hub-Registrierung unter *dotnet/core* veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-258">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on optimized Docker images for three main scenarios and published them in the Docker Hub registry at *dotnet/core*, beginning with version 2.1:</span></span>

1. <span data-ttu-id="b9ee0-259">**Entwicklung:** Die schnelle Iteration hat Vorrang. Das Debuggen von Änderungen und die Größe sind zweitrangig.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-259">**Development**: Where the priority is the ability to quickly iterate and debug changes, and where size is secondary.</span></span>

2. <span data-ttu-id="b9ee0-260">**Build:** Das Kompilieren der Anwendung hat Vorrang. Außerdem sind Binärdateien und andere Abhängigkeiten enthalten, um die Binärdateien zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-260">**Build**: The priority is compiling the application and includes binaries and other dependencies to optimize binaries.</span></span>

3. <span data-ttu-id="b9ee0-261">**Produktion:** Das schnelle Bereitstellen und Starten von Containern hat Vorrang. Die Images sind deshalb auf Binärdateien und den Inhalt beschränkt, der zum Ausführen der Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-261">**Production**: Where the focus is fast deploying and starting of containers, so these images are limited to the binaries and the content needed to run the application.</span></span>

<span data-ttu-id="b9ee0-262">Zu diesem Zweck stellt das .NET-Team vier grundlegende Varianten unter [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) (im Docker-Hub) bereit:</span><span class="sxs-lookup"><span data-stu-id="b9ee0-262">To achieve this, the .NET team is providing four basic variants in [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) (at Docker Hub):</span></span>

1. <span data-ttu-id="b9ee0-263">**sdk:** für Entwicklungs- und Buildszenarien</span><span class="sxs-lookup"><span data-stu-id="b9ee0-263">**sdk**: for development and build scenarios</span></span>
1. <span data-ttu-id="b9ee0-264">**aspnet**: für ASP.NET-Produktionsszenarien</span><span class="sxs-lookup"><span data-stu-id="b9ee0-264">**aspnet**: for ASP.NET production scenarios</span></span>
1. <span data-ttu-id="b9ee0-265">**runtime**: für .NET-Produktionsszenarien</span><span class="sxs-lookup"><span data-stu-id="b9ee0-265">**runtime**: for .NET production scenarios</span></span>
1. <span data-ttu-id="b9ee0-266">**runtime-deps:** für Produktionsszenarien von [eigenständigen Anwendungen](../../../core/deploying/index.md#publish-self-contained)</span><span class="sxs-lookup"><span data-stu-id="b9ee0-266">**runtime-deps**: for production scenarios of [self-contained applications](../../../core/deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="b9ee0-267">Für einen schnelleren Start setzen Runtimeimages auch automatisch aspnetcore\_urls auf Port 80 und verwenden Ngen, um einen nativen Imagecache von Assemblys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9ee0-267">For faster startup, runtime images also automatically set aspnetcore\_urls to port 80 and use Ngen to create a native image cache of assemblies.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="b9ee0-268">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b9ee0-268">Additional resources</span></span>

- <span data-ttu-id="b9ee0-269">**Building Optimized Docker Images with ASP.NET Core (Erstellen von optimierten Docker-Images mit ASP.NET Core)**</span><span class="sxs-lookup"><span data-stu-id="b9ee0-269">**Building Optimized Docker Images with ASP.NET Core**</span></span>  
  <https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core>

- <span data-ttu-id="b9ee0-270">**Erstellen von Docker-Images für .NET Core-Anwendungen**</span><span class="sxs-lookup"><span data-stu-id="b9ee0-270">**Building Docker Images for .NET Core Applications**</span></span>  
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

> [!div class="step-by-step"]
> <span data-ttu-id="b9ee0-271">[Zurück](data-driven-crud-microservice.md)
> [Weiter](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="b9ee0-271">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>
