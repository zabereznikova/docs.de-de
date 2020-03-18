---
title: Docker - gRPC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.NET Core-gRPC-Anwendungen
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148113"
---
# <a name="create-docker-images"></a><span data-ttu-id="c8343-103">Erstellen von Docker-Images</span><span class="sxs-lookup"><span data-stu-id="c8343-103">Create Docker images</span></span>

<span data-ttu-id="c8343-104">In diesem Abschnitt werden die Erstellung von Docker-Images für ASP.NET Core-gRPC-Anwendungen behandelt, die in Docker-, Kubernetes- oder anderen Containerumgebungen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c8343-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="c8343-105">Die verwendete Beispielanwendung mit einer ASP.NET Core MVC-Web-App und einem gRPC-Dienst ist im [Repository dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8343-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="c8343-106">Microsoft-Basisbilder für ASP.NET-Kernanwendungen</span><span class="sxs-lookup"><span data-stu-id="c8343-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="c8343-107">Microsoft bietet eine Reihe von Basisabbildern zum Erstellen und Ausführen von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="c8343-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="c8343-108">Um ein ASP.NET Core 3.0-Bild zu erstellen, verwenden Sie zwei Basisbilder:</span><span class="sxs-lookup"><span data-stu-id="c8343-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="c8343-109">Ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c8343-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="c8343-110">Ein Laufzeitabbild für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="c8343-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="c8343-111">Image</span><span class="sxs-lookup"><span data-stu-id="c8343-111">Image</span></span> | <span data-ttu-id="c8343-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8343-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="c8343-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="c8343-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="c8343-114">Für Gebäudeanwendungen `docker build`mit .</span><span class="sxs-lookup"><span data-stu-id="c8343-114">For building applications with `docker build`.</span></span> <span data-ttu-id="c8343-115">Nicht in der Produktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8343-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="c8343-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="c8343-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="c8343-117">Enthält die Laufzeit- und ASP.NET Core-Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="c8343-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="c8343-118">Für die Produktion.</span><span class="sxs-lookup"><span data-stu-id="c8343-118">For production.</span></span> |

<span data-ttu-id="c8343-119">Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren, die sich durch Tags unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c8343-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="c8343-120">Bild-Tag(e)</span><span class="sxs-lookup"><span data-stu-id="c8343-120">Image tag(s)</span></span> | <span data-ttu-id="c8343-121">Linux</span><span class="sxs-lookup"><span data-stu-id="c8343-121">Linux</span></span> | <span data-ttu-id="c8343-122">Notizen</span><span class="sxs-lookup"><span data-stu-id="c8343-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="c8343-123">3,0-Buster, 3,0</span><span class="sxs-lookup"><span data-stu-id="c8343-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="c8343-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="c8343-124">Debian 10</span></span> | <span data-ttu-id="c8343-125">Das Standardabbild, wenn keine Betriebssystemvariante angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c8343-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="c8343-126">3.0-alpin</span><span class="sxs-lookup"><span data-stu-id="c8343-126">3.0-alpine</span></span> | <span data-ttu-id="c8343-127">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="c8343-127">Alpine 3.9</span></span> | <span data-ttu-id="c8343-128">Alpine Basis-Images sind viel kleiner als Debian- oder Ubuntu-Images.</span><span class="sxs-lookup"><span data-stu-id="c8343-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="c8343-129">3.0-Disco</span><span class="sxs-lookup"><span data-stu-id="c8343-129">3.0-disco</span></span> | <span data-ttu-id="c8343-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="c8343-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="c8343-131">3.0-bionic</span><span class="sxs-lookup"><span data-stu-id="c8343-131">3.0-bionic</span></span> | <span data-ttu-id="c8343-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="c8343-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="c8343-133">Das Alpine-Basis-Image beträgt etwa 100 MB, verglichen mit 200 MB für die Debian- und Ubuntu-Images.</span><span class="sxs-lookup"><span data-stu-id="c8343-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="c8343-134">Einige Softwarepakete oder Bibliotheken sind möglicherweise nicht in der Paketverwaltung von Alpine verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8343-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="c8343-135">Wenn Sie nicht sicher sind, welches Image Sie verwenden sollen, sollten Sie wahrscheinlich das Standard-Debian wählen.</span><span class="sxs-lookup"><span data-stu-id="c8343-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8343-136">Stellen Sie sicher, dass Sie die gleiche Linux-Variante für den Build und die Laufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8343-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="c8343-137">Anwendungen, die für eine Variante erstellt und veröffentlicht wurden, funktionieren möglicherweise nicht auf einer anderen.</span><span class="sxs-lookup"><span data-stu-id="c8343-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="c8343-138">Erstellen eines Docker-Image</span><span class="sxs-lookup"><span data-stu-id="c8343-138">Create a Docker image</span></span>

<span data-ttu-id="c8343-139">Ein Docker-Image wird durch eine *Dockerfile*definiert.</span><span class="sxs-lookup"><span data-stu-id="c8343-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="c8343-140">Dies ist eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung und zum Installieren aller Abhängigkeiten erforderlich sind, die zum Erstellen oder Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c8343-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="c8343-141">Das folgende Beispiel zeigt die einfachste Dockerfile-Datei für eine ASP.NET Core 3.0-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="c8343-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="c8343-142">Die Dockerfile besteht aus zwei `sdk` Teilen: Der erste verwendet das Basisabbild, um die Anwendung zu erstellen und zu veröffentlichen. die zweite erstellt ein Laufzeitbild von der `aspnet` Basis aus.</span><span class="sxs-lookup"><span data-stu-id="c8343-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="c8343-143">Dies liegt `sdk` daran, dass das Abbild etwa 900 MB groß ist, verglichen mit etwa 200 MB für das Laufzeitabbild, und der größte Teil seines Inhalts zur Laufzeit nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c8343-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="c8343-144">Die Buildschritte</span><span class="sxs-lookup"><span data-stu-id="c8343-144">The build steps</span></span>

| <span data-ttu-id="c8343-145">Schritt</span><span class="sxs-lookup"><span data-stu-id="c8343-145">Step</span></span> | <span data-ttu-id="c8343-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8343-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="c8343-147">Deklariert das Basisbild und `builder` weist den Alias zu.</span><span class="sxs-lookup"><span data-stu-id="c8343-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="c8343-148">Erstellt `/src` das Verzeichnis und legt es als aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="c8343-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="c8343-149">Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Image.</span><span class="sxs-lookup"><span data-stu-id="c8343-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="c8343-150">Stellt alle externen Pakete wieder her (ASP.NET Core 3.0-Framework ist mit dem SDK vorinstalliert).</span><span class="sxs-lookup"><span data-stu-id="c8343-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="c8343-151">Erstellt und veröffentlicht einen Release-Build.</span><span class="sxs-lookup"><span data-stu-id="c8343-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="c8343-152">Beachten Sie, dass das `--runtime` Flag nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c8343-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="c8343-153">Die Laufzeitbildschritte</span><span class="sxs-lookup"><span data-stu-id="c8343-153">The runtime image steps</span></span>

| <span data-ttu-id="c8343-154">Schritt</span><span class="sxs-lookup"><span data-stu-id="c8343-154">Step</span></span> | <span data-ttu-id="c8343-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8343-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="c8343-156">Deklariert ein neues Basisbild.</span><span class="sxs-lookup"><span data-stu-id="c8343-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="c8343-157">Erstellt `/app` das Verzeichnis und legt es als aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="c8343-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="c8343-158">Kopiert die veröffentlichte Anwendung aus dem `builder` vorherigen Bild, `FROM` indem der Alias aus der ersten Zeile verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8343-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="c8343-159">Legt fest, dass der Befehl ausgeführt wird, wenn der Container gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c8343-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="c8343-160">Der `dotnet` Befehl im Laufzeitabbild kann nur DLL-Dateien ausführen.</span><span class="sxs-lookup"><span data-stu-id="c8343-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="c8343-161">HTTPS in Docker</span><span class="sxs-lookup"><span data-stu-id="c8343-161">HTTPS in Docker</span></span>

<span data-ttu-id="c8343-162">Microsoft-Basisabbilder für `ASPNETCORE_URLS` Docker `http://+:80`legen die Umgebungsvariable auf fest, d. h., Kestrel wird ohne HTTPS auf diesem Port ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8343-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="c8343-163">Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie in [selbstgehosteten gRPC-Anwendungen](self-hosted.md)beschrieben), sollten Sie dies überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c8343-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="c8343-164">Legen Sie die Umgebungsvariable im Laufzeitbilderstellungsteil Ihrer Dockerfile fest.</span><span class="sxs-lookup"><span data-stu-id="c8343-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="c8343-165">Die .dockerignore-Datei</span><span class="sxs-lookup"><span data-stu-id="c8343-165">The .dockerignore file</span></span>

