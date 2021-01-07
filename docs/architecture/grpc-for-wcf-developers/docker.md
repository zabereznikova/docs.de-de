---
title: Docker-GrpC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.net Core GrpC-Anwendungen
ms.date: 01/06/2021
ms.openlocfilehash: f59518a28b0a1dee75c792ba03bd4af826638502
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970088"
---
# <a name="create-docker-images"></a><span data-ttu-id="852b1-103">Erstellen von Docker-Images</span><span class="sxs-lookup"><span data-stu-id="852b1-103">Create Docker images</span></span>

<span data-ttu-id="852b1-104">In diesem Abschnitt wird die Erstellung von Docker-Images für ASP.net Core GrpC-Anwendungen behandelt, die in Docker, Kubernetes oder anderen Container Umgebungen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="852b1-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="852b1-105">Die Beispielanwendung, die mit einer ASP.net Core MVC-Web-App und einem GrpC-Dienst verwendet wird, ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="852b1-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="852b1-106">Microsoft-Basis Images für ASP.net Core Anwendungen</span><span class="sxs-lookup"><span data-stu-id="852b1-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="852b1-107">Microsoft bietet eine Reihe von Basis Images zum entwickeln und Ausführen von .NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="852b1-107">Microsoft provides a range of base images for building and running .NET applications.</span></span> <span data-ttu-id="852b1-108">Zum Erstellen eines ASP.net Core 5,0-Abbilds verwenden Sie zwei Basis Images:</span><span class="sxs-lookup"><span data-stu-id="852b1-108">To create an ASP.NET Core 5.0 image, you use two base images:</span></span>

- <span data-ttu-id="852b1-109">Ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="852b1-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="852b1-110">Ein Lauf Zeit Image für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="852b1-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="852b1-111">Image</span><span class="sxs-lookup"><span data-stu-id="852b1-111">Image</span></span> | <span data-ttu-id="852b1-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="852b1-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="852b1-113">mcr.microsoft.com/dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="852b1-113">mcr.microsoft.com/dotnet/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-sdk/) | <span data-ttu-id="852b1-114">Zum Entwickeln von Anwendungen mit `docker build` .</span><span class="sxs-lookup"><span data-stu-id="852b1-114">For building applications with `docker build`.</span></span> <span data-ttu-id="852b1-115">Nicht zur Verwendung in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="852b1-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="852b1-116">mcr.microsoft.com/dotnet/aspnet</span><span class="sxs-lookup"><span data-stu-id="852b1-116">mcr.microsoft.com/dotnet/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | <span data-ttu-id="852b1-117">Enthält die Lauf Zeit-und ASP.net Core Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="852b1-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="852b1-118">Für Produktionszwecke.</span><span class="sxs-lookup"><span data-stu-id="852b1-118">For production.</span></span> |

<span data-ttu-id="852b1-119">Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren und durch Tags unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="852b1-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="852b1-120">Imagetag (e)</span><span class="sxs-lookup"><span data-stu-id="852b1-120">Image tag(s)</span></span> | <span data-ttu-id="852b1-121">Linux</span><span class="sxs-lookup"><span data-stu-id="852b1-121">Linux</span></span> | <span data-ttu-id="852b1-122">Notizen</span><span class="sxs-lookup"><span data-stu-id="852b1-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="852b1-123">5,0-Buster-schlank, 5,0</span><span class="sxs-lookup"><span data-stu-id="852b1-123">5.0-buster-slim, 5.0</span></span> | <span data-ttu-id="852b1-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="852b1-124">Debian 10</span></span> | <span data-ttu-id="852b1-125">Das Standardbild, wenn keine Betriebssystem Variante angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="852b1-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="852b1-126">5,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="852b1-126">5.0-alpine</span></span> | <span data-ttu-id="852b1-127">Alpine 3,12</span><span class="sxs-lookup"><span data-stu-id="852b1-127">Alpine 3.12</span></span> | <span data-ttu-id="852b1-128">Alpine Base-Images sind wesentlich kleiner als Debian oder Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="852b1-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="852b1-129">5,0-Fokus</span><span class="sxs-lookup"><span data-stu-id="852b1-129">5.0-focal</span></span>| <span data-ttu-id="852b1-130">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="852b1-130">Ubuntu 20.04</span></span> | |

