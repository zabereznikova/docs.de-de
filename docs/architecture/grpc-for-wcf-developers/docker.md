---
title: Docker-GrpC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.net Core GrpC-Anwendungen
ms.date: 09/02/2019
ms.openlocfilehash: 0a680d0918868829042e521506fa8c1a1628bf5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688444"
---
# <a name="create-docker-images"></a><span data-ttu-id="0c02a-103">Erstellen von Docker-Images</span><span class="sxs-lookup"><span data-stu-id="0c02a-103">Create Docker images</span></span>

<span data-ttu-id="0c02a-104">In diesem Abschnitt wird die Erstellung von Docker-Images für ASP.net Core GrpC-Anwendungen behandelt, die in Docker, Kubernetes oder anderen Container Umgebungen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="0c02a-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="0c02a-105">Die Beispielanwendung, die mit einer ASP.net Core MVC-Web-App und einem GrpC-Dienst verwendet wird, ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c02a-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="0c02a-106">Microsoft-Basis Images für ASP.net Core Anwendungen</span><span class="sxs-lookup"><span data-stu-id="0c02a-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="0c02a-107">Microsoft bietet eine Reihe von Basis Images zum entwickeln und Ausführen von .net Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="0c02a-108">Zum Erstellen eines ASP.net Core 3,0-Abbilds verwenden Sie zwei Basis Images:</span><span class="sxs-lookup"><span data-stu-id="0c02a-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="0c02a-109">Ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0c02a-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="0c02a-110">Ein Lauf Zeit Image für die Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="0c02a-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="0c02a-111">Bild</span><span class="sxs-lookup"><span data-stu-id="0c02a-111">Image</span></span> | <span data-ttu-id="0c02a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c02a-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="0c02a-113">mcr.microsoft.com/dotnet/sdk</span><span class="sxs-lookup"><span data-stu-id="0c02a-113">mcr.microsoft.com/dotnet/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-sdk/) | <span data-ttu-id="0c02a-114">Zum Entwickeln von Anwendungen mit `docker build` .</span><span class="sxs-lookup"><span data-stu-id="0c02a-114">For building applications with `docker build`.</span></span> <span data-ttu-id="0c02a-115">Nicht zur Verwendung in der Produktion.</span><span class="sxs-lookup"><span data-stu-id="0c02a-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="0c02a-116">mcr.microsoft.com/dotnet/aspnet</span><span class="sxs-lookup"><span data-stu-id="0c02a-116">mcr.microsoft.com/dotnet/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | <span data-ttu-id="0c02a-117">Enthält die Lauf Zeit-und ASP.net Core Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="0c02a-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="0c02a-118">Für Produktionszwecke.</span><span class="sxs-lookup"><span data-stu-id="0c02a-118">For production.</span></span> |

<span data-ttu-id="0c02a-119">Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren und durch Tags unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="0c02a-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="0c02a-120">Imagetag (e)</span><span class="sxs-lookup"><span data-stu-id="0c02a-120">Image tag(s)</span></span> | <span data-ttu-id="0c02a-121">Linux</span><span class="sxs-lookup"><span data-stu-id="0c02a-121">Linux</span></span> | <span data-ttu-id="0c02a-122">Notizen</span><span class="sxs-lookup"><span data-stu-id="0c02a-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="0c02a-123">3,0-Buster, 3,0</span><span class="sxs-lookup"><span data-stu-id="0c02a-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="0c02a-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="0c02a-124">Debian 10</span></span> | <span data-ttu-id="0c02a-125">Das Standardbild, wenn keine Betriebssystem Variante angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="0c02a-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="0c02a-126">3,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="0c02a-126">3.0-alpine</span></span> | <span data-ttu-id="0c02a-127">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="0c02a-127">Alpine 3.9</span></span> | <span data-ttu-id="0c02a-128">Alpine Base-Images sind wesentlich kleiner als Debian oder Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="0c02a-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="0c02a-129">3,0-Disco</span><span class="sxs-lookup"><span data-stu-id="0c02a-129">3.0-disco</span></span> | <span data-ttu-id="0c02a-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="0c02a-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="0c02a-131">3,0-Bionic</span><span class="sxs-lookup"><span data-stu-id="0c02a-131">3.0-bionic</span></span> | <span data-ttu-id="0c02a-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="0c02a-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="0c02a-133">Das Alpine Base-Image ist um 100 MB im Vergleich zu 200 MB für die Debian-und Ubuntu-Images.</span><span class="sxs-lookup"><span data-stu-id="0c02a-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="0c02a-134">Einige Softwarepakete oder-Bibliotheken sind in der Alpine-Paketverwaltung möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c02a-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="0c02a-135">Wenn Sie nicht sicher sind, welches Image verwendet werden soll, sollten Sie wahrscheinlich das standardmäßige Debian auswählen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c02a-136">Stellen Sie sicher, dass Sie für den Build und die Laufzeit dieselbe Variante von Linux verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c02a-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="0c02a-137">Anwendungen, die auf einem Variant erstellt und veröffentlicht werden, funktionieren möglicherweise nicht auf einem anderen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="0c02a-138">Erstellen eines Docker-Image</span><span class="sxs-lookup"><span data-stu-id="0c02a-138">Create a Docker image</span></span>