<span data-ttu-id="c8343-166">Ähnlich `.gitignore` wie Dateien, die bestimmte Dateien und `.dockerignore` Verzeichnisse aus der Quellcodeverwaltung ausschließen, kann die Datei verwendet werden, um dateien- und Verzeichnisse davon auszuschließen, während des Builds in das Bild kopiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="c8343-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="c8343-167">Dies spart nicht nur Zeit beim Kopieren, sondern `obj` kann auch einige Fehler vermeiden, die entstehen, wenn das Verzeichnis von Ihrem PC in das Bild kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="c8343-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="c8343-168">Sie sollten mindestens Einträge für `bin` `obj` und `.dockerignore` zu Ihrer Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8343-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="c8343-169">Erstellen des Image</span><span class="sxs-lookup"><span data-stu-id="c8343-169">Build the image</span></span>

<span data-ttu-id="c8343-170">Für eine Lösung mit einer einzelnen Anwendung und damit einer einzelnen Dockerfile ist es am einfachsten, die Dockerfile im Basisverzeichnis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c8343-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="c8343-171">Mit anderen Worten, legen Sie es `.sln` in das gleiche Verzeichnis wie die Datei.</span><span class="sxs-lookup"><span data-stu-id="c8343-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="c8343-172">Verwenden Sie in diesem Fall zum `docker build` Erstellen des Images den folgenden Befehl aus dem Verzeichnis, das die Dockerfile enthält.</span><span class="sxs-lookup"><span data-stu-id="c8343-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="c8343-173">Das verwirrend `--tag` benannte Flag (das `-t`auf gekürzt werden kann) gibt den gesamten Namen des Bildes an, einschließlich des tatsächlichen Tags, falls angegeben.</span><span class="sxs-lookup"><span data-stu-id="c8343-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="c8343-174">Der `.` am Ende gibt den Kontext an, in dem der Build ausgeführt wird. das aktuelle Arbeitsverzeichnis `COPY` für die Befehle in der Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="c8343-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="c8343-175">Wenn Sie mehrere Anwendungen in einer einzigen Lösung haben, können Sie die Dockerfile für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="c8343-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="c8343-176">Sie sollten den `docker build` Befehl weiterhin aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projektmappe und alle Projekte in das Abbild kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8343-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="c8343-177">Sie können eine Dockerfile unterhalb des `--file` aktuellen `-f`Verzeichnisses angeben, indem Sie das Flag (oder ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8343-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="c8343-178">Ausführen des Images in einem Container auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="c8343-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="c8343-179">Verwenden Sie den `docker run` Befehl, um das Image in Ihrer lokalen Docker-Instanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c8343-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="c8343-180">Das `-ti` Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c8343-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="c8343-181">Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 auf dem Container zu Port 5000 auf der lokalen Host-Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c8343-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="c8343-182">Pushen des Images in eine Registrierung</span><span class="sxs-lookup"><span data-stu-id="c8343-182">Push the image to a registry</span></span>