<span data-ttu-id="852b1-131">Das Alpine Base-Image ist um 100 MB im Vergleich zu 200 MB für die Debian-und Ubuntu-Images.</span><span class="sxs-lookup"><span data-stu-id="852b1-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="852b1-132">Einige Softwarepakete oder-Bibliotheken sind in der Alpine-Paketverwaltung möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="852b1-132">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="852b1-133">Wenn Sie nicht sicher sind, welches Image verwendet werden soll, sollten Sie wahrscheinlich das standardmäßige Debian auswählen.</span><span class="sxs-lookup"><span data-stu-id="852b1-133">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="852b1-134">Stellen Sie sicher, dass Sie für den Build und die Laufzeit dieselbe Variante von Linux verwenden.</span><span class="sxs-lookup"><span data-stu-id="852b1-134">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="852b1-135">Anwendungen, die auf einem Variant erstellt und veröffentlicht werden, funktionieren möglicherweise nicht auf einem anderen.</span><span class="sxs-lookup"><span data-stu-id="852b1-135">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="852b1-136">Erstellen eines Docker-Image</span><span class="sxs-lookup"><span data-stu-id="852b1-136">Create a Docker image</span></span>

<span data-ttu-id="852b1-137">Ein docker-Image wird durch eine *dockerfile-Datei* definiert.</span><span class="sxs-lookup"><span data-stu-id="852b1-137">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="852b1-138">Bei dieser *dockerfile-Datei* handelt es sich um eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung und zum Installieren von Abhängigkeiten erforderlich sind, die zum Erstellen oder Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="852b1-138">This *Dockerfile* is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="852b1-139">Das folgende Beispiel zeigt die einfachste dockerfile-Datei für eine ASP.net Core 5,0-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="852b1-139">The following example shows the simplest Dockerfile for an ASP.NET Core 5.0 application:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="852b1-140">Die dockerfile-Datei besteht aus zwei Teilen: der erste verwendet das `sdk` Basis Image, um die Anwendung zu erstellen und zu veröffentlichen. das zweite erstellt ein Lauf Zeit Image aus der `aspnet` Basis.</span><span class="sxs-lookup"><span data-stu-id="852b1-140">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="852b1-141">Dies liegt daran, dass das `sdk` Image ungefähr 900 MB groß ist, im Vergleich zu etwa 200 MB für das Lauf Zeit Image, und der meiste Inhalt ist zur Laufzeit unnötig.</span><span class="sxs-lookup"><span data-stu-id="852b1-141">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="852b1-142">Die Buildschritte</span><span class="sxs-lookup"><span data-stu-id="852b1-142">The build steps</span></span>

| <span data-ttu-id="852b1-143">Schritt</span><span class="sxs-lookup"><span data-stu-id="852b1-143">Step</span></span> | <span data-ttu-id="852b1-144">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="852b1-144">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="852b1-145">Deklariert das Basis Image und weist den `builder` Alias zu.</span><span class="sxs-lookup"><span data-stu-id="852b1-145">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="852b1-146">Erstellt das `/src` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="852b1-146">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="852b1-147">Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Bild.</span><span class="sxs-lookup"><span data-stu-id="852b1-147">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="852b1-148">Stellt alle externen Pakete wieder her (ASP.net Core 3,0-Framework ist mit dem SDK vorinstalliert).</span><span class="sxs-lookup"><span data-stu-id="852b1-148">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="852b1-149">Erstellt und veröffentlicht einen Releasebuild.</span><span class="sxs-lookup"><span data-stu-id="852b1-149">Builds and publishes a Release build.</span></span> <span data-ttu-id="852b1-150">Beachten Sie, dass das- `--runtime` Flag nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="852b1-150">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="852b1-151">Die Schritte zum Lauf Zeit Image</span><span class="sxs-lookup"><span data-stu-id="852b1-151">The runtime image steps</span></span>