<span data-ttu-id="0c02a-139">Ein docker-Image wird durch eine *dockerfile-Datei* definiert.</span><span class="sxs-lookup"><span data-stu-id="0c02a-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="0c02a-140">Dabei handelt es sich um eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung und zum Installieren von Abhängigkeiten erforderlich sind, die zum Erstellen oder Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0c02a-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="0c02a-141">Das folgende Beispiel zeigt die einfachste dockerfile-Datei für eine ASP.net Core 3,0-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="0c02a-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="0c02a-142">Die dockerfile-Datei besteht aus zwei Teilen: der erste verwendet das `sdk` Basis Image, um die Anwendung zu erstellen und zu veröffentlichen. das zweite erstellt ein Lauf Zeit Image aus der `aspnet` Basis.</span><span class="sxs-lookup"><span data-stu-id="0c02a-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="0c02a-143">Dies liegt daran, dass das `sdk` Image ungefähr 900 MB groß ist, im Vergleich zu etwa 200 MB für das Lauf Zeit Image, und der meiste Inhalt ist zur Laufzeit unnötig.</span><span class="sxs-lookup"><span data-stu-id="0c02a-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="0c02a-144">Die Buildschritte</span><span class="sxs-lookup"><span data-stu-id="0c02a-144">The build steps</span></span>

| <span data-ttu-id="0c02a-145">Schritt</span><span class="sxs-lookup"><span data-stu-id="0c02a-145">Step</span></span> | <span data-ttu-id="0c02a-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c02a-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="0c02a-147">Deklariert das Basis Image und weist den `builder` Alias zu.</span><span class="sxs-lookup"><span data-stu-id="0c02a-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="0c02a-148">Erstellt das `/src` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="0c02a-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="0c02a-149">Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Bild.</span><span class="sxs-lookup"><span data-stu-id="0c02a-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="0c02a-150">Stellt alle externen Pakete wieder her (ASP.net Core 3,0-Framework ist mit dem SDK vorinstalliert).</span><span class="sxs-lookup"><span data-stu-id="0c02a-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="0c02a-151">Erstellt und veröffentlicht einen Releasebuild.</span><span class="sxs-lookup"><span data-stu-id="0c02a-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="0c02a-152">Beachten Sie, dass das- `--runtime` Flag nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0c02a-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="0c02a-153">Die Schritte zum Lauf Zeit Image</span><span class="sxs-lookup"><span data-stu-id="0c02a-153">The runtime image steps</span></span>

| <span data-ttu-id="0c02a-154">Schritt</span><span class="sxs-lookup"><span data-stu-id="0c02a-154">Step</span></span> | <span data-ttu-id="0c02a-155">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c02a-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="0c02a-156">Deklariert ein neues Basis Image.</span><span class="sxs-lookup"><span data-stu-id="0c02a-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="0c02a-157">Erstellt das `/app` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="0c02a-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="0c02a-158">Kopiert die veröffentlichte Anwendung aus dem vorherigen Bild mithilfe des `builder` Alias aus der ersten `FROM` Zeile.</span><span class="sxs-lookup"><span data-stu-id="0c02a-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="0c02a-159">Legt den Befehl fest, der beim Starten des Containers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c02a-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="0c02a-160">Der `dotnet` Befehl im Lauf Zeit Image kann nur DLL-Dateien ausführen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="0c02a-161">HTTPS in docker</span><span class="sxs-lookup"><span data-stu-id="0c02a-161">HTTPS in Docker</span></span>

<span data-ttu-id="0c02a-162">Microsoft Base Images für docker legen die `ASPNETCORE_URLS` Umgebungsvariable auf fest `http://+:80` . Dies bedeutet, dass Kestrel ohne HTTPS an diesem Port ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0c02a-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="0c02a-163">Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie in [selbstgeh osteten GrpC-Anwendungen](self-hosted.md)beschrieben), sollten Sie dies außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="0c02a-164">Legen Sie die Umgebungsvariable im Rahmen der Lauf Zeit Image Erstellung der dockerfile-Datei fest.</span><span class="sxs-lookup"><span data-stu-id="0c02a-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="0c02a-165">Die. dockerignore-Datei</span><span class="sxs-lookup"><span data-stu-id="0c02a-165">The .dockerignore file</span></span>

