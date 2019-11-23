---
title: Docker-GrpC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.net Core GrpC-Anwendungen
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967841"
---
# <a name="docker"></a><span data-ttu-id="66b1e-103">Docker</span><span class="sxs-lookup"><span data-stu-id="66b1e-103">Docker</span></span>

<span data-ttu-id="66b1e-104">In diesem Abschnitt wird die Erstellung von Docker-Images für ASP.net Core GrpC-Anwendungen behandelt, die in Docker, Kubernetes oder anderen Container Umgebungen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="66b1e-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="66b1e-105">Die Beispielanwendung, die mit einer ASP.net Core MVC-Web-App und einem GrpC-Dienst verwendet wird, ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66b1e-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="66b1e-106">Microsoft-Basis Images für ASP.net Core Anwendungen</span><span class="sxs-lookup"><span data-stu-id="66b1e-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="66b1e-107">Microsoft bietet eine Reihe von Basis Images zum entwickeln und Ausführen von .net Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="66b1e-108">Zum Erstellen eines ASP.net Core 3,0-Images werden zwei Basis Images verwendet: ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung und ein Lauf Zeit Image für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="66b1e-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="66b1e-109">Bild</span><span class="sxs-lookup"><span data-stu-id="66b1e-109">Image</span></span> | <span data-ttu-id="66b1e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66b1e-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="66b1e-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="66b1e-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="66b1e-112">Zum Entwickeln von Anwendungen mit `docker build`.</span><span class="sxs-lookup"><span data-stu-id="66b1e-112">For building applications with `docker build`.</span></span> <span data-ttu-id="66b1e-113">Nicht zur Verwendung in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="66b1e-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="66b1e-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="66b1e-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="66b1e-115">Enthält die Lauf Zeit-und ASP.net Core Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="66b1e-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="66b1e-116">Für die Produktion.</span><span class="sxs-lookup"><span data-stu-id="66b1e-116">For production.</span></span> |

<span data-ttu-id="66b1e-117">Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren und durch Tags unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="66b1e-118">Imagetag (e)</span><span class="sxs-lookup"><span data-stu-id="66b1e-118">Image tag(s)</span></span> | <span data-ttu-id="66b1e-119">Linux</span><span class="sxs-lookup"><span data-stu-id="66b1e-119">Linux</span></span> | <span data-ttu-id="66b1e-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66b1e-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="66b1e-121">3,0-Buster, 3,0</span><span class="sxs-lookup"><span data-stu-id="66b1e-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="66b1e-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="66b1e-122">Debian 10</span></span> | <span data-ttu-id="66b1e-123">Das Standardbild, wenn keine Betriebssystem Variante angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="66b1e-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="66b1e-124">3,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="66b1e-124">3.0-alpine</span></span> | <span data-ttu-id="66b1e-125">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="66b1e-125">Alpine 3.9</span></span> | <span data-ttu-id="66b1e-126">Alpine Base-Images sind wesentlich kleiner als Debian oder Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="66b1e-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="66b1e-127">3,0-Disco</span><span class="sxs-lookup"><span data-stu-id="66b1e-127">3.0-disco</span></span> | <span data-ttu-id="66b1e-128">Ubuntu 19,04</span><span class="sxs-lookup"><span data-stu-id="66b1e-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="66b1e-129">3,0-Bionic</span><span class="sxs-lookup"><span data-stu-id="66b1e-129">3.0-bionic</span></span> | <span data-ttu-id="66b1e-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="66b1e-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="66b1e-131">Das Alpine Base-Image ist um 100 MB im Vergleich zu 200 MB für die Debian-und Ubuntu-Images, aber einige Softwarepakete oder-Bibliotheken sind in der Alpine-Paketverwaltung möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66b1e-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="66b1e-132">Wenn Sie nicht sicher sind, welches Image verwendet werden soll, ist es am besten, wenn Sie eine andere Distribution verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66b1e-133">Stellen Sie sicher, dass Sie für den Build und die Laufzeit dieselbe Variante von Linux verwenden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="66b1e-134">Anwendungen, die auf einem Variant erstellt und veröffentlicht werden, funktionieren möglicherweise nicht auf einem anderen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="66b1e-135">Erstellen eines docker-Images</span><span class="sxs-lookup"><span data-stu-id="66b1e-135">Create a Docker image</span></span>