| <span data-ttu-id="852b1-152">Schritt</span><span class="sxs-lookup"><span data-stu-id="852b1-152">Step</span></span> | <span data-ttu-id="852b1-153">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="852b1-153">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="852b1-154">Deklariert ein neues Basis Image.</span><span class="sxs-lookup"><span data-stu-id="852b1-154">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="852b1-155">Erstellt das `/app` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="852b1-155">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="852b1-156">Kopiert die veröffentlichte Anwendung aus dem vorherigen Bild mithilfe des `builder` Alias aus der ersten `FROM` Zeile.</span><span class="sxs-lookup"><span data-stu-id="852b1-156">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="852b1-157">Legt den Befehl fest, der beim Starten des Containers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="852b1-157">Sets the command to run when the container starts.</span></span> <span data-ttu-id="852b1-158">Der `dotnet` Befehl im Lauf Zeit Image kann nur DLL-Dateien ausführen.</span><span class="sxs-lookup"><span data-stu-id="852b1-158">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="852b1-159">HTTPS in docker</span><span class="sxs-lookup"><span data-stu-id="852b1-159">HTTPS in Docker</span></span>

<span data-ttu-id="852b1-160">Microsoft Base Images für docker legen die `ASPNETCORE_URLS` Umgebungsvariable auf fest `http://+:80` . Dies bedeutet, dass Kestrel ohne HTTPS an diesem Port ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="852b1-160">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="852b1-161">Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie in [selbstgeh osteten GrpC-Anwendungen](self-hosted.md)beschrieben), sollten Sie diese Konfiguration außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="852b1-161">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this configuration.</span></span> <span data-ttu-id="852b1-162">Legen Sie die Umgebungsvariable im Rahmen der Lauf Zeit Image Erstellung der dockerfile-Datei fest.</span><span class="sxs-lookup"><span data-stu-id="852b1-162">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="852b1-163">Die. dockerignore-Datei</span><span class="sxs-lookup"><span data-stu-id="852b1-163">The .dockerignore file</span></span>

<span data-ttu-id="852b1-164">Ähnlich wie `.gitignore` Dateien, die bestimmte Dateien und Verzeichnisse aus der Quell Code Verwaltung ausschließen, `.dockerignore` kann die Datei verwendet werden, um Dateien und Verzeichnisse auszuschließen, die während des Buildvorgangs in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="852b1-164">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="852b1-165">Diese Datei spart nicht nur Zeit, das kopiert werden kann, sondern kann auch einige Fehler vermeiden, die dazu führen, dass das `obj` Verzeichnis von Ihrem PC in das Abbild kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="852b1-165">This file not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="852b1-166">Sie sollten der Datei mindestens Einträge für und hinzu `bin` fügen `obj` `.dockerignore` .</span><span class="sxs-lookup"><span data-stu-id="852b1-166">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="852b1-167">Erstellen des Image</span><span class="sxs-lookup"><span data-stu-id="852b1-167">Build the image</span></span>

<span data-ttu-id="852b1-168">Für eine `StockKube.sln` Lösung, die zwei verschiedene Anwendungen `StockData` und enthält `StockWeb` , ist es am einfachsten, die dockerfile-Datei für jede dieser Dateien im Basisverzeichnis zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="852b1-168">For a `StockKube.sln` solution containing two different applications `StockData` and `StockWeb`, it's simplest to put the Dockerfile for each one of them in the base directory.</span></span> <span data-ttu-id="852b1-169">Verwenden Sie in diesem Fall den folgenden Befehl aus dem Verzeichnis, in dem sich die Datei befindet, um das Image zu erstellen `docker build` `.sln` .</span><span class="sxs-lookup"><span data-stu-id="852b1-169">In that case, to build the image, use the following `docker build` command from the same directory where `.sln` file resides.</span></span>