<span data-ttu-id="0c02a-166">Ähnlich wie `.gitignore` Dateien, die bestimmte Dateien und Verzeichnisse aus der Quell Code Verwaltung ausschließen, `.dockerignore` kann die Datei verwendet werden, um Dateien und Verzeichnisse auszuschließen, die während des Buildvorgangs in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c02a-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="0c02a-167">Dadurch wird nicht nur Zeit gespart, sondern es können auch einige Fehler vermieden werden, die durch das Kopieren des `obj` Verzeichnisses von Ihrem PC in das Image entstehen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="0c02a-168">Sie sollten der Datei mindestens Einträge für und hinzu `bin` fügen `obj` `.dockerignore` .</span><span class="sxs-lookup"><span data-stu-id="0c02a-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="0c02a-169">Erstellen des Image</span><span class="sxs-lookup"><span data-stu-id="0c02a-169">Build the image</span></span>

<span data-ttu-id="0c02a-170">Für eine Lösung mit einer einzelnen Anwendung und somit einer einzelnen dockerfile-Datei ist es am einfachsten, die dockerfile-Datei im Basisverzeichnis zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="0c02a-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="0c02a-171">Mit anderen Worten: Platzieren Sie Sie im gleichen Verzeichnis wie die `.sln` Datei.</span><span class="sxs-lookup"><span data-stu-id="0c02a-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="0c02a-172">Verwenden Sie in diesem Fall den folgenden `docker build` Befehl aus dem Verzeichnis mit der dockerfile-Datei, um das Image zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="0c02a-173">Das verwirrend benannte `--tag` Flag (das auf gekürzt werden kann `-t` ) gibt den vollständigen Namen des Bilds an, einschließlich des tatsächlichen Tags, wenn angegeben.</span><span class="sxs-lookup"><span data-stu-id="0c02a-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="0c02a-174">Der `.` am Ende gibt den Kontext an, in dem der Build ausgeführt wird, das aktuelle Arbeitsverzeichnis für die `COPY` Befehle in der dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="0c02a-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="0c02a-175">Wenn Sie mehrere Anwendungen in einer einzelnen Projekt Mappe haben, können Sie die dockerfile-Datei für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="0c02a-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="0c02a-176">Sie sollten weiterhin den `docker build` Befehl aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projekt Mappe und alle Projekte in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c02a-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="0c02a-177">Sie können eine dockerfile-Datei unterhalb des aktuellen Verzeichnisses angeben, indem Sie das- `--file` Flag (oder `-f` ) verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c02a-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="0c02a-178">Ausführen des Images in einem Container auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="0c02a-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="0c02a-179">Verwenden Sie den Befehl, um das Image in der lokalen docker-Instanz auszuführen `docker run` .</span><span class="sxs-lookup"><span data-stu-id="0c02a-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="0c02a-180">Das `-ti` -Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c02a-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="0c02a-181">Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 für den Container an Port 5000 auf der localhost-Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0c02a-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="0c02a-182">Pushen des Images in eine Registrierung</span><span class="sxs-lookup"><span data-stu-id="0c02a-182">Push the image to a registry</span></span>

<span data-ttu-id="0c02a-183">Nachdem Sie überprüft haben, ob das Image funktioniert, überführen Sie es per Push an eine docker-Registrierung, um es auf anderen Systemen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="0c02a-184">Interne Netzwerke müssen eine docker-Registrierung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="0c02a-185">Dies kann genauso einfach sein wie das Ausführen [des eigenen `registry` Images von Docker](https://docs.docker.com/registry/deploying/) (die Docker-Registrierung wird in einem docker-Container ausgeführt), es sind jedoch verschiedene umfassendere Lösungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c02a-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="0c02a-186">Für die externe Freigabe und die cloudnutzung stehen verschiedene verwaltete Registrierungen zur Verfügung, z. b. [Azure Container Registry](/azure/container-registry/) oder [docker Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="0c02a-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="0c02a-187">Um per Push an docker Hub zu übernehmen, stellen Sie dem Image Namen den Namen Ihres Benutzers oder Ihrer Organisation voran.</span><span class="sxs-lookup"><span data-stu-id="0c02a-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="0c02a-188">Um per Push in eine private Registrierung zu übernehmen, stellen Sie dem Image Namen den Namen des Registrierungs Hosts und den Organisationsnamen voran.</span><span class="sxs-lookup"><span data-stu-id="0c02a-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="0c02a-189">Nachdem sich das Image in einer Registrierung befindet, können Sie es auf einzelnen docker-Hosts oder in einer Container Orchestrierungs-Engine wie Kubernetes bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0c02a-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0c02a-190">[Zurück](self-hosted.md)
>[Weiter](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="0c02a-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