<span data-ttu-id="66b1e-136">Ein docker-Image wird durch eine *dockerfile-Datei*definiert. Dies ist eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung benötigt werden, und alle Abhängigkeiten zu installieren, die zum Erstellen oder Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="66b1e-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="66b1e-137">Das folgende Beispiel zeigt die einfachste dockerfile-Datei für eine ASP.net Core 3,0-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="66b1e-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="66b1e-138">Die dockerfile-Datei besteht aus zwei Teilen: der erste verwendet das `sdk` Basis Image, um die Anwendung zu erstellen und zu veröffentlichen. die zweite erstellt ein Lauf Zeit Bild aus der `aspnet` Basis.</span><span class="sxs-lookup"><span data-stu-id="66b1e-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="66b1e-139">Dies liegt daran, dass das `sdk` Abbild ungefähr 900 MB im Vergleich zu etwa 200 MB für das Lauf Zeit Image liegt und der meiste Inhalt zur Laufzeit unnötig ist.</span><span class="sxs-lookup"><span data-stu-id="66b1e-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="66b1e-140">Die Buildschritte</span><span class="sxs-lookup"><span data-stu-id="66b1e-140">The build steps</span></span>

| <span data-ttu-id="66b1e-141">Schritt</span><span class="sxs-lookup"><span data-stu-id="66b1e-141">Step</span></span> | <span data-ttu-id="66b1e-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66b1e-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="66b1e-143">Deklariert das Basis Image und weist den `builder` Alias zu (Weitere Erläuterungen finden Sie im nächsten Abschnitt).</span><span class="sxs-lookup"><span data-stu-id="66b1e-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="66b1e-144">Erstellt das `/src` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="66b1e-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="66b1e-145">Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Bild.</span><span class="sxs-lookup"><span data-stu-id="66b1e-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="66b1e-146">Stellt alle externen Pakete wieder her (ASP.net Core 3,0-Framework ist mit dem SDK vorinstalliert).</span><span class="sxs-lookup"><span data-stu-id="66b1e-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="66b1e-147">Erstellt und veröffentlicht einen Releasebuild.</span><span class="sxs-lookup"><span data-stu-id="66b1e-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="66b1e-148">Beachten Sie, dass das `--runtime`-Flag nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="66b1e-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="66b1e-149">Die Schritte zum Lauf Zeit Image</span><span class="sxs-lookup"><span data-stu-id="66b1e-149">The runtime image steps</span></span>

| <span data-ttu-id="66b1e-150">Schritt</span><span class="sxs-lookup"><span data-stu-id="66b1e-150">Step</span></span> | <span data-ttu-id="66b1e-151">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66b1e-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="66b1e-152">Deklariert ein neues Basis Image.</span><span class="sxs-lookup"><span data-stu-id="66b1e-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="66b1e-153">Erstellt das `/app` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="66b1e-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="66b1e-154">Kopiert die veröffentlichte Anwendung aus dem vorherigen Bild unter Verwendung des `builder` Alias aus der ersten `FROM` Zeile.</span><span class="sxs-lookup"><span data-stu-id="66b1e-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="66b1e-155">Legt den Befehl fest, der beim Starten des Containers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66b1e-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="66b1e-156">Der Befehl `dotnet` im Lauf Zeit Image kann nur DLL-Dateien ausführen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="66b1e-157">HTTPS in docker</span><span class="sxs-lookup"><span data-stu-id="66b1e-157">HTTPS in Docker</span></span>

<span data-ttu-id="66b1e-158">Die Basis Images von Microsoft für docker legen die `ASPNETCORE_URLS`-Umgebungsvariable auf `http://+:80`fest. Dies bedeutet, dass Kestrel ohne HTTPS an diesem Port ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66b1e-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="66b1e-159">Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie im [vorherigen Abschnitt](self-hosted.md)beschrieben), sollten Sie dies überschreiben, indem Sie die Umgebungsvariable **im Rahmen der Lauf Zeit Image Erstellung** der dockerfile-Datei festlegen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="66b1e-160">Die. dockerignore-Datei</span><span class="sxs-lookup"><span data-stu-id="66b1e-160">The .dockerignore file</span></span>