```console
docker build -t stockdata:1.0.0 -f ./src/StockData/Dockerfile .
```

<span data-ttu-id="852b1-170">Das verwirrend benannte `--tag` Flag (das auf gekürzt werden kann `-t` ) gibt den vollständigen Namen des Bilds an, einschließlich des tatsächlichen Tags, wenn angegeben.</span><span class="sxs-lookup"><span data-stu-id="852b1-170">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="852b1-171">Der `.` am Ende gibt den Kontext an, in dem der Build ausgeführt wird, das aktuelle Arbeitsverzeichnis für die `COPY` Befehle in der dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="852b1-171">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="852b1-172">Wenn Sie mehrere Anwendungen in einer einzelnen Projekt Mappe haben, können Sie die dockerfile-Datei für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="852b1-172">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="852b1-173">Sie sollten weiterhin den `docker build` Befehl aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projekt Mappe und alle Projekte in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="852b1-173">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="852b1-174">Sie können eine dockerfile-Datei unterhalb des aktuellen Verzeichnisses angeben, indem Sie das- `--file` Flag (oder `-f` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="852b1-174">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build -t stockdata:1.0.0 -f ./src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="852b1-175">Ausführen des Images in einem Container auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="852b1-175">Run the image in a container on your machine</span></span>

<span data-ttu-id="852b1-176">Verwenden Sie den Befehl, um das Image in der lokalen docker-Instanz auszuführen `docker run` .</span><span class="sxs-lookup"><span data-stu-id="852b1-176">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

<span data-ttu-id="852b1-177">Das `-ti` -Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="852b1-177">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="852b1-178">Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 für den Container an Port 5000 auf der localhost-Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="852b1-178">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="852b1-179">Pushen des Images in eine Registrierung</span><span class="sxs-lookup"><span data-stu-id="852b1-179">Push the image to a registry</span></span>

<span data-ttu-id="852b1-180">Nachdem Sie überprüft haben, ob das Image funktioniert, überführen Sie es per Push an eine docker-Registrierung, um es auf anderen Systemen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="852b1-180">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="852b1-181">Interne Netzwerke müssen eine docker-Registrierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="852b1-181">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="852b1-182">Diese Aktivität kann so einfach sein wie das Ausführen [des eigenen `registry` Images von Docker](https://docs.docker.com/registry/deploying/) (die Docker-Registrierung wird in einem docker-Container ausgeführt), es sind jedoch verschiedene umfassendere Lösungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="852b1-182">This activity can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="852b1-183">Für die externe Freigabe und die cloudnutzung stehen verschiedene verwaltete Registrierungen zur Verfügung, z. b. [Azure Container Registry](/azure/container-registry/) oder [docker Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="852b1-183">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="852b1-184">Um per Push an docker Hub zu übernehmen, stellen Sie dem Image Namen den Namen Ihres Benutzers oder Ihrer Organisation voran.</span><span class="sxs-lookup"><span data-stu-id="852b1-184">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

<span data-ttu-id="852b1-185">Um per Push in eine private Registrierung zu übernehmen, stellen Sie dem Image Namen den Namen des Registrierungs Hosts und den Organisationsnamen voran.</span><span class="sxs-lookup"><span data-stu-id="852b1-185">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

<span data-ttu-id="852b1-186">Nachdem sich das Image in einer Registrierung befindet, können Sie es auf einzelnen docker-Hosts oder in einer Container Orchestrierungs-Engine wie Kubernetes bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="852b1-186">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="852b1-187">[Zurück](self-hosted.md)
>[Weiter](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="852b1-187">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