<span data-ttu-id="c8343-183">Nachdem Sie überprüft haben, ob das Image funktioniert, übertragen Sie es an eine Docker-Registrierung, um es auf anderen Systemen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="c8343-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="c8343-184">Interne Netzwerke müssen eine Docker-Registrierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8343-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="c8343-185">Dies kann so einfach sein wie das [Ausführen des eigenen `registry` Images](https://docs.docker.com/registry/deploying/) von Docker (die Docker-Registrierung wird in einem Docker-Container ausgeführt), aber es stehen verschiedene umfassendere Lösungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c8343-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="c8343-186">Für die externe Freigabe und Cloudnutzung stehen verschiedene verwaltete Registrierungsstellen zur Verfügung, z. B. [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) oder Docker [Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="c8343-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="c8343-187">Um einen Push-Code an Docker Hub zu übertragen, setzen Sie dem Imagenamen den Namen Ihres Benutzers oder Ihrer Organisation voran.</span><span class="sxs-lookup"><span data-stu-id="c8343-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="c8343-188">Um einen Push zu einer privaten Registrierung zu erstellen, setzen Sie dem Imagenamen den Namen des Registrierungshosts und den Organisationsnamen voran.</span><span class="sxs-lookup"><span data-stu-id="c8343-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="c8343-189">Nachdem sich das Image in einer Registrierung befindet, können Sie es auf einzelnen Docker-Hosts oder in einem Containerorchestrierungsmodul wie Kubernetes bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c8343-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c8343-190">[VorherigeS](self-hosted.md)
>[Weiter](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="c8343-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