<span data-ttu-id="66b1e-161">Ähnlich wie `.gitignore` Dateien, die bestimmte Dateien und Verzeichnisse aus der Quell Code Verwaltung ausschließen, kann die `.dockerignore` Datei verwendet werden, um zu verhindern, dass Dateien und Verzeichnisse während des Buildvorgangs in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="66b1e-162">Dadurch wird nicht nur Zeit gespart, sondern es können auch einige verwirrende Fehler vermieden werden, die dazu führen, dass (insbesondere) das `obj` Verzeichnis von Ihrem PC in das Abbild kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="66b1e-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="66b1e-163">Sie sollten der `.dockerignore` Datei mindestens Einträge für `bin` und `obj` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="66b1e-164">Erstellen des Images</span><span class="sxs-lookup"><span data-stu-id="66b1e-164">Build the image</span></span>

<span data-ttu-id="66b1e-165">Für eine Lösung mit einer einzelnen Anwendung und somit einer einzelnen dockerfile-Datei ist es am einfachsten, die dockerfile-Datei im Basisverzeichnis zu platzieren. Das heißt, dasselbe Verzeichnis wie die `.sln` Datei.</span><span class="sxs-lookup"><span data-stu-id="66b1e-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="66b1e-166">Verwenden Sie in diesem Fall den folgenden `docker build` Befehl aus dem Verzeichnis mit der dockerfile-Datei, um das Image zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="66b1e-167">Das verwirrende `--tag`-Flag (das auf `-t`verkürzt werden kann) gibt den gesamten Namen des Bilds an, *einschließlich* des tatsächlichen Tags, wenn angegeben.</span><span class="sxs-lookup"><span data-stu-id="66b1e-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="66b1e-168">Der `.` am Ende gibt den *Kontext* an, in dem der Build ausgeführt wird. das aktuelle Arbeitsverzeichnis für die `COPY`-Befehle in der dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="66b1e-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="66b1e-169">Wenn Sie mehrere Anwendungen in einer einzelnen Projekt Mappe haben, können Sie die dockerfile-Datei für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren, aber Sie sollten trotzdem den `docker build` Befehl aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projekt Mappe und alle Projekte in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="66b1e-170">Sie können eine dockerfile-Datei unterhalb des aktuellen Verzeichnisses angeben, indem Sie das `--file`-Flag (oder `-f`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="66b1e-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="66b1e-171">Ausführen des Images in einem Container auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="66b1e-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="66b1e-172">Verwenden Sie den Befehl `docker run`, um das Image in der lokalen docker-Instanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="66b1e-173">Das `-ti`-Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="66b1e-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="66b1e-174">Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 im Container an Port 80 auf der localhost-Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="66b1e-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="66b1e-175">Übertragung des Images per Push in eine Registrierung</span><span class="sxs-lookup"><span data-stu-id="66b1e-175">Push the image to a registry</span></span>

<span data-ttu-id="66b1e-176">Nachdem Sie überprüft haben, ob das Image funktioniert, müssen Sie es per Push an eine docker-Registrierung überführen, damit es auf anderen Systemen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="66b1e-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="66b1e-177">Interne Netzwerke müssen eine docker-Registrierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="66b1e-178">Dies kann so einfach sein wie das Ausführen [des eigenen `registry` Images von Docker](https://docs.docker.com/registry/deploying/) (die Docker-Registrierung wird in einem docker-Container ausgeführt), es gibt jedoch verschiedene umfassendere Lösungen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="66b1e-179">Für die externe Freigabe und die cloudnutzung stehen verschiedene verwaltete Registrierungen zur Verfügung, z. b. [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) oder [docker Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="66b1e-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="66b1e-180">Um per Push an den docker-Hub zu übernehmen, stellen Sie dem Image Namen den Namen Ihres Benutzers oder Ihrer Organisation voran.</span><span class="sxs-lookup"><span data-stu-id="66b1e-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="66b1e-181">Um per Push in eine private Registrierung zu übernehmen, stellen Sie dem Image Namen den Namen des Registrierungs Hosts und den Organisationsnamen voran.</span><span class="sxs-lookup"><span data-stu-id="66b1e-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="66b1e-182">Sobald sich das Image in einer Registrierung befindet, können Sie es auf einzelnen docker-Hosts oder in einer Container Orchestrierungs-Engine wie Kubernetes bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="66b1e-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="66b1e-183">[Zurück](self-hosted.md)
>[Weiter](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="66b1e-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
